# 🚀 PerfBench - Advanced CPU Performance Benchmarking Suite

[![.NET](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/download/dotnet/8.0)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen.svg)]()

A comprehensive CPU performance benchmarking suite designed to test various aspects of processor performance including arithmetic operations, compression algorithms, cryptographic functions, and specialized instruction sets (AVX, SSE, BMI, FMA, etc.).

## ✨ Features

- **Comprehensive Benchmarking**: Tests arithmetic, compression, cryptography, and specialized instruction sets
- **Multi-threading Support**: Automatic CPU core detection and manual thread configuration
- **Cross-platform**: Supports Windows, Linux, macOS, and ARM architectures
- **Memory Efficient**: Optimized for low-memory devices
- **Real-time Progress**: Visual progress bars and detailed execution tracking
- **Result Persistence**: Save and compare benchmark results over time
- **Hardware Detection**: Automatic system information gathering

## 🏗️ Architecture

The project consists of two main components:

- **Benchmarker**: The main executable application with command-line interface
- **Benchmarking**: Core benchmarking engine with extensible benchmark framework

## 🚀 Quick Start

### Prerequisites

- .NET 8.0 SDK or later
- Windows, Linux, or macOS
- PowerShell (for build scripts)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Tuhin-SnapD/PerfBench.git
   cd PerfBench
   ```

2. **Build the project**
   ```bash
   # Using PowerShell (Windows)
   .\build.ps1
   
   # Using dotnet CLI
   dotnet build Benchmarking.sln
   ```

3. **Run benchmarks**
   ```bash
   # List available benchmarks
   .\Benchmarker\bin\Release\net8.0\benchmarker.exe --list-benchmarks
   
   # Run a specific benchmark
   .\Benchmarker\bin\Release\net8.0\benchmarker.exe --benchmark=arithmetic
   
   # Run with multiple threads
   .\Benchmarker\bin\Release\net8.0\benchmarker.exe --benchmark=compression --multithreaded
   ```

## 📋 Available Benchmarks

### 🧮 Arithmetic Benchmarks
- **Integer Operations**: Addition, subtraction, multiplication, division for int32 and int64
- **Floating Point**: Single and double precision arithmetic operations
- **Performance Categories**: Basic arithmetic performance testing

### 🗜️ Compression Benchmarks
- **ZIP**: Standard ZIP compression/decompression
- **GZip**: GZip compression/decompression  
- **BZip2**: BZip2 compression/decompression
- **Deflate**: Deflate compression/decompression

### 🔐 Cryptographic Benchmarks
- **AES Encryption/Decryption**: Advanced Encryption Standard operations
- **Hashing**: SHA-256 hash computation
- **CSPRNG**: Cryptographically secure pseudo-random number generation

### ⚡ Instruction Set Extensions
- **AVX/AVX2**: Advanced Vector Extensions performance
- **SSE/SSE2/SSE3/SSE4**: Streaming SIMD Extensions
- **BMI1/BMI2**: Bit Manipulation Instructions
- **FMA**: Fused Multiply-Add operations
- **PCLMULQDQ**: Carryless multiplication

### 📊 Parsing Benchmarks
- **JSON Parsing**: Large and small JSON file processing
- **HTML Parsing**: HTML document parsing performance

## 🛠️ Command Line Options

### Basic Usage
```bash
.\benchmarker.exe --benchmark={BENCHMARK_NAME}
```

### Threading Options
```bash
# Auto-detect CPU cores
.\benchmarker.exe --multithreaded

# Manual thread count
.\benchmarker.exe --threads=8
```

### Execution Options
```bash
# Run multiple iterations
.\benchmarker.exe --runs=10

# Memory efficient mode
.\benchmarker.exe --memory-efficient

# Stress test mode
.\benchmarker.exe --stress
```

### Utility Options
```bash
# List all benchmarks
.\benchmarker.exe --list-benchmarks

# Clear saved results
.\benchmarker.exe --clear-save
```

### Combined Example
```bash
.\benchmarker.exe --benchmark=compression --multithreaded --runs=5 --memory-efficient
```

## 📊 Benchmark Categories

### General Categories
- `ALL` - Run all available benchmarks
- `COMPRESSION` - All compression benchmarks
- `DECOMPRESSION` - All decompression benchmarks  
- `ARITHMETIC` - All arithmetic benchmarks
- `EXTENSION` - All instruction extension benchmarks
- `CRYPTOGRAPHY` - All cryptographic benchmarks
- `PARSING` - All parsing benchmarks

### Specific Benchmarks
- `arithmetic_int` - Integer arithmetic performance
- `arithmetic_float` - Floating point arithmetic
- `arithmetic_double` - Double precision arithmetic
- `zip` - ZIP compression/decompression
- `gzip` - GZip compression/decompression
- `bzip2` - BZip2 compression/decompression
- `deflate` - Deflate compression/decompression
- `encryption` - AES encryption performance
- `hashing` - SHA-256 hashing performance
- `avx` - AVX instruction set performance
- `sse` - SSE instruction set performance
- `json` - JSON parsing performance
- `html` - HTML parsing performance

## 🏗️ Development

### Project Structure
```
PerfBench/
├── Benchmarker/           # Main executable application
├── Benchmarking/          # Core benchmarking engine
├── docs/                 # Documentation and web interface
├── build.ps1            # Build script
└── Benchmarking.sln     # Visual Studio solution
```

### Building from Source
```bash
# Restore dependencies
dotnet restore

# Build in Debug mode
dotnet build

# Build in Release mode
dotnet build -c Release

# Run tests
dotnet test
```

### Adding New Benchmarks
1. Create a new class inheriting from `Benchmark`
2. Implement required methods: `Run()`, `GetName()`, `GetDescription()`
3. Add to the appropriate category in the benchmark discovery system

## 📈 Performance Reference

The benchmark includes reference points for a Ryzen 9 3900X system:
- **CPU**: AMD Ryzen 9 3900X (non-overclocked)
- **RAM**: 32 GB DDR4-3200 CL16
- **Motherboard**: ASUS Crosshair VIII Hero

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Setup
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Run tests: `dotnet test`
5. Commit changes: `git commit -m 'Add amazing feature'`
6. Push to branch: `git push origin feature/amazing-feature`
7. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [CommandLine](https://github.com/commandlineparser/commandline) - Command line argument parsing
- [ShellProgressBar](https://github.com/Mpdreamz/shellprogressbar) - Progress bar implementation
- [HTMLAgilityPack](https://github.com/zzzprojects/html-agility-pack) - HTML parsing
- [Newtonsoft.Json](https://github.com/JamesNK/Newtonsoft.Json) - JSON processing
- [SharpZipLib](https://github.com/icsharpcode/SharpZipLib) - Compression algorithms

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Tuhin-SnapD/PerfBench/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Tuhin-SnapD/PerfBench/discussions)
- **Documentation**: [Wiki](https://github.com/Tuhin-SnapD/PerfBench/wiki)

## 🔄 Changelog

See [CHANGELOG.md](CHANGELOG.md) for a detailed list of changes and version history.

---

**Made with ❤️ for the performance testing community**
