# FirebaseCocoaPodsTest
A weird problem that if a pass `"GCC_INSTRUMENT_PROGRAM_FLOW_ARCS=YES"` to `$ xcodebuild build test`, test fails

## Bootstrap

```bash
$ pod install
```

## Steps to reproduce

1. Normal way to run tests works fine:

```bash
$ xcodebuild -workspace FirebaseTest.xcworkspace -scheme FirebaseTest clean build test -destination 'platform=iOS Simulator,name=iPhone X' GCC_GENERATE_TEST_COVERAGE_FILES=YES
```

2. If pass `GCC_INSTRUMENT_PROGRAM_FLOW_ARCS=YES` parameter to the command above it fails with errors like `Undefined symbol: _llvm_gcov_init`

```bash
$ xcodebuild -workspace FirebaseTest.xcworkspace -scheme FirebaseTest clean build test -destination 'platform=iOS Simulator,name=iPhone X' GCC_INSTRUMENT_PROGRAM_FLOW_ARCS=YES GCC_GENERATE_TEST_COVERAGE_FILES=YES
```
