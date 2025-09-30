# Remix IDE Desktop

Native desktop application wrapper for Remix IDE, the Ethereum smart contract development environment.

[View Portfolio](https://zachayers.io) | [Live Demo](https://remix.zachayers.io)

## About

Remix IDE Desktop brings the full Remix Ethereum IDE experience to your desktop as a native application. Built with Electron, it provides a dedicated window for smart contract development, eliminating the need for browser tabs and offering a more integrated development workflow. Perfect for Solidity developers who prefer native applications or need to work offline with locally hosted Remix instances.

## Built With

- Electron
- Node.js
- Remix IDE (embedded)
- Electron Builder
- Electron Squirrel (auto-updates)

## Features

- **Native Desktop Experience** - Run Remix IDE as a standalone application
- **Cross-Platform Support** - Available for Windows, macOS, and Linux
- **Dedicated Development Window** - No browser distractions or tab management
- **Custom App Icon** - Professional branding with high-resolution icons
- **Auto-Update Support** - Built-in update mechanism via Electron Squirrel
- **Offline Capability** - Can be configured to work with local Remix instance
- **DevTools Access** - Full Chrome DevTools for debugging smart contracts

## Getting Started

### Prerequisites

- Node.js 14.x or higher
- npm or yarn

### Installation

```bash
git clone https://github.com/N73311/remix.ide.git
cd remix.ide
npm install
```

### Development

```bash
npm start         # Launch the application in development mode
npm run build     # Build distributables for current platform
npm run dist      # Build and package for distribution
```

### Building for All Platforms

```bash
npm run build-win     # Build for Windows
npm run build-mac     # Build for macOS
npm run build-linux   # Build for Linux
```

## Project Structure

```
remix.ide/
├── src/
│   ├── main.js         # Main process entry point
│   ├── preload.js      # Preload script for security
│   └── renderer.js     # Renderer process scripts
├── assets/             # Application icons and resources
├── build/              # Build configuration
└── dist/               # Built distributables
```

## Smart Contract Development

Once launched, you have access to:
- Solidity compiler with multiple versions
- Contract deployment and testing
- Debugger and static analysis tools
- Plugin ecosystem
- File explorer for project management
- Integration with MetaMask and hardware wallets

## Security

- Electron security best practices implemented
- Context isolation enabled
- Remote content loaded only from trusted Remix domains
- No node integration in renderer process

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.

## Author

Zachariah Ayers - [zachayers.io](https://zachayers.io)