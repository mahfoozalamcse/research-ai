# Research AI Assistant

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/mahfoozalamcse/research-ai.svg)](https://github.com/mahfoozalamcse/research-ai)
[![GitHub Issues](https://img.shields.io/github/issues/mahfoozalamcse/research-ai.svg)](https://github.com/mahfoozalamcse/research-ai/issues)

A powerful Chrome extension that leverages AI to enhance your research workflow, providing intelligent assistance for information gathering, analysis, and documentation.

## 🎯 Features

- **AI-Powered Research Assistant**: Intelligent suggestions and insights while browsing
- **Quick Content Analysis**: Summarize and analyze web content with AI
- **Smart Highlighting**: Automatically highlight key information relevant to your research
- **Citation Management**: Easy reference collection and citation generation
- **One-Click Lookup**: Quickly search academic databases and research repositories
- **Local Storage**: Secure offline storage of your research materials
- **Keyboard Shortcuts**: Efficient workflow with customizable keyboard shortcuts

## 📋 Table of Contents

- [Installation](#installation)
- [Quick Start](#quick-start)
- [Features](#-features)
- [Technologies](#-technologies)
- [Project Structure](#-project-structure)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Development](#-development)
- [Contributing](#-contributing)
- [Troubleshooting](#-troubleshooting)
- [License](#-license)
- [Support](#-support)

## 📦 Installation

### From Chrome Web Store
Visit the [Chrome Web Store](https://chrome.google.com/webstore) and search for "Research AI Assistant" or use the direct link once published.

### Manual Installation (Development)

1. **Clone the repository**
   ```bash
   git clone https://github.com/mahfoozalamcse/research-ai.git
   cd research-ai
   ```

2. **Build the extension**
   ```bash
   npm install
   npm run build
   ```

3. **Load in Chrome**
   - Open `chrome://extensions/` in your browser
   - Enable "Developer mode" (top-right corner)
   - Click "Load unpacked"
   - Select the `dist` or `build` directory from the project

## 🚀 Quick Start

1. **Install the extension** following the installation steps above
2. **Pin the extension** to your Chrome toolbar for easy access
3. **Open your first research project** and look for the Research AI Assistant icon
4. **Right-click** on any text to access AI-powered options
5. **Configure settings** in the extension preferences to suit your needs

## 🔧 Technologies

The project is built with a robust tech stack:

- **Backend**: Java (61.2%)
  - Core business logic and AI processing
  - Research data management
  - SpringBoot framework for REST APIs
  - Gemini API integration for intelligent assistance

- **Frontend**: JavaScript (20.9%) & HTML (8.7%)
  - Chrome extension UI
  - Real-time content interaction
  - User interface components

- **Styling**: CSS (9.2%)
  - Responsive design
  - Modern UI/UX

## 📁 Project Structure

```
research-ai/
├── src/
│   ├── main/
│   │   ├── java/              # Java backend services
│   │   │   └── SpringBoot app with Gemini API integration
│   │   ├── resources/         # Configuration files
│   │   └── ...
│   ├── chrome/
│   │   ├── popup/             # Extension popup UI
│   │   ├── content/           # Content scripts
│   │   ├── background/        # Background service worker
│   │   ├── styles/            # CSS stylesheets
│   │   └── manifest.json      # Chrome extension manifest
│   └── assets/                # Images and icons
├── build/                     # Build output
├── package.json               # Node.js dependencies
├── pom.xml                    # Maven configuration
└── README.md                  # This file
```

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
GEMINI_KEY=your_gemini_api_key_here
SPRING_PORT=8080
EXTENSION_ID=your_chrome_extension_id
```

### Extension Settings

Access settings by clicking the extension icon and navigating to "Options":

- **API Key**: Add your Gemini API key for enhanced features
- **Theme**: Choose between Light, Dark, or Auto modes
- **Keyboard Shortcuts**: Customize shortcuts for quick access
- **Auto-Save**: Enable/disable automatic saving of research notes
- **Privacy Level**: Adjust data collection preferences

### manifest.json

Key permissions configured:
- `activeTab`: Access current tab content
- `scripting`: Inject content scripts
- `storage`: Store user data locally
- `webRequest`: Monitor and modify web requests

## 💡 Usage

### Basic Operations

**Highlight and Research**
1. Select any text on a webpage
2. Right-click to open context menu
3. Choose "Analyze with AI" or related options
4. View insights in the side panel

**Save References**
1. Click the extension icon
2. Use "Add to Research" button
3. Add tags and notes
4. Access saved items from the popup

**Generate Citations**
1. Open saved references
2. Select desired citation format (APA, MLA, Chicago, etc.)
3. Copy the formatted citation

### Advanced Features

**Smart Highlighting**
- Enables automatic highlighting of key research terms
- Configure highlighted terms in settings

**Quick Lookup**
- Use keyboard shortcut (default: `Ctrl+Shift+R`) for instant research
- Select search scope (Google Scholar, PubMed, arXiv, etc.)

## 👨‍💻 Development

### Prerequisites

- Node.js 14+ and npm
- Java 11+ and Maven
- Chrome/Chromium browser
- Gemini API key from [Google AI Studio](https://makersuite.google.com/)

### Setup Development Environment

```bash
# Install frontend dependencies
npm install
npm install -g webpack webpack-cli

# Install Java backend (Maven)
mvn install

# Build for development
npm run dev

# Build for production
npm run build

# Run tests
npm test

# Lint code
npm run lint
```

### Building from Source

```bash
# Start Java Spring Boot backend
mvn spring-boot:run

# Build frontend in another terminal
npm run build

# Load extension in Chrome
# Open chrome://extensions/ → Enable Developer Mode → Load unpacked
```

### Testing

```bash
# Run all tests
npm test

# Run with coverage
npm run test:coverage

# Run specific test file
npm test -- --testPathPattern=filename

# Run Java tests
mvn test
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Make** your changes and commit (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Code Standards

- Follow existing code style and conventions
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

### Reporting Issues

Found a bug? Please [open an issue](https://github.com/mahfoozalamcse/research-ai/issues) with:
- Clear title and description
- Steps to reproduce
- Expected vs actual behavior
- Screenshots/logs if applicable
- Your environment details

## 🐛 Troubleshooting

### Extension Won't Load

**Solution**: Ensure you're loading from the correct directory containing `manifest.json`

### AI Features Not Working

**Solution**: 
- Verify Gemini API key is correctly set in environment variables
- Check internet connection
- Ensure API quota hasn't been exceeded
- Verify backend service is running on correct port

### GEMINI_KEY Error

**Solution**:
- Get your key from [Google AI Studio](https://makersuite.google.com/)
- Add to `.env` file: `GEMINI_KEY=your_key_here`
- Restart the Spring Boot application

### Content Scripts Not Injecting

**Solution**:
- Refresh the webpage
- Reload the extension from `chrome://extensions/`
- Clear browser cache
- Check manifest.json permissions

### Performance Issues

**Solution**:
- Reduce the number of simultaneous research operations
- Disable auto-save if not needed
- Clear stored research data periodically
- Check backend service memory usage

For more help, check [open issues](https://github.com/mahfoozalamcse/research-ai/issues) or create a new one.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 💬 Support

- **Documentation**: [Wiki](https://github.com/mahfoozalamcse/research-ai/wiki)
- **Issues**: [GitHub Issues](https://github.com/mahfoozalamcse/research-ai/issues)
- **Discussions**: [GitHub Discussions](https://github.com/mahfoozalamcse/research-ai/discussions)
- **Email**: mahfoozalamcse@gmail.com

## 🙏 Acknowledgments

- Thanks to all contributors who have helped improve this project
- Powered by [Google Gemini API](https://ai.google.dev/)
- Built with SpringBoot and Chrome Extension APIs
- Inspired by the research community's needs

---

**Made with ❤️ by [Mahfooz Alam](https://github.com/mahfoozalamcse)**

Last updated: 2026-04-25
