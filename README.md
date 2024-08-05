name: CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        language: [python, javascript, ruby]

    steps:
    - uses: actions/checkout@v2
    - name: Set up ${{ matrix.language }}
      if: matrix.language == 'python'
      run: echo "Python is active"
    - name: Set up ${{ matrix.language }}
      if: matrix.language == 'javascript'
      run: echo "JavaScript is active"
    - name: Set up ${{ matrix.language }}
      if: matrix.language == 'ruby'
      run: echo "Ruby is active"
