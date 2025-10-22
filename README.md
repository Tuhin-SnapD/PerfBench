# 🚀 PerfBench - Advanced CPU Performance Benchmarking Suite

[![.NET](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/download/dotnet/8.0)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen.svg)]()
[![Downloads](https://img.shields.io/badge/Downloads-1K+-blue.svg)]()
[![Stars](https://img.shields.io/github/stars/Tuhin-SnapD/PerfBench?style=social)](https://github.com/Tuhin-SnapD/PerfBench)

> **A comprehensive CPU performance benchmarking suite** designed to test various aspects of processor performance including arithmetic operations, compression algorithms, cryptographic functions, and specialized instruction sets (AVX, SSE, BMI, FMA, etc.).

## 🎯 Quick Demo

```bash
# Run a quick arithmetic benchmark
.\benchmarker.exe --benchmark=arithmetic --multithreaded --runs=3

# Expected Output:
# Gathering hardware information...
# OS:             Microsoft Windows 11
# Processor:      AMD Ryzen 9 5900X
# Architecture:   x64
# Logical Cores:  24
# Physical Cores: 12
# 
# Starting Benchmark...
# Running the following benchmarks in approx. 00:00:15: arithmetic
# 
# ════════════════════════════════════════════════════════════════════════════════
# BENCHMARK RESULTS
# ════════════════════════════════════════════════════════════════════════════════
# 
# Single-threaded Results:
# ┌─────────────────┬─────────────┬─────────────┬─────────────┬─────────────┐
# │ Benchmark       │ Score       │ Throughput  │ Time (ms)   │ Category    │
# ├─────────────────┼─────────────┼─────────────┼─────────────┼─────────────┤
# │ Arithmetic_Int  │ 1,250,000   │ 2.5 GB/s    │ 5,000       │ Arithmetic  │
# │ Arithmetic_Float│ 980,000     │ 1.96 GB/s   │ 5,000       │ Arithmetic  │
# │ Arithmetic_Dbl  │ 750,000     │ 1.5 GB/s    │ 5,000       │ Arithmetic  │
# └─────────────────┴─────────────┴─────────────┴─────────────┴─────────────┘
# 
# Multi-threaded Results (24 threads):
# ┌─────────────────┬─────────────┬─────────────┬─────────────┬─────────────┐
# │ Benchmark       │ Score       │ Throughput  │ Time (ms)   │ Category    │
# ├─────────────────┼─────────────┼─────────────┼─────────────┼─────────────┤
# │ Arithmetic_Int  │ 28,500,000  │ 57.0 GB/s   │ 5,000       │ Arithmetic  │
# │ Arithmetic_Float│ 22,800,000  │ 45.6 GB/s   │ 5,000       │ Arithmetic  │
# │ Arithmetic_Dbl  │ 17,100,000  │ 34.2 GB/s   │ 5,000       │ Arithmetic  │
# └─────────────────┴─────────────┴─────────────┴─────────────┴─────────────┘
```

## ✨ Key Features

- **🧮 Comprehensive Benchmarking**: Tests arithmetic, compression, cryptography, and specialized instruction sets
- **⚡ Multi-threading Support**: Automatic CPU core detection and manual thread configuration
- **🌍 Cross-platform**: Supports Windows, Linux, macOS, and ARM architectures
- **💾 Memory Efficient**: Optimized for low-memory devices with configurable memory usage
- **📊 Real-time Progress**: Visual progress bars and detailed execution tracking
- **💾 Result Persistence**: Save and compare benchmark results over time
- **🔍 Hardware Detection**: Automatic system information gathering and analysis
- **📈 Performance Analysis**: Detailed throughput and latency measurements
- **🎛️ Flexible Configuration**: Extensive command-line options for customization

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
# Run a specific benchmark
.\benchmarker.exe --benchmark=arithmetic

# Run all benchmarks
.\benchmarker.exe --benchmark=ALL
```

### Threading Options
```bash
# Auto-detect CPU cores (recommended)
.\benchmarker.exe --multithreaded
# Output: Using 24 threads (auto-detected)

# Manual thread count
.\benchmarker.exe --threads=8
# Output: Using 8 threads (manual)

# Single-threaded execution
.\benchmarker.exe --threads=1
# Output: Using 1 thread (single-threaded)
```

### Execution Options
```bash
# Run multiple iterations for better accuracy
.\benchmarker.exe --runs=10
# Output: Running each benchmark 10 times and averaging results

# Memory efficient mode (for low-memory systems)
.\benchmarker.exe --memory-efficient
# Output: Using memory-efficient mode (reduced data sizes)

# Stress test mode (continuous execution)
.\benchmarker.exe --stress
# Output: Stress test mode - press any key to stop
```

### Utility Options
```bash
# List all available benchmarks
.\benchmarker.exe --list-benchmarks
# Output:
# Available Benchmarks:
# - arithmetic (Arithmetic operations)
# - compression (Data compression)
# - cryptography (Encryption/Hashing)
# - avx (AVX instruction sets)
# - sse (SSE instruction sets)
# - json (JSON parsing)
# - html (HTML parsing)

# Clear saved results
.\benchmarker.exe --clear-save
# Output: Successfully cleared all saved data!
```

### Advanced Examples
```bash
# High-performance compression test
.\benchmarker.exe --benchmark=compression --multithreaded --runs=5 --memory-efficient

# Cryptographic performance analysis
.\benchmarker.exe --benchmark=cryptography --threads=16 --runs=3

# Instruction set extension testing
.\benchmarker.exe --benchmark=avx --multithreaded --stress

# Memory-constrained environment
.\benchmarker.exe --benchmark=arithmetic --threads=2 --memory-efficient --runs=1
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

## 🌐 Web Interface

PerfBench includes a modern web interface for visualizing benchmark results:

### Features
- **📊 Interactive Charts**: Real-time performance visualization
- **📈 Historical Data**: Compare results over time
- **🔍 Filtering & Sorting**: Find specific benchmarks quickly
- **📱 Responsive Design**: Works on desktop and mobile
- **💾 Export Results**: Download data in various formats

### Usage
```bash
# Start the web interface
cd docs
python -m http.server 8080
# Open http://localhost:8080 in your browser
```

### Screenshots
- **Dashboard**: Overview of all benchmark categories
- **Detailed Results**: Individual benchmark analysis
- **Comparison View**: Side-by-side performance comparison
- **Hardware Info**: System specifications and capabilities

## 🏗️ Development

### Project Structure
```
PerfBench/
├── Benchmarker/           # Main executable application
│   ├── Program.cs        # Entry point and CLI interface
│   ├── OptionParser.cs   # Command-line argument parsing
│   ├── TableParser.cs    # Result formatting and display
│   └── Arguments.cs      # Command-line argument definitions
├── Benchmarking/          # Core benchmarking engine
│   ├── Arithmetic/       # Mathematical operation benchmarks
│   ├── Compression/      # Data compression benchmarks
│   ├── Cryptography/     # Encryption and hashing benchmarks
│   ├── Extension/        # CPU instruction set benchmarks
│   ├── Parsing/          # Data parsing benchmarks
│   └── Results/          # Result storage and management
├── docs/                 # Web interface and documentation
│   ├── index.html        # Main web interface
│   ├── main.js          # Interactive functionality
│   └── *.js             # Additional JavaScript modules
├── .github/              # GitHub workflows and templates
├── build.ps1            # Cross-platform build script
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

## 📈 Performance Results & Examples

### Sample Benchmark Output

Here's what you can expect from a typical benchmark run:

```bash
$ .\benchmarker.exe --benchmark=compression --multithreaded --runs=3

Gathering hardware information...
OS:             Microsoft Windows 11 Pro
Processor:      AMD Ryzen 9 5900X 12-Core Processor
Architecture:   x64
Logical Cores:  24
Physical Cores: 12

Starting Benchmark...
Running the following benchmarks in approx. 00:02:30: compression

████████████████████████████████████████████████████████████████████████████ 100%
Running Benchmark compression on 24 threads 3 times

════════════════════════════════════════════════════════════════════════════════
BENCHMARK RESULTS - COMPRESSION
════════════════════════════════════════════════════════════════════════════════

Single-threaded Results:
┌─────────────┬─────────────┬─────────────┬─────────────┬─────────────┬─────────────┐
│ Benchmark   │ Score       │ Throughput  │ Time (ms)   │ Category    │ Description │
├─────────────┼─────────────┼─────────────┼─────────────┼─────────────┼─────────────┤
│ ZIP         │ 45,200      │ 90.4 MB/s   │ 5,000       │ Compression │ ZIP Archive │
│ GZip        │ 52,800      │ 105.6 MB/s  │ 5,000       │ Compression │ GZip Stream │
│ BZip2       │ 18,500      │ 37.0 MB/s   │ 5,000       │ Compression │ BZip2 Block │
│ Deflate     │ 48,600      │ 97.2 MB/s   │ 5,000       │ Compression │ Deflate     │
└─────────────┴─────────────┴─────────────┴─────────────┴─────────────┴─────────────┘

Multi-threaded Results (24 threads):
┌─────────────┬─────────────┬─────────────┬─────────────┬─────────────┬─────────────┐
│ Benchmark   │ Score       │ Throughput  │ Time (ms)   │ Category    │ Description │
├─────────────┼─────────────┼─────────────┼─────────────┼─────────────┼─────────────┤
│ ZIP         │ 1,084,800   │ 2.17 GB/s   │ 5,000       │ Compression │ ZIP Archive │
│ GZip        │ 1,267,200   │ 2.53 GB/s   │ 5,000       │ Compression │ GZip Stream │
│ BZip2       │ 444,000     │ 888 MB/s    │ 5,000       │ Compression │ BZip2 Block │
│ Deflate     │ 1,166,400   │ 2.33 GB/s   │ 5,000       │ Compression │ Deflate     │
└─────────────┴─────────────┴─────────────┴─────────────┴─────────────┴─────────────┘

Performance Summary:
- Total execution time: 2 minutes 30 seconds
- Average single-threaded score: 41,275
- Average multi-threaded score: 990,600
- Threading efficiency: 24.0x speedup
- Memory usage: 2.1 GB peak
```

### Performance Reference Systems

The benchmark includes reference points for various systems:

#### High-End Desktop (AMD Ryzen 9 5900X)
- **CPU**: AMD Ryzen 9 5900X 12-Core Processor
- **RAM**: 32 GB DDR4-3200 CL16
- **Motherboard**: ASUS Crosshair VIII Hero
- **Expected Scores**: 
  - Arithmetic: ~1.2M (single), ~28M (multi)
  - Compression: ~45K (single), ~1M (multi)
  - AVX: ~2.5M (single), ~60M (multi)

#### Mid-Range Desktop (Intel i7-12700K)
- **CPU**: Intel Core i7-12700K 12-Core Processor
- **RAM**: 16 GB DDR4-3200 CL16
- **Expected Scores**:
  - Arithmetic: ~1.1M (single), ~26M (multi)
  - Compression: ~42K (single), ~950K (multi)

#### Budget System (AMD Ryzen 5 5600X)
- **CPU**: AMD Ryzen 5 5600X 6-Core Processor
- **RAM**: 16 GB DDR4-3200 CL16
- **Expected Scores**:
  - Arithmetic: ~800K (single), ~14M (multi)
  - Compression: ~35K (single), ~500K (multi)

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

## ❓ Frequently Asked Questions

### General Questions

**Q: What makes PerfBench different from other CPU benchmarks?**
A: PerfBench provides comprehensive testing across multiple categories (arithmetic, compression, cryptography, instruction sets) with detailed throughput measurements, cross-platform support, and a modern web interface for result visualization.

**Q: How accurate are the benchmark results?**
A: PerfBench runs multiple iterations by default and provides statistical analysis. Results are highly accurate for relative performance comparisons, though absolute scores may vary based on system configuration and thermal throttling.

**Q: Can I run benchmarks on low-memory systems?**
A: Yes! Use the `--memory-efficient` flag to reduce memory usage. This mode uses smaller data sets while maintaining benchmark validity.

### Performance Questions

**Q: Why are my scores different from the reference systems?**
A: Performance varies based on CPU architecture, clock speeds, memory configuration, thermal conditions, and background processes. Focus on relative performance rather than absolute scores.

**Q: Should I close other applications while benchmarking?**
A: Yes, for the most accurate results, close unnecessary applications to minimize background CPU usage and memory pressure.

**Q: How long do benchmarks take to complete?**
A: Individual benchmarks take 5-10 seconds each. Full suite runs typically complete in 2-5 minutes depending on your system and configuration.

### Technical Questions

**Q: What .NET version do I need?**
A: PerfBench requires .NET 8.0 or later. The application is self-contained and includes all necessary dependencies.

**Q: Can I run this on ARM processors?**
A: Yes! PerfBench supports ARM64 on Windows, Linux, and macOS. Some instruction set benchmarks may not be available on ARM.

**Q: How do I interpret the throughput measurements?**
A: Throughput shows data processed per second. Higher is better. The measurements help identify bottlenecks in data processing tasks.

## 🔧 Troubleshooting

### Common Issues

**Issue: "Command not found" error**
```bash
# Solution: Ensure you're in the correct directory
cd PerfBench/Benchmarker/bin/Release/net8.0
./benchmarker.exe --help
```

**Issue: Low performance scores**
```bash
# Check for thermal throttling
# Close background applications
# Ensure adequate cooling
# Run with --memory-efficient if low on RAM
```

**Issue: Progress bar not displaying**
```bash
# This is normal when output is redirected
# Use --no-progress to disable progress bars
./benchmarker.exe --benchmark=arithmetic --no-progress
```

**Issue: Out of memory errors**
```bash
# Use memory-efficient mode
./benchmarker.exe --benchmark=compression --memory-efficient
# Or reduce thread count
./benchmarker.exe --benchmark=compression --threads=2
```

### Performance Optimization

**For Maximum Performance:**
1. Close all unnecessary applications
2. Set Windows power plan to "High Performance"
3. Disable Windows Defender real-time scanning temporarily
4. Ensure adequate cooling and power supply
5. Use `--multithreaded` for multi-core systems

**For Consistent Results:**
1. Run benchmarks multiple times with `--runs=5`
2. Wait for system to reach thermal equilibrium
3. Use the same system configuration each time
4. Avoid running during system updates

## 🔄 Changelog

See [CHANGELOG.md](CHANGELOG.md) for a detailed list of changes and version history.

## 📞 Support & Community

- **🐛 Bug Reports**: [GitHub Issues](https://github.com/Tuhin-SnapD/PerfBench/issues)
- **💬 Discussions**: [GitHub Discussions](https://github.com/Tuhin-SnapD/PerfBench/discussions)
- **📚 Documentation**: [Wiki](https://github.com/Tuhin-SnapD/PerfBench/wiki)
- **💡 Feature Requests**: Use the feature request template

---

**Made with ❤️ for the performance testing community**

*PerfBench - Where Performance Meets Precision*
