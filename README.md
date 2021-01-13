## Goal

1. Diff two IR files and highlight the nontrivial differences

    - Ignore temporary variable naming differences
    - Ignore reordering of basic blocks
    - Other differences not related to the semantics 

2. Find the cause (transforms) of any performance change
3. Use the differences to predict performance change
4. Use performane change to determine the necessity of a code change (critic
   and remedy)

## Prior Work

### Existing ways to diff LLVM IR

- llvm-diff
- llvm-canon (under development)
- Update test checks
  [script](https://github.com/llvm/llvm-project/blob/main/llvm/utils/update_test_checks.py)

### Existing ways to find the cause

- [Remarks](https://llvm.org/docs/Remarks.html) and
  [opt-viewer](https://github.com/llvm/llvm-project/tree/main/llvm/tools/opt-viewer)

## High Level Ideas

- Try all the existing ways using the motivating example from Rust project and
  see what is missing
- Use PDG/CFG to facilitate the diff
- Use CPF outside of automatic parallelization
