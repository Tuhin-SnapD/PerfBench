# Contributing to BenchmarkerPDC

Thank you for your interest in contributing to BenchmarkerPDC! This document provides guidelines and information for contributors.

## 🤝 How to Contribute

### Reporting Issues

Before creating an issue, please:
1. Check if the issue already exists
2. Use the issue templates provided
3. Include system information (OS, .NET version, hardware specs)
4. Provide steps to reproduce the issue

### Suggesting Enhancements

We welcome feature requests! Please:
1. Check existing issues and discussions first
2. Provide a clear description of the proposed feature
3. Explain the use case and potential benefits
4. Consider implementation complexity

## 🛠️ Development Setup

### Prerequisites

- .NET 8.0 SDK or later
- Visual Studio 2022 or VS Code
- Git
- PowerShell (Windows) or Bash (Linux/macOS)

### Getting Started

1. **Fork the repository**
   ```bash
   git clone https://github.com/yourusername/BenchmarkerPDC.git
   cd BenchmarkerPDC
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Set up the development environment**
   ```bash
   dotnet restore
   dotnet build
   ```

4. **Run tests**
   ```bash
   dotnet test
   ```

## 📝 Code Style Guidelines

### C# Coding Standards

- Follow Microsoft C# coding conventions
- Use meaningful variable and method names
- Add XML documentation for public APIs
- Keep methods focused and small
- Use async/await for I/O operations

### Example Code Style

```csharp
/// <summary>
/// Executes a benchmark with the specified options.
/// </summary>
/// <param name="options">The benchmark execution options.</param>
/// <returns>The benchmark results.</returns>
public async Task<BenchmarkResult> ExecuteBenchmarkAsync(BenchmarkOptions options)
{
    // Implementation here
}
```

### File Organization

- One class per file
- Use namespaces that match folder structure
- Group related functionality together
- Keep files under 500 lines when possible

## 🧪 Testing Guidelines

### Writing Tests

- Write unit tests for new functionality
- Test edge cases and error conditions
- Use descriptive test names
- Follow the AAA pattern (Arrange, Act, Assert)

### Test Structure

```csharp
[Test]
public void Benchmark_WithValidOptions_ReturnsExpectedResult()
{
    // Arrange
    var options = new BenchmarkOptions();
    var benchmark = new TestBenchmark();
    
    // Act
    var result = benchmark.Run(options);
    
    // Assert
    Assert.That(result, Is.Not.Null);
    Assert.That(result.Score, Is.GreaterThan(0));
}
```

## 🚀 Adding New Benchmarks

### Creating a New Benchmark

1. **Create the benchmark class**
   ```csharp
   public class MyCustomBenchmark : Benchmark
   {
       public override string GetName() => "my-custom";
       
       public override string GetDescription() => "My custom benchmark";
       
       public override ulong Run(CancellationToken cancellationToken)
       {
           // Implementation
       }
   }
   ```

2. **Add to the benchmark discovery system**
3. **Create unit tests**
4. **Update documentation**

### Benchmark Categories

- **Arithmetic**: Basic mathematical operations
- **Compression**: Data compression algorithms
- **Cryptography**: Encryption and hashing
- **Extensions**: CPU instruction set extensions
- **Parsing**: Data format parsing
- **Memory**: Memory access patterns

## 📚 Documentation

### Code Documentation

- Add XML documentation for public APIs
- Include parameter descriptions and return values
- Document exceptions that may be thrown
- Provide usage examples where helpful

### README Updates

- Update feature lists when adding new benchmarks
- Add new command-line options to usage examples
- Update installation instructions if needed
- Include new dependencies in prerequisites

## 🔄 Pull Request Process

### Before Submitting

1. **Run all tests**
   ```bash
   dotnet test
   ```

2. **Build in Release mode**
   ```bash
   dotnet build -c Release
   ```

3. **Check code style**
   - Use your IDE's formatting tools
   - Ensure consistent naming conventions

4. **Update documentation**
   - Update README if needed
   - Add XML documentation for new APIs
   - Update changelog for significant changes

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests pass
- [ ] Manual testing completed
- [ ] Performance impact assessed

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No breaking changes (or clearly documented)
```

## 🏷️ Commit Message Guidelines

### Format
```
type(scope): description

[optional body]

[optional footer]
```

### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Examples
```
feat(benchmark): add AVX-512 support
fix(compression): resolve memory leak in BZip2
docs(readme): update installation instructions
```

## 🐛 Bug Reports

### Required Information

- **OS and Version**: Windows 11, Ubuntu 22.04, etc.
- **.NET Version**: `dotnet --version`
- **Hardware**: CPU, RAM, storage type
- **Steps to Reproduce**: Detailed steps
- **Expected Behavior**: What should happen
- **Actual Behavior**: What actually happens
- **Logs**: Any error messages or logs

### Bug Report Template

```markdown
**Describe the bug**
A clear description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Run command '...'
2. See error

**Expected behavior**
What you expected to happen.

**System Information**
- OS: [e.g. Windows 11]
- .NET Version: [e.g. 8.0.0]
- Hardware: [e.g. Intel i7-12700K, 32GB RAM]

**Additional context**
Any other relevant information.
```

## 🎯 Feature Requests

### Required Information

- **Use Case**: Why is this feature needed?
- **Proposed Solution**: How should it work?
- **Alternatives**: Other approaches considered
- **Additional Context**: Screenshots, mockups, etc.

## 📞 Getting Help

- **GitHub Discussions**: For questions and general discussion
- **GitHub Issues**: For bug reports and feature requests
- **Code Review**: All PRs will be reviewed by maintainers

## 🏆 Recognition

Contributors will be recognized in:
- CONTRIBUTORS.md file
- Release notes for significant contributions
- GitHub contributor graphs

Thank you for contributing to BenchmarkerPDC! 🚀
