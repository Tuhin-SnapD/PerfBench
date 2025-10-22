# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Comprehensive README with installation and usage instructions
- Contributing guidelines for open source development
- Enhanced .gitignore for .NET projects
- GitHub-ready project structure

### Changed
- Improved project documentation and organization
- Enhanced build scripts and cross-platform support

## [0.6.0] - 2024-01-XX

### Added
- .NET 8.0 support
- Cross-platform builds for Windows, Linux, macOS, and ARM
- Comprehensive benchmark suite including:
  - Arithmetic benchmarks (int32, int64, float, double)
  - Compression benchmarks (ZIP, GZip, BZip2, Deflate)
  - Cryptographic benchmarks (AES, SHA-256, CSPRNG)
  - Instruction set extension benchmarks (AVX, SSE, BMI, FMA)
  - Parsing benchmarks (JSON, HTML)
- Multi-threading support with automatic CPU core detection
- Memory-efficient execution modes
- Real-time progress tracking with visual progress bars
- Result persistence and comparison system
- Hardware information gathering
- Stress testing capabilities
- Command-line interface with extensive options

### Changed
- Migrated from .NET Core 3.0 to .NET 8.0
- Improved benchmark execution engine
- Enhanced result formatting and reporting
- Better error handling and logging

### Fixed
- Memory leaks in compression benchmarks
- Threading issues in multi-core execution
- Progress bar display in redirected console scenarios
- Cross-platform compatibility issues

## [0.5.0] - 2023-XX-XX

### Added
- Initial release of BenchmarkerPDC
- Basic arithmetic benchmarking
- Compression algorithm testing
- Simple command-line interface

### Changed
- Migrated from original CPU Benchmark project
- Improved code organization and structure

## [0.1.0] - 2022-XX-XX

### Added
- Original CPU Benchmark implementation
- Basic performance testing framework
- Initial benchmark categories

---

## Legend

- **Added** for new features
- **Changed** for changes in existing functionality
- **Deprecated** for soon-to-be removed features
- **Removed** for now removed features
- **Fixed** for any bug fixes
- **Security** for vulnerability fixes
