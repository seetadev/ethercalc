# EtherCalc

A web-based collaborative spreadsheet server that enables real-time multi-user editing of spreadsheets through a web browser. EtherCalc provides a powerful online spreadsheet solution with support for formulas, formatting, and simultaneous collaboration without requiring user accounts.

## 🚀 Features

- **Real-time Collaboration** - Multiple users can edit the same spreadsheet simultaneously
- **No Registration Required** - Start collaborating immediately without creating accounts
- **Rich Formula Support** - Full spreadsheet functionality with extensive formula library
- **Import/Export** - Support for CSV, Excel, and JSON formats
- **Multi-language Support** - Internationalization with support for 7 languages
- **RESTful API** - Programmatic access to spreadsheet data and operations
- **Cross-platform** - Works on desktop and mobile browsers
- **Persistent Storage** - Data persistence with Redis backend
- **CORS Support** - Cross-origin resource sharing for API integration
- **Docker Support** - Easy deployment with Docker and Docker Compose

## 🛠️ Tech Stack

### Frontend
- **SocialCalc** - Core spreadsheet engine
- **JavaScript/LiveScript** - Client-side logic and UI
- **CSS/Stylus** - Styling and responsive design
- **HTML5** - Modern web standards
- **Webpack** - Module bundling and asset management

### Backend/Services
- **Node.js** (>= 0.8.x) - Server runtime
- **ZappaJS** - Web application framework
- **Redis** - Data persistence and session storage
- **Express.js** - HTTP server middleware
- **CORS** - Cross-origin resource sharing

### Development Tools
- **LiveScript** - Functional programming language that compiles to JavaScript
- **Webpack** - Module bundler with hot reload
- **PM2** - Process manager for production deployment
- **Docker** - Containerization
- **Make** - Build automation

### Mobile/Desktop
- **Progressive Web App** - Mobile-friendly with app manifest
- **Responsive Design** - Adaptive layout for all screen sizes
- **Touch Support** - Mobile gesture support

## 📁 Project Structure

```
├── app.js              # Main application entry point
├── main.js             # Core application logic
├── db.js               # Database abstraction layer
├── bin/                # Executable scripts and runners
├── src/                # Source code files
├── static/             # Static assets and compiled files
├── images/             # UI icons and graphics
├── l10n/               # Internationalization files
├── multi/              # Multi-user collaboration components
├── third-party/        # External libraries and dependencies
├── apache/             # Apache configuration files
├── nginx/              # Nginx configuration files
└── misc/               # Utility scripts and tools
```

## 🔧 Installation & Setup

### Prerequisites
- Node.js (>= 0.8.x)
- Redis server
- npm package manager

### Installation Steps

#### Option 1: Direct Installation
```bash
# Install globally via npm
npm install -g ethercalc

# Start Redis server (if not already running)
redis-server

# Run EtherCalc
ethercalc
```

#### Option 2: From Source
```bash
# Clone the repository
git clone https://github.com/audreyt/ethercalc.git
cd ethercalc

# Install dependencies
npm install

# Build the application
make

# Start the application
npm start
```

#### Option 3: Docker (Recommended)
```bash
# Using Docker Compose
docker-compose up -d

# Or using standalone Docker
docker run -d -p 8000:8000 audreyt/ethercalc
```

## 🎯 Usage

### Development
```bash
# Start in development mode
node app.js

# Build assets with webpack
npm run webpack

# Run with live reload
npm run dev
```

### Production
```bash
# Start with PM2 process manager
pm2 start app.js --name ethercalc

# Or start directly
NODE_ENV=production node app.js

# With CORS enabled
node app.js --cors
```

### Docker Deployment
```bash
# Start services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

### API Usage
```bash
# Create/access a spreadsheet
GET/POST /:room_id

# Export as CSV
GET /:room_id.csv

# Export as JSON
GET /:room_id.json

# Get cell value
GET /:room_id/cells/:cell_id
```

## 📱 Platform Support

- **Web Browsers** - Chrome, Firefox, Safari, Edge
- **Mobile** - iOS Safari, Android Chrome
- **Desktop** - All major operating systems
- **Progressive Web App** - Installable on mobile devices
- **Docker** - Linux, macOS, Windows

## 🧪 Testing

```bash
# Run test suite
npm test

# Test specific components
node misc/test-sumifs.ls
```

## 🔄 Deployment

### Docker Deployment
The project includes comprehensive Docker support:

```yaml
# docker-compose.yml setup
version: '3'
services:
  ethercalc:
    image: audreyt/ethercalc
    ports:
      - "80:8000"
    links:
      - redis
  redis:
    image: redis:latest
    volumes:
      - /var/lib/redis:/data
```

### Apache/Nginx Configuration
Configuration files are provided for both Apache and Nginx reverse proxy setups in the `apache/` and `nginx/` directories.

### Environment Variables
- `REDIS_HOST` - Redis server hostname
- `REDIS_PORT` - Redis server port
- `REDIS_PASS` - Redis password (if required)
- `NODE_ENV` - Environment mode (development/production)

## 📊 Performance & Optimization

- **Redis Backend** - Efficient data storage and retrieval
- **WebSocket Communication** - Real-time updates with minimal latency
- **Asset Optimization** - Webpack bundling and minification
- **Process Management** - PM2 for production reliability
- **Caching** - HTTP caching headers for static assets

## 🌍 Internationalization

EtherCalc supports multiple languages:
- English (en)
- German (de)
- Spanish (es-ES)
- French (fr)
- Russian (ru-RU)
- Simplified Chinese (zh-CN)
- Traditional Chinese (zh-TW)

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Use LiveScript for new server-side code
- Follow existing code style and conventions
- Test your changes with multiple browsers
- Update documentation as needed
- Ensure Docker builds work correctly

## 📄 License

This project is licensed under the Common Public Attribution License Version 1.0 (CPAL-1.0). See the [LICENSE.txt](LICENSE.txt) file for details.

## 🙏 Acknowledgments

- **SocialCalc** - The powerful spreadsheet engine that powers EtherCalc
- **LiveScript** - Functional programming language for elegant server-side code
- **Redis Labs** - For the excellent Redis database
- **Docker** - For containerization support
- **The Open Source Community** - For continuous improvements and bug reports

## 📞 Support & Contact

- **Homepage**: [http://ethercalc.net/](http://ethercalc.net/)
- **Repository**: [https://github.com/audreyt/ethercalc](https://github.com/audreyt/ethercalc)
- **Issues**: Report bugs and request features on GitHub Issues
- **API Documentation**: See [API.md](API.md) for detailed API reference

---

**Start collaborating on spreadsheets today!** 🎉