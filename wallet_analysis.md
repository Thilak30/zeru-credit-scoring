
# Wallet Behavior Analysis

This document presents insights into the transaction patterns of wallets that received the highest and lowest ML-based credit scores (on a scale from 0 to 100) from our Compound V2 behavioral modeling.

---

## Top 5 High-Scoring Wallets

| Wallet Address                               | Credit Score | Behavior 
| `0x00000000af5a61acaf76190794e3fdf1289288a1` | **100.00**   | Demonstrates high repay behavior without borrowing. Likely a clean testing or replenishment wallet. Excellent protocol-friendly usage. |
| `0x0035e78d54a1daf93de5b7740ec9864294cd25f8` | **100.00**   | Consistent activity pattern, likely making safe deposits or stable participation. Low-risk behavior.                                   |
| `0x003f6b20bfa4b5cab701960ecf73859cb3c095fc` | **100.00**   | Possibly a passive liquidity provider with clean deposits. Minimal interaction but no suspicious activity.                             |
| `0x003dc32fe920a4aaeed12dc87e145f030aa753f3` | **100.00**   | Balanced transaction history with responsible usage. May be a bot account tuned for optimal lending.                                   |
| `0x003c52a71c887461087154eccced08cb1c5384a5` | **100.00**   | Exhibits protocol-supportive behavior. No signs of exploitative patterns. Very low-risk profile.                                       |

---

## Bottom 5 Low-Scoring Wallets

| Wallet Address                               | Credit Score | Behavior 
| `0x64a8070811567783cf820225a11e5bba213322e9` | **0.00**     | Extremely abnormal repay-to-borrow ratio (possibly inflated or corrupt). Suggests anomalous or bot-like behavior.                      |
| `0xeb97d37bb6cd268ddb25e67cfbb9b3f7468db46c` | **43.04**    | Inconsistent usage patterns. Transactions indicate limited or non-repaying behavior, creating risk.                                    |
| `0xf76cb72ecfa276d8d64a24f54a94554e2da8f712` | **53.91**    | Participates without sufficient collateral behavior. No red flags but also lacks positive engagement indicators.                       |
| `0x95b9f2f528338b0cdb3f14442837b0e7f05dceec` | **82.17**    | Score still high but likely pulled down by irregular transaction patterns. Activity may be infrequent or overly optimized.             |
| `0x2b03088c22ae484ce873f21251a2e6fd0509ea07` | **100.00**   | High score despite being last in bottom 5 — likely due to scoring distribution. Behavior warrants reevaluation for edge-case modeling. |

---

