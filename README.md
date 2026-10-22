# JEV fine-tuned Laya checkpoints — research only

**Status: experimental research artifacts. Not trading-ready. Do not use for live or paper trading.** The selection campaign did not qualify any model; no checkpoint was selected, no final test was read, and live qualification is false.

Nine fine-tuned Laya checkpoints from `research-v1` are attached to the [`research-v1` GitHub release](https://github.com/labo45000/jev-tradingbot-research-models/releases/tag/research-v1). Each ZIP contains one `.safetensors` weight file plus its encoder/tokenizer and model configuration files.

## Checkpoints

The repository includes [`SHA256SUMS.txt`](SHA256SUMS.txt) with SHA-256 checksums for all weights.

| Target | Epochs |
| --- | --- |
| 1R | 1, 2, 4 |
| 1.5R | 1, 2, 4 |
| 2R | 1, 2, 4 |

Release asset names use `laya-tp<TARGET>-epoch<EPOCH>.zip` (for example, `laya-tp1.5-epoch2.zip`).

## Evaluation status

- Training produced nine Laya candidates. Selection evaluated 18 candidates across 16 LONG/SHORT threshold pairs each (288 trials).
- No Laya candidate produced a simulated trade at the frozen thresholds. Six additional numeric candidates also produced zero trades. EMA produced at most 11 trades, below the 20-trade minimum; its best observed net/day was negative.
- `selected=null`, `baseline_selected=null`, `final_test_read=false`, `live_qualified=false`.
- Research used a short selection slice and only 34 calibration observations. Historical candle replay used a proxy where order-book/mark data was unavailable.

These results describe this specific campaign only. They do not establish that the model family has no possible edge. Any follow-up research must be a separate campaign with untouched evaluation data.

## Provenance and license

Fine-tuned from [`convaiinnovations/laya`](https://huggingface.co/convaiinnovations/laya), pinned upstream revision `55cf4c4ebb4ebe31b2550e8bdf3bd21b99753851`. The upstream model page identifies its license as Apache-2.0; see [`LICENSE`](LICENSE) and the upstream repository for terms and notices. Training and selection implementation belongs to the private `jev-tradingbot` project.

## Intended use

Research, inspection, and reproducibility work only. These checkpoints are not endorsed for trading, have no demonstrated profitability, and must not be represented as qualified or production-ready models.
