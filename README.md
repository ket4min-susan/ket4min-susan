### `ket4min-susan` — Protocol, Binary & Audio DSP Surgeon

Independent systems engineer and protocol security researcher focusing on state-machine invariants, on-chain forensics, and zero-disk acoustic signal processing.

---

#### 1. Protocol & Smart Contract State-Machine Audits (`Rust` · `Solidity` · `Go`)

- **Tari L1, Bulletproofs+ & Ootle L2 (`tari-project/tari`, `tari-project/tari-ootle`, `tari-project/tari-crypto`, `tari-project/bulletproofs-plus`)**
  - **Call-Scope Capability Isolation (`tari-ootle#3231`):** Enforced current call-scope membership in `WorkingState::check_all_substates_known` and `RuntimeInterfaceImpl::validate_return_value`; purged consumed buckets, dropped proofs, and used address allocations across ancestor scopes; bounded WASM CBOR return-value depth by `MAX_CBOR_NESTING_DEPTH`.
  - **Cryptographic Curve & Transcript Invariants (`tari-crypto#256`, `#257`, `#258`, `bulletproofs-plus#152`, `#154`, `triptych#116`, `tari_utilities#81`, `#82`):** Enforced canonical curve point decompression (`CompressedCommitment::from_canonical_bytes_validated`), domain-separated ComSig signature challenges and `finalize_into_reset` tags (`#258`), `AggregatedGensIter` `n=0` / `PedersenGens::commit` base vector bounds (`#154`), rejected identity/duplicate generators and identity linking tags in `triptych` (`#116`), and preserved in-place fixed-length `SafeArray` zeroization (`#82`).
  - **Base Node Canonical Sync (`tari#8212`, `#8214`):** Enforced canonical chain header continuity and full kernel/input/output equality in `BlockBodyPartialValidator`.
  - **wTARI Bridge Contracts & Subgraph (`wxtm-bridge-contracts#52`, `#53`, `wxtm-bridge-subgraph#15`):** Verified Safe fallback handler storage slots and aligned `wTARIBridge` ABI definitions across Base and Base Sepolia.
  - **Tari Ecosystem Rust/FFI & Host Hardening (`randomx-rs#86`, `tari_vault#1/#2`, `tari-tapplet-lib#1`, `utxo-scanner#1/#2`, `ootle-wallet-cli#11`, `tari-cli#253`, `minotari-cli#165`, `wallet-benchmarks#15`, `tor-hash-password#9`, `tariswap-ui#4`, `monero-address-creator#3`, `tari-connector-button#7`, `tari-tower#35`, `wasm-template#74`):** Eliminated FFI mutable aliasing UB in `randomx-rs`, authenticated encryption key derivation & TLS listener shutdown in `tari_vault`, enforced Lua host sandboxing in `tari-tapplet-lib`, hardened S2K constant-time passphrase hashing in `tor-hash-password`, mnemonic checksum & canonical seed generation in `monero-address-creator`, and non-interactive CLI indexer/transaction state in `ootle-wallet-cli`, `tari-cli`, and `minotari-cli`.

- **Uniswap v4 Lending Hooks & ERC4626 Vaults (`revert-finance/v4lend`)**
  - **ERC4626 Utilization Asymmetry (`#78`):** Clamped `autoLendForceExit` and `autoLendWithdraw` redemptions to `min(vault.maxRedeem(address(this)), shares)` with direct residual share transfer so high vault utilization cannot revert user exits with `ERC4626ExceededMaxRedeem`.
  - **Tick-Delta Arithmetic & Trigger Preservation (`#85`, `#87`, `#89`):** Widened `int24` tick-delta and tolerance arithmetic prior to clamping; preserved surviving `AUTO_RANGE` / `AUTO_LEVERAGE` mode triggers when remint paths fail.

- **Compiler Ownership & Borrow Verification (`limitlessprojects/Go-Hybrid`)**
  - **16/16 Merged Compiler Patches (`#2387`–`#2752`) + Active `#2718`, `#2741`, `#2756`, `#2781`, `#2785`, `#2798`, `#2807`, `#2855`, `#2882`:** Enforced `O8` slot-loan move invariants across closures (`#2798` `HYB-E2010`), pointer type aliases (`#2707`), parallel key writes, loop back-edges (`#2625`), `A5` foreign-escape closure captures (`#2726`), `E11` `try_context` handlers & shadowed `E11`/`E4`/`E6` propagation (`#2752`, `#2882` `HYB-E2011`), receive operands (`#2781`), composite range iterables (`#2785`), `N5` array pointer/partial zero-init lowering (`#2807`), and `E6002`/`E6006` constant-folding & aliased conversion checks (`#2855`) in `hy-check` and `hy-emit`.

---

#### 2. Open-Source Forensics & Low-Level Tooling

- **[`ket4min-susan/otc-taint-permit2-guard`](https://github.com/ket4min-susan/otc-taint-permit2-guard)** [![CI](https://github.com/ket4min-susan/otc-taint-permit2-guard/actions/workflows/ci.yml/badge.svg)](https://github.com/ket4min-susan/otc-taint-permit2-guard/actions/workflows/ci.yml) · [Release `v2.6.11`](https://github.com/ket4min-susan/otc-taint-permit2-guard/releases/tag/v2.6.11) · [GitLab Mirror (`@memwm`)](https://gitlab.com/memwm/otc-taint-permit2-guard) — Sub-second on-chain USDT (`0xe47d6060`) & USDC (`0xfe575a87`) blacklist checker and pre-sign EIP-712 `Permit2` (`PermitSingle` word-5 / `PermitBatch` word-4) & allowance (`0x095ea7b3`) ABI calldata disassembler.
- **[`ket4min-susan/fpcalc-stream-dedup`](https://github.com/ket4min-susan/fpcalc-stream-dedup)** [![CI](https://github.com/ket4min-susan/fpcalc-stream-dedup/actions/workflows/ci.yml/badge.svg)](https://github.com/ket4min-susan/fpcalc-stream-dedup/actions/workflows/ci.yml) · [Release `v1.0.0`](https://github.com/ket4min-susan/fpcalc-stream-dedup/releases/tag/v1.0.0) · [GitLab Mirror (`@memwm`)](https://gitlab.com/memwm/fpcalc-stream-dedup) — Zero-disk Chromaprint / 28-bit synchsafe ID3-aligned dual-32KB acoustic frame deduplicator and promotional watermark stripper backed by SQLite WAL + FTS5.
- **[`ket4min-susan/flapjax-treasury-audits`](https://github.com/ket4min-susan/flapjax-treasury-audits)** [![CI](https://github.com/ket4min-susan/flapjax-treasury-audits/actions/workflows/ci.yml/badge.svg)](https://github.com/ket4min-susan/flapjax-treasury-audits/actions/workflows/ci.yml) · [Release `v1.0.0`](https://github.com/ket4min-susan/flapjax-treasury-audits/releases/tag/v1.0.0) · [GitLab Mirror (`@memwm`)](https://gitlab.com/memwm/flapjax-treasury-audits) — Deterministic BSC receipt cluster forensics (`Q76`, `Q78`, `Q80`) grouped by genesis BNB funder.
- **[`ket4min-susan/nanoaddr-ts`](https://github.com/ket4min-susan/nanoaddr-ts)** [![CI](https://github.com/ket4min-susan/nanoaddr-ts/actions/workflows/ci.yml/badge.svg)](https://github.com/ket4min-susan/nanoaddr-ts/actions/workflows/ci.yml) · [Release `v1.0.0`](https://github.com/ket4min-susan/nanoaddr-ts/releases/tag/v1.0.0) · [GitLab Mirror (`@memwm`)](https://gitlab.com/memwm/nanoaddr-ts) — Zero-dependency TypeScript port of Nano (`XNO`) address codec and `blake2b-40` checksum validator.
- **[`ket4min-susan/agent-bounty-feed-client`](https://github.com/ket4min-susan/agent-bounty-feed-client)** [![CI](https://github.com/ket4min-susan/agent-bounty-feed-client/actions/workflows/ci.yml/badge.svg)](https://github.com/ket4min-susan/agent-bounty-feed-client/actions/workflows/ci.yml) · [Release `v1.0.0`](https://github.com/ket4min-susan/agent-bounty-feed-client/releases/tag/v1.0.0) · [GitLab Mirror (`@memwm`)](https://gitlab.com/memwm/agent-bounty-feed-client) — Zero-dependency Python MCP Streamable HTTP & `x402` settlement client.
- **[Public Technical Gist (`8128bd4162b53406f7c55203b2b4afc8`)](https://gist.github.com/ket4min-susan/8128bd4162b53406f7c55203b2b4afc8)** — On-Chain Taint Propagation, Permit2 Calldata Forensics & Verified Mirror Index.

---

#### 3. Contact & Channels
- **X / Twitter:** [`@ket4min141`](https://x.com/ket4min141)
- **GitHub / GitLab:** [`ket4min-susan`](https://github.com/ket4min-susan) / [`@memwm`](https://gitlab.com/memwm) (`memwmain@gmail.com`)

---

![State-Machine Invariant Verification](./assets/state_machine_cfg.png)
