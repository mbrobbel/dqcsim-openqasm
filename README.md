# dqcsim-openqasm
An [OpenQASM 2.0](https://arxiv.org/abs/1707.03429) frontend plugin for [DQCsim](https://github.com/mbrobbel/dqcsim).

## Usage

### Requirements

- [Rust](https://rustup.rs/)
- [DQCsim](https://github.com/mbrobbel/dqcsim)

### Install

```bash
cargo install dqcsim-openqasm
```

### Update/Re-install

```bash
cargo install --force dqcsim-openqasm
```

### Uninstall

```bash
cargo uninstall dqcsim-openqasm
```

### Run

This plugin enables running `.qasm` files directly e.g.

```bash
dqcsim test.qasm null
```

## Notes

- Include statements are resolved relative to the current working directory and there are no automatic includes or additional gate definitions. `.qasm` files including other files e.g. `include "qelib1.inc";` have to provide these files.
- `barrier` instructions are skipped by default. To enable passing `barrier` instructions in the gatestream set the `DQCSIM_OPENQASM_BARRIER` environment variable. The `barrier` instruction is encoded as a custom gate named `openqasm.barrier` with the target qubits set accordingly.
