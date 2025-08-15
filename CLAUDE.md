# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Build and Setup
- `npm install` - Install dependencies 
- `npm run build` - Build the project (updates icons and fonts from external sources)
- `npm start` - Start local development server using http-server on ./generator directory

### Testing
- No automated tests are configured (test script returns error)

## Project Architecture

This is a static HTML/CSS/JavaScript RPG card generator that runs entirely in the browser. The main application lives in the `./generator` directory.

### Core Structure
- **Main Entry**: `generator/index.html` - Primary UI for card creation
- **Output View**: `generator/output.html` - Displays generated cards for printing
- **Documentation**: `generator/documentation.html` - User documentation

### Key JavaScript Modules
- `js/cards.js` - Core card generation logic and default options
- `js/ui.js` - Main user interface controls and interactions
- `js/colors.js` - Color management and theming
- `js/common.js` - Shared utilities
- `js/doc_parser.js` - Documentation parsing
- `js/output.js` - Card output and printing functionality

### Data and Configuration
- `data/card_data.js` - User's card data (empty by default)
- `data/card_data_example.js` - Example card definitions
- Card data is stored as JavaScript arrays in the global `card_data` variable

### Asset Management
- **Icons**: `generator/icons/` - Auto-generated from game-icons.net during build
- **Custom Icons**: `resources/custom-icons/` - User-provided icons (PNG/SVG)
- **Fonts**: `generator/fonts/` - Icon fonts from gameicons-font project
- Build process downloads and processes external icon/font assets

### Styling
- Uses Bootstrap 3 for UI framework
- Custom CSS in `generator/css/` directory
- Card styling in `css/cards.css` and `css/card-size.css`
- Icon-specific styles auto-generated during build

### Build Tools
- `resources/tools/update-icons.js` - Downloads and processes game-icons.net SVG icons
- `resources/tools/update-fonts.js` - Downloads and installs gameicons-font assets
- Both tools create CSS and JS files for icon integration

## Development Notes

The project must be built at least once before use to populate icon and font assets. The generator creates printable RPG cards with customizable layouts, colors, and content.

Card definitions use a specific JavaScript object format with properties like title, contents, color, and icon references. See `card_data_example.js` for formatting examples.