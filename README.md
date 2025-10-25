# My Projects

Here are some projects I've worked on in software development and security research.

## Table of Contents

- [Fuzzing and Vulnerability Analysis of libpng](#fuzzing-and-vulnerability-analysis-of-libpng)

---

## Fuzzing and Vulnerability Analysis of libpng

Security research project using Google's OSS-Fuzz framework to test the libpng library through coverage-guided fuzzing. We analyzed how different fuzzing approaches affect code coverage and developed custom fuzzers to reach previously untested code paths.

**What we did:**

- Compared fuzzing effectiveness with and without seed corpus (17% coverage difference)
- Built custom fuzzers to test read and write operations separately
- Achieved coverage on 1,270+ lines that were previously untested
- Developed proof-of-concept exploit for CVE-2014-9495 (heap buffer overflow)

**Results:**

- Seed corpus provided 17% better line coverage compared to starting from scratch
- New write fuzzer covered 30-50% of encoding functions (previously at 0%)
- Enhanced read fuzzer added 1% coverage through better API call combinations
- Successfully triggered heap buffer overflow using AddressSanitizer

**Technologies:** OSS-Fuzz, LibFuzzer, LLVM Coverage, AddressSanitizer, C/C++  
**Type:** Group research project

**[View Full Repository](https://github.com/Enessar/LibPNG_OSS-Fuzz)**

---
