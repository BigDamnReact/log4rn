<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/25423296/163456776-7f95b81a-f1ed-45f7-b7ab-8fa810d529fa.png">
  <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
  <img alt="Shows an illustrated sun in light mode and a moon with stars in dark mode." src="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
</picture>

# Log4R(N)

## Overview

**Log4R(N)** is a modern and efficient logging library for both **React** and **React Native** applications. Inspired by popular logging frameworks like **Log4j**, **NLog**, and **log4net**, Log4R(N) provides a familiar "multi-appender" logging architecture, tailored to the needs of web and mobile development. With Log4R(N), developers can achieve detailed logging, robust performance, and seamless integration across platforms.

## Features

- **Multi-Appender Support**: Route logs to multiple destinations (console, file, remote server, etc.).
- **Customizable Log Levels**: Support for `DEBUG`, `INFO`, `WARN`, `ERROR`, and more.
- **Performance-Aware**: Optimized for React and React Native environments, with buffering and batching for network logs.
- **React Native Ready**: Compatible with native modules like `react-native-fs` for file logging and AsyncStorage for local storage.
- **Extensible Design**: Easily add custom appenders for specialized use cases.

## Installation

Install Log4R(N) via npm or yarn:

```bash
npm install log4rn
# or
yarn add log4rn
```

## Getting Started

Here’s how to use Log4R(N) in your application:

```javascript
import { Logger, ConsoleAppender, FileAppender, NetworkAppender } from 'log4rn';

// Configure your logger with appenders
const logger = new Logger([
  new ConsoleAppender({ levelThreshold: 'DEBUG' }),
  new FileAppender({ levelThreshold: 'INFO', filePath: 'logs/app.log' }),
  new NetworkAppender({ levelThreshold: 'WARN', endpoint: 'https://example.com/logs' }),
]);

// Use the logger
logger.debug('Debugging information');
logger.info('User signed in');
logger.warn('Low disk space');
logger.error('Unhandled exception occurred');
```

## Configuration

You can configure Log4R(N) to suit your app’s logging requirements. Each appender accepts options such as log level thresholds, file paths, or remote endpoints.

### Example Configuration

```javascript
const logger = new Logger([
  new ConsoleAppender({ levelThreshold: 'DEBUG' }),
  new FileAppender({ levelThreshold: 'ERROR', filePath: 'logs/errors.log' }),
  new NetworkAppender({
    levelThreshold: 'WARN',
    endpoint: 'https://example.com/logs',
    bufferSize: 10, // Batch logs to minimize network requests
  }),
]);
```

## Why Log4R(N)?

The name **Log4R(N)** reflects its lineage and inspiration from established logging frameworks like:

- **Log4j**: A popular Java-based logging framework that pioneered the multi-appender architecture.
- **NLog**: A flexible .NET logging library known for its extensive configurability.
- **log4net**: The .NET adaptation of Log4j, with similar features and functionality.

### Clarification

While the name "Log4R(N)" pays homage to these frameworks, it is a distinct project tailored to the JavaScript ecosystem, specifically **React** and **React Native**. It is not affiliated with or derived from the Apache Logging Services project, **Log4n**, **NLog**, or any other "log4" libraries.

## Repository

The official repository for Log4R(N) is hosted on GitHub:

[Log4R(N) GitHub Repository](https://github.com/BigDamnReact/log4rn)

## Use Cases

- **React Web Applications**: Debug and monitor browser-based applications with console and remote logging.
- **React Native Mobile Apps**: Capture logs locally on devices or send them to remote servers for analysis.
- **Hybrid Apps**: Share logging configuration and appenders across web and mobile platforms seamlessly.

## Contributions

Contributions are welcome! If you’d like to improve the project or add new features, please read our [Contribution Guidelines](CONTRIBUTING.md).

### Contributor License Agreement (CLA)

To ensure future flexibility for licensing, all contributors are required to sign a Contributor License Agreement (CLA). This allows the maintainers to use the contributions in open-source and commercial contexts while preserving proper attribution.

## Support

If you find this library helpful, consider supporting its development by:
- [Starring the GitHub repository](https://github.com/BigDamnReact/log4rn).
- Contributing code, documentation, or ideas.


## License

Log4R(N) is open-source software licensed under the **MIT License**.

## Roadmap
- NPM Publish
- The Log engine. 
- Add support for in-memory ring buffers for debugging.
- Introduce more appenders (e.g., email, cloud services).
- Enhance React Native integrations for offline log persistence.

## Acknowledgments

This project is inspired by the rich ecosystem of logging libraries across various programming languages, including Log4j, NLog, and log4net, and is adapted to meet the needs of modern JavaScript and mobile development.

---

Start logging smarter with Log4R(N) today!

