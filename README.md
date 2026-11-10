<div align="center">
  <img src="./assets/luxury_hero_banner.svg" width="100%" alt="ket4min-susan" />
</div>

<br/>

<div align="center">
  <img src="./assets/architecture_matrix.svg" width="100%" alt="Engineering Domains" />
</div>

<br/>

### Selected Upstream Work

| Repository | Subsystem | Patch Summary | PRs |
| :--- | :--- | :--- | :--- |
| **`tari-project/tari-ootle`** | L2 WASM Engine | Call-scope substate isolation, proof cleanup & `MAX_CBOR_NESTING_DEPTH = 32` guard | [`#3231`](https://github.com/tari-project/tari-ootle/pull/3231) |
| **`tari-project/tari-crypto`** | Ristretto255 | Canonical point decompression, `ComSig` domain separation & `SafeArray` zeroization | [`#256`](https://github.com/tari-project/tari-crypto/pull/256) · [`#257`](https://github.com/tari-project/tari-crypto/pull/257) · [`#258`](https://github.com/tari-project/tari-crypto/pull/258) |
| **`tari-project/bulletproofs-plus`** | Range Proofs | Generator vector bounds in `AggregatedGensIter` & identity point rejection in `triptych` | [`#152`](https://github.com/tari-project/bulletproofs-plus/pull/152) · [`#154`](https://github.com/tari-project/bulletproofs-plus/pull/154) · [`#116`](https://github.com/tari-project/triptych/pull/116) |
| **`tari-project/tari`** | Base Node | Header chain continuity across `sync_kernels` / `sync_utxos` & block body validation | [`#8212`](https://github.com/tari-project/tari/pull/8212) · [`#8214`](https://github.com/tari-project/tari/pull/8214) |
| **`revert-finance/v4lend`** | Uniswap v4 Hooks | Clamped `autoLendForceExit` ERC-4626 redemptions (~2.6k gas warm) & `int24` tick math | [`#78`](https://github.com/revert-finance/v4lend/pull/78) · [`#85`](https://github.com/revert-finance/v4lend/pull/85) · [`#87`](https://github.com/revert-finance/v4lend/pull/87) · [`#89`](https://github.com/revert-finance/v4lend/pull/89) |
| **`limitlessprojects/Go-Hybrid`** | `hy-check` Compiler | 25+ patches: `O8` slot-loan loop back-edges, pointer aliases & foreign closure escapes | [`#2625`](https://github.com/limitlessprojects/Go-Hybrid/pull/2625) · [`#2707`](https://github.com/limitlessprojects/Go-Hybrid/pull/2707) · [`#2726`](https://github.com/limitlessprojects/Go-Hybrid/pull/2726) · [`#2752`](https://github.com/limitlessprojects/Go-Hybrid/pull/2752) |

### Repositories

* **[`otc-taint-permit2-guard`](https://github.com/ket4min-susan/otc-taint-permit2-guard)** — On-chain token freeze inspector and pre-sign EIP-712 `Permit2` calldata disassembler.
* **[`fpcalc-stream-dedup`](https://github.com/ket4min-susan/fpcalc-stream-dedup)** — In-memory Chromaprint & ID3v2 acoustic frame deduplicator backed by SQLite WAL.
* **[`TARI.Miner`](https://github.com/ket4min-susan/TARI.Miner)** — NVIDIA CUDA Cuckaroo29 solver and graph trimmer for Tari (`XTM`).
* **[`nanoaddr-ts`](https://github.com/ket4min-susan/nanoaddr-ts)** — Zero-dependency TypeScript `XNO` base32 codec and `blake2b-40` checksum verifier.

<br/>

<div align="center">
  <img src="./assets/contribution_hud.svg" width="100%" alt="Benchmarks" />
</div>
