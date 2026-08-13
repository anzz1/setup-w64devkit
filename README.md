# Setup w64devkit (GitHub Action)

Install and configure [w64devkit](https://github.com/skeeto/w64devkit) for MinGW builds on GitHub Actions.

## ⚠️ Requirements

This action **only works on Windows runners**.

## 🚀 Usage

```yaml
jobs:
  build:
    runs-on: windows-latest

    steps:
      - uses: actions/checkout@v5

      - name: Set up w64devkit
      - uses: anzz1/setup-w64devkit@v1
        with:
          platform: x64

      - name: Build
      - run: |
          %CC% app.c -O2 -o app.exe
```

## ⚙️ Inputs

| Input     | Value  | Description
| --------- | ------ | -----------
| platform  | x64    | Install the x86_64 toolchain.
|           | x86    | Install the i686 toolchain.
| version   | latest | Install the latest version (default).
|           | x.x.x  | Install the specified version.
