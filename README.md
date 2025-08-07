# Remix IDE Desktop

A native desktop application wrapper for Remix IDE, the powerful web-based Ethereum smart contract development environment. Built with Electron to provide a standalone development experience for Solidity developers.

## Overview

Remix IDE Desktop brings the full Remix Ethereum IDE experience to your desktop as a native application. This Electron wrapper provides a dedicated window for smart contract development, eliminating the need for browser tabs and offering a more integrated development workflow. Perfect for developers who prefer native applications or need to work offline with locally hosted Remix instances.

## Features

- **Native Desktop Experience** - Run Remix IDE as a standalone application
- **Cross-Platform Support** - Available for Windows, macOS, and Linux
- **Dedicated Development Window** - No browser distractions or tab management
- **Custom App Icon** - Professional branding with high-resolution icons
- **Auto-Update Support** - Built-in update mechanism via Electron Squirrel
- **Offline Capability** - Can be configured to work with local Remix instance
- **DevTools Access** - Full Chrome DevTools for debugging smart contracts

## Installation

### Prerequisites

- Node.js (v14 or higher)
- npm or Yarn package manager
- Git for cloning the repository

### Quick Start

```bash
# Clone the repository
git clone https://github.com/N73311/remix.ide.git
cd remix.ide

# Install dependencies
yarn install
# or
npm install

# Start the application
yarn start
# or
npm start
```

### Building Installers

```bash
# Package the application
yarn package

# Create platform-specific installers
yarn make

# Publish to GitHub releases (requires GH_TOKEN)
yarn publish
```

## Project Structure

```
remix.ide/
├── src/
│   ├── assets/             # Application icons and resources
│   │   ├── icon_*.png      # Various icon sizes
│   │   ├── icon_*.icns     # macOS icons
│   │   └── Contents.json   # Icon metadata
│   └── index.js            # Main Electron process
├── package.json            # Project configuration
├── yarn.lock               # Dependency lock file
└── README.md               # This file
```

## Configuration

### Main Process (src/index.js)

The application is configured to:
- Load Remix IDE from `http://remix.ethereum.org/`
- Set initial window size to 800x600
- Use custom application icons
- Handle platform-specific behaviors (macOS dock, Windows installer)

### Customization Options

1. **Change Remix URL**: Edit line 22 in `src/index.js`
   ```javascript
   mainWindow.loadURL("http://remix.ethereum.org/");
   ```

2. **Window Size**: Modify the BrowserWindow options
   ```javascript
   const mainWindow = new BrowserWindow({
     width: 1200,  // Custom width
     height: 800,  // Custom height
     icon: iconPath,
   });
   ```

3. **Enable DevTools**: Uncomment line 25
   ```javascript
   mainWindow.webContents.openDevTools();
   ```

## Development

### Running in Development Mode

```bash
# Start with hot-reload
yarn start

# The app will open with Remix IDE loaded
# Any changes to index.js will require restart
```

### Debugging

1. Enable DevTools in the code (uncomment line 25)
2. Use Chrome DevTools for web debugging
3. Use VS Code's Node.js debugger for main process

### Building for Production

```bash
# Windows
yarn make --platform=win32

# macOS
yarn make --platform=darwin

# Linux
yarn make --platform=linux
```

## Platform-Specific Notes

### macOS
- Custom dock icon is automatically set
- App stays in dock when all windows are closed
- Supports native macOS features (menu bar, shortcuts)

### Windows
- Squirrel installer handles shortcuts and updates
- Start menu and desktop shortcuts created on install
- Auto-update support via Squirrel.Windows

### Linux
- Supports .deb and .rpm packages
- Desktop file created for application launchers
- Icon properly integrated with system theme

## Technologies Used

- **Electron** - Cross-platform desktop app framework
- **Electron Forge** - Build toolchain and packaging
- **Electron Squirrel** - Auto-update and installer framework
- **Node.js** - JavaScript runtime
- **Remix IDE** - Ethereum smart contract IDE (loaded via web)

## Troubleshooting

### Common Issues

1. **App won't start**: Ensure Node.js v14+ is installed
2. **Build fails**: Clear node_modules and reinstall
3. **Icon not showing**: Check icon paths in package.json
4. **Can't connect to Remix**: Check internet connection

### Debug Mode

To run in debug mode with full logging:
```bash
DEBUG=electron-forge:* yarn start
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Future Enhancements

- Local Remix instance bundling
- Custom themes and preferences
- Plugin system for Electron-specific features
- File system integration for local projects
- Multi-window support for parallel development

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Remix IDE team for the excellent smart contract development environment
- Electron community for the robust desktop framework
- Ethereum Foundation for supporting developer tools
