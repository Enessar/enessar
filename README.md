# 👋 My Projects

Welcome! Here you'll find a collection of projects I've worked on, showcasing my skills in software development, security research, and more.

## 📑 Table of Contents

- [Fuzzing and Vulnerability Analysis of libpng](#fuzzing-and-vulnerability-analysis-of-libpng)

---

## 🔍 Fuzzing and Vulnerability Analysis of libpng

**Security Research | Fuzzing | Vulnerability Exploitation**

A comprehensive security research project exploring coverage-guided fuzzing techniques using Google's OSS-Fuzz framework on the libpng library. This project demonstrates practical application of modern software testing methodologies to discover vulnerabilities and improve code coverage.

### Key Highlights

- 🧪 **Coverage-Guided Fuzzing** with OSS-Fuzz and LibFuzzer
- 📊 **Empirical Analysis** comparing fuzzing with and without seed corpus (+17% coverage improvement)
- 🛠️ **Custom Fuzzer Development** creating new fuzzers to explore untested code paths
- 🚨 **CVE Exploitation** successful proof-of-concept for CVE-2014-9495 (heap buffer overflow)
- 📈 **Novel Coverage** achieved 1,270+ lines of previously untested code

### Results

✅ Demonstrated 17% coverage increase with quality seed corpus  
✅ Developed 2 custom fuzzer variants (enhanced read + new write fuzzer)  
✅ Achieved 30-50% coverage on previously untested write operations  
✅ Successfully exploited historical CVE with AddressSanitizer validation

**Technologies:** OSS-Fuzz • LibFuzzer • LLVM Coverage • AddressSanitizer • C/C++  
**Type:** Group security research project

**[→ View Full Project Repository](https://github.com/Enessar/LibPNG_OSS-Fuzz)**

---
