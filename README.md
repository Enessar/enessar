# My Projects

Here are some projects I've worked on in software development and security research.

## Table of Contents

- [Fuzzing and Vulnerability Analysis of libpng](#fuzzing-and-vulnerability-analysis-of-libpng)
- [SMCompiler: Secure Multiparty Computation Framework](#smcompiler-secure-multiparty-computation-framework)
- [SecretStroll: Privacy-Preserving Location Service](#secretstroll-privacy-preserving-location-service)

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

## SMCompiler: Secure Multiparty Computation Framework

Privacy-preserving computation framework enabling multiple parties to jointly compute functions over private inputs without revealing individual data. Implements additive secret sharing and Beaver Triplet Protocol for secure operations.

**What we did:**

- Implemented additive secret sharing over Mersenne primes with n-party support
- Built Beaver Triplet Protocol for secure multiplication via Trusted Third Party (TTP)
- Designed recursive expression evaluation for arbitrary arithmetic circuits
- Optimized scalar operations to bypass expensive Beaver triples when possible
- Developed friendship compatibility calculator demonstrating real-world SMC use case

**Results:**

- Scalar operations: near-constant time (~0.1ms), minimal communication overhead
- Beaver multiplication: linear scaling with operations and party count
- Performance tested across varying circuit sizes and party counts (2-10 parties)
- Successfully computed private compatibility scores without input leakage

**Security Model:** Honest-but-curious adversaries, protects against n-1 colluding parties

**Technologies:** Python, Secret Sharing, Beaver Triples, Zero-Knowledge Proofs  
**Type:** Group research project (3 members)

**[View Course Materials](https://github.com/spring-epfl/CS-523-public)**  
*Note: Implementation contains solutions and remains private per course policy*

---

## SecretStroll: Privacy-Preserving Location Service

Complete privacy-preserving location service enabling anonymous queries for Points of Interest (POIs) while defending against identity, location, and behavioral tracking. Combines cryptographic authentication, privacy attack analysis, and machine learning-based defenses.

**What we did:**

- **Anonymous Authentication:** Implemented Pointcheval-Sanders signatures with Fiat-Shamir heuristic for non-interactive zero-knowledge proofs, enabling selective disclosure of subscriptions while hiding user identity
- **Privacy Attack Analysis:** Developed three inference attacks on "anonymized" query metadata:
  - Home/work location inference via temporal clustering (9am-5pm work, 10pm-6am home)
  - User interest profiling from POI type frequencies
  - Behavioral pattern extraction from query timestamps
- **Location Obfuscation Defense:** Designed Gaussian noise addition (σ≈200m) that destroyed clustering accuracy while preserving service utility
- **Traffic Fingerprinting:** Collected 2,000 Tor network traces and trained ML classifier on 15+ traffic features to identify queried geographic cells

**Results:**

- ABC performance: credential operations complete in 1.5-11ms with <2KB communication overhead
- Privacy attacks successfully identified home/work locations, dominant interests, and activity patterns
- Location obfuscation reduced clustering to ~1 query per inferred location (vs. high-confidence clusters before)
- Traffic fingerprinting achieved **65% mean accuracy** despite Tor encryption (10-fold CV)

**Key Insights:**

- Cryptographic privacy alone is insufficient—metadata leaks sensitive information
- Simple noise-based defenses can significantly reduce inference accuracy
- Encrypted traffic still reveals location through observable patterns (packet sizes, timing)

**Technologies:** Python, Pointcheval-Sanders Signatures, Tor, Scikit-learn, tcpdump, Pyshark  
**Type:** Group research project (3 members)

**[View Course Materials](https://github.com/spring-epfl/CS-523-public)**  
*Note: Implementation contains solutions and remains private per course policy*

---

*Both projects from EPFL's CS-253: Advanced Topics in Privacy Enhancing Technologies*
