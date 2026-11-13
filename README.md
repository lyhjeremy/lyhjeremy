<a href="https://lyhjeremy.com/"><img src="assets/banner.png" alt="Jeremy Lee, AI engineer, Los Angeles, open to relocation. LLM systems on Claude and MCP, each with a frozen eval set, a baseline, and the cost and latency of every answer. Drawing of the Berlin Marathon course, run in 2:48." width="100%"></a>

I build LLM systems and the evals that show whether they work. Most recently I led a natural-language analytics platform on Claude and MCP at Kandu (health tech), from proposal to production. Before that I was a data scientist at InstaAgent (Y Combinator), and for nine years co-founder and Chief Strategy Officer of an education company that grew enrollment 5.2 times. MSBA at UCLA Anderson, December 2026 (GPA 3.92).

**Looking for:** AI engineer and applied ML roles. Based in Los Angeles, open to relocation.

**[lyhjeremy.com](https://lyhjeremy.com/)** (all 37 projects) · **[Resume (PDF)](https://lyhjeremy.com/assets/Jeremy-Lee-Resume-AI-Engineer.pdf)** · [LinkedIn](https://www.linkedin.com/in/lyhjeremy/) · [lyhjeremy@gmail.com](mailto:lyhjeremy@gmail.com)

## Start here

- **[Menu Decoder](https://github.com/lyhjeremy/menu-decoder)**: a 1.5B model I fine-tuned to tag 14 allergens, behind two guard layers that can add a warning but never remove one (an ingredient lexicon, then a Claude Haiku second opinion). On 60 adversarial dishes frozen before the run, hidden allergens missed went from 22 to 0; held-out false-safe calls from 7.3% to 0.8%, at $0.18 per 1,000 dishes. [Write-up](https://lyhjeremy.github.io/menu-decoder/overview/)
- **[Marathon strategy coach](https://github.com/lyhjeremy/marathon-strategy-rag)**: Claude answers with my pace and heat models as tools, also served over MCP. On 42 numeric targets frozen before any run: tools 42, retrieval 21, bare model 14. Since then: a 15-case red-team set, reruns for variance, and a step-by-step trace replay. [Write-up](https://lyhjeremy.github.io/marathon-strategy-rag/overview/)
- **[Podcastify](https://github.com/lyhjeremy/podcastify)**: a whole book becomes a two-host episode where every claim cites its source sentences. Its fact-checkers were tested on 56 lines broken on purpose: Opus caught all 56, my pipeline's Sonnet checker 44 to 49, a three-judge vote 52. [Write-up](https://lyhjeremy.github.io/podcastify/overview/)
- **[When Can I Retire?](https://github.com/lyhjeremy/fire-retirement-simulator)**: ask in plain English; Claude fills a validated scenario, my engine on 152 years of market data does every calculation, and any number the engine did not produce is rejected. 28 of 30 frozen questions right; the bare model matched the engine 3 times in 20. [Write-up](https://lyhjeremy.github.io/fire-retirement-simulator/overview/)
- **[Receipt Auditor](https://github.com/lyhjeremy/receipt-auditor)**: a 1.5B Qwen model fine-tuned on my laptop (LoRA) sorts line items at 90.5% against 80.0% for Claude zero-shot, in 0.19 s per item instead of 3.6 s. [Write-up](https://lyhjeremy.github.io/receipt-auditor/overview/)

## How I test AI systems

Every AI project has a test set frozen before the first run, a baseline it has to beat, measured cost and latency, and its main failure written down. No result below rests on human labels; where those are the next step, the repo has a labeling sheet.

| Project | Result vs baseline | Cost per task | Latency (median) | Main failure |
|---|---|---|---|---|
| [Strategy coach](https://lyhjeremy.github.io/marathon-strategy-rag/overview/) | 42 of 42 vs 21 (RAG), 14 (bare); 0 of 15 red-team attacks worked | $0.017 | 8.4 s | 42 of 42 is close to circular |
| [Menu Decoder](https://lyhjeremy.github.io/menu-decoder/overview/) | False-safe 7.3% to 0.8%; adversarial misses 22 to 0 | $0.00018 (guard) | 2.8 s local | Over-warning up to 27% |
| [Podcastify judges](https://lyhjeremy.github.io/podcastify/overview/) | Opus 56 of 56 broken lines; Sonnet 44 to 49 | $0.0025 per line | 10.6 s per batch | Sonnet forgives flipped negations |
| [Training agent](https://lyhjeremy.github.io/marathon-training-agent/overview/) | Schema plans 6 of 6 pass vs 1 of 6; wrong lengths 0 vs 3 | $0.10 | 47 s | Drafts break the note limit |
| [Retirement agent](https://lyhjeremy.github.io/fire-retirement-simulator/overview/) | 28 of 30; headline 19 of 20 vs 3 of 20 bare | $0.0087 | 7.7 s | A reply dropped the what-if result |
| [Itinerary checker](https://lyhjeremy.github.io/connection-odds/overview/) | 30 of 30 parsed; bare model 9.4 points off | $0.0068 | 6.3 s | "No chance" for "no figure" |
| [Wine RAG](https://lyhjeremy.github.io/wine-sommelier-rag/overview/) | Limit-breaking results 77.5% to 0; nDCG@10 0.76 vs 0.59 | $0.053 extraction | 2.4 s | Word filter drops unoaked wines |
| [Pairing agent](https://lyhjeremy.github.io/wine-pairing-agent/overview/) | Critique passes 10 of 10 vs 0; grapes 10 vs 3 | $0.49 | 34 s | Second judge agrees 6 of 10 |
| [Receipt Auditor](https://lyhjeremy.github.io/receipt-auditor/overview/) | LoRA 90.5% vs Claude 80.0% | $0 vs $0.003 | 0.19 s vs 3.6 s | Labels that split two ways |
| [One in a Hundred](https://lyhjeremy.github.io/one-in-a-hundred/overview/) | In-browser parser 66 vs 58 of 104 new; 172 vs 181 of 200 frozen | $0 | 4.9 ms | Lost cue words before embedding |

<sub>Cost is the API-equivalent price reported by the Claude CLI; local timings on an Apple M4. Each write-up has the eval files and the scripts that produced them.</sub>

**Methods across these:** agents with tool use over my own models, MCP servers (four repos), schema-validated structured output with repair, LLM judges scored against known answers and each other (Cohen's kappa), red-team and adversarial sets, models running in the browser (transformers.js, self-hosted), replayable run traces, and a Claude Code plugin. The [matrix on lyhjeremy.com](https://lyhjeremy.com/#methods) shows which project uses which.

## Experience

- **Kandu**, Data Engineer, Jul to Sep 2026: led a natural-language analytics platform on Claude and MCP, and the dbt warehouse under it from 13 post-merger systems (HIPAA, GDPR); record linkage from 75.7% to 97.5%.
- **UCLA Anderson**, Data Analyst and graduate student researcher, Jun to Dec 2026: the Office of Inclusive Excellence's first data pipeline; research on LA's deep-tech cluster and on LLM voice agents in debt recovery (36,000 calls).
- **InstaAgent** (Y Combinator), Data Scientist, Jun 2025 to Mar 2026: LLM content generation for nine clients, cutting production cost by more than 80%; engagement models that lifted engagement 25%.
- **Casual Ace Learning Centre**, Co-founder and Chief Strategy Officer, 2016 to 2025: one location to eight, enrollment up 5.2 times and revenue 6.7 times; shipped the learning platform, LLM tutor included.

## The fine-tuning series

Four photo-to-structured-data apps. Each one pairs an LLM pipeline with a small open model fine-tuned on my laptop (LoRA on Qwen2.5) for the same task, then benchmarks base vs. fine-tuned vs. Claude zero-shot on held-out data.

| App | Task for the fine-tuned model | Fine-tuned | Claude zero-shot | |
|---|---|---|---|---|
| [**Receipt Auditor**](https://github.com/lyhjeremy/receipt-auditor) | Spend category for merchants it has never seen | **90.5%** | 80.0%<sup>1</sup> | [Live](https://lyhjeremy.github.io/receipt-auditor/) · [Write-up](https://lyhjeremy.github.io/receipt-auditor/overview/) |
| [**Cellar Scanner**](https://github.com/lyhjeremy/cellar-scanner) | Grape variety from a blind tasting note (1.5B model) | **27.7%** top-1 | 23.0%<sup>2</sup> | [Live](https://lyhjeremy.github.io/cellar-scanner/) · [Write-up](https://lyhjeremy.github.io/cellar-scanner/overview/) |
| [**Menu Decoder**](https://github.com/lyhjeremy/menu-decoder) | Cuisine and 14-allergen tags from a bare dish name | **99.3%** cuisine with no schema in the prompt; 69.3% allergen recall | 79.3% allergen recall<sup>3</sup> | [Live](https://lyhjeremy.github.io/menu-decoder/) · [Write-up](https://lyhjeremy.github.io/menu-decoder/overview/) |
| [**Race Day Copilot**](https://github.com/lyhjeremy/race-day-copilot) | Km-by-km pacing plan from a course map, checked by six deterministic rules (3B model) | 95.7% valid plans; **0.0%** pass all six checks | 90.0% valid; 75.7% pass | [Live](https://lyhjeremy.github.io/race-day-copilot/) · [Write-up](https://lyhjeremy.github.io/race-day-copilot/overview/) |

<sub>1. Clean rerun on 2026-10-28: Claude saw only the merchant text and the 12 labels, with tools off. Most of its misses are noisy labels in the test set (hardware and cables marked other). The first run scored 56.0% with a leaked category list. 2. Scored on the same 200 notes, the fine-tuned model is right on 55 and Claude on 46 (sign test p = 0.33), so the gap is within noise. 3. Claude needs the full allergen schema in every prompt to get there; the fine-tuned model gets only the dish name.</sub>

## Data stories

Running and wine supply most of the questions: I have run 14 marathons (2:48 in Berlin) and hold WSET Level 3.

- **[Fuel Lockstep](https://lyhjeremy.github.io/fuel-lockstep/)**: Hong Kong's five petrol brands posted the same price on 88% of days from 2020 to 2026, and prices rose 110 times against 33 cuts. Collusion screens against import costs, with Perth and Los Angeles for contrast, plus an [11-page paper](https://lyhjeremy.github.io/fuel-lockstep/paper/fuel-lockstep.pdf).
- **[The Heat Tax](https://lyhjeremy.github.io/marathon-heat-tax/)**: 80 Boston Marathons (1940 to 2019) against ERA5 course weather. Heat costs nothing up to 55°F, then about 0.42% of finish time per °F for the median runner; dew point added nothing. Includes a live race-day forecast, and says plainly that the model did not beat a flat guess on its 2015 to 2019 holdout.
- **[Wine Score Inflation](https://lyhjeremy.github.io/wine-score-inflation/)**: the 100-point scale works like an 8-point one. Nothing in about 120k unique reviews scores below 80, and 85% land between 84 and 92.
- **[Vintage Heat](https://lyhjeremy.github.io/vintage-heat/)**: growing-season weather for 55 wine regions joined to 55,597 unique reviews. A season 1 °C warmer than normal moved scores by 0.24 points in cool regions and 0.08 in warm ones, and the placebo and trend checks weaken even that.
- **[Fame Half-Life](https://lyhjeremy.github.io/fame-half-life/)**: daily Wikipedia views around 1,905 deaths and 178 major awards. Half the extra attention a death brings is gone about two days after the peak, and a year later the page still draws 1.08 times its old traffic. A two-phase decay fits 75% of events best, a share the page tests against simulated curves.
- **[The Negative-Split Myth](https://lyhjeremy.github.io/marathon-negative-split-myth/)**: of 31,912 Boston 2014 finishers, 2.5% ran the faster second half coaches recommend, and the median runner slowed 14%. Across eight Boston years the share runs from 2.4% to 10.8%; 2014 had the hardest fade.
- **[Are Song Lyrics Getting Simpler?](https://lyhjeremy.github.io/lyrics-complexity-over-time/)**: 50 years of Billboard hits doubled in length and got more repetitive, but the vocabulary did not shrink.
- **[Scoring-Table Fairness](https://lyhjeremy.github.io/athletics-scoring-fairness/)**: Kruskal-Wallis tests on 6,400 elite marks. The best performers in some events score 68 points higher than in others.

<details>
<summary><strong>More projects</strong>, grouped by theme</summary>

#### Generative AI and agents
- [Marathon Strategy RAG](https://github.com/lyhjeremy/marathon-strategy-rag): a tool-calling coach that runs my Boston pace and heat models instead of guessing numbers, with an MCP server for Claude Desktop and Claude Code. On a frozen 43-question gold set it got 42 of 42 numeric values within tolerance (plain RAG 21, bare model 14) and left an unsourced number in 3 of 43 answers (RAG 28, bare 43). [Live](https://lyhjeremy.github.io/marathon-strategy-rag/)
- [Marathon Training Agent](https://github.com/lyhjeremy/marathon-training-agent): a LangGraph planner rebuilt on schema-validated plans with code checks and up to two repairs; 6 of 6 frozen runners pass against 1 of 6 for its old critique loop. MCP server for the checks. [Live](https://lyhjeremy.github.io/marathon-training-agent/)
- [Wine Pairing Agent](https://github.com/lyhjeremy/wine-pairing-agent): a LangGraph agent that reasons from pairing principles to a style, searches 30,000 indexed reviews as a tool, and critiques its pick against a schema-checked rubric; every run replays node by node. [Live](https://lyhjeremy.github.io/wine-pairing-agent/)

#### Running and sports analytics
- [Performance Continuum](https://github.com/lyhjeremy/marathon-performance-continuum): distribution fitting and extreme-value theory on 31,842 finishers, and how far the world record sits beyond them. [Live](https://lyhjeremy.github.io/marathon-performance-continuum/)
- [National Strength Profiles](https://github.com/lyhjeremy/national-strength-profiles): k-means and PCA on 43 nations across five disciplines; five archetypes. [Live](https://lyhjeremy.github.io/national-strength-profiles/)
- [Hitting the Wall](https://github.com/lyhjeremy/marathon-pacing-decay): a finish-time and wall-risk predictor trained on 176,059 Boston finishers (2014 to 2023) with conformal intervals, tested on the unseen 2024 race: 7.9 min typical miss at halfway against 18.1 for even pace. Live split card on the write-up. [Live](https://lyhjeremy.github.io/marathon-pacing-decay/)
- [Boston BQ Fairness](https://github.com/lyhjeremy/boston-marathon-qualifying-fairness): are Boston qualifying times equally hard across age and gender groups? [Live](https://lyhjeremy.github.io/boston-marathon-qualifying-fairness/)
- [Marathon Majors Course Difficulty](https://github.com/lyhjeremy/marathon-majors-course-difficulty): three methods for ranking course difficulty across the six Majors, tested on simulated races with planted course penalties; the paired method recovers each within 7.3 s. [Live](https://lyhjeremy.github.io/marathon-majors-course-difficulty/)
- [Marathon Shoe Revolution](https://github.com/lyhjeremy/marathon-shoe-revolution-decomposition): how much of the recent drop in marathon times is the shoes. [Live](https://lyhjeremy.github.io/marathon-shoe-revolution-decomposition/)

#### Language and NLP
- [Mandarin Learning Reader](https://github.com/lyhjeremy/mandarin-learning-reader): a tutor built from any Chinese EPUB, with pinyin over every character, read-aloud and offline pronunciation grading. [Live](https://lyhjeremy.github.io/mandarin-learning-reader/)
- [EPUB Reading-Level Analyzer](https://github.com/lyhjeremy/epub-reading-level-analyzer): grade level, vocabulary richness and word-coverage curve for any EPUB, entirely in the browser. [Live](https://lyhjeremy.github.io/epub-reading-level-analyzer/)
- [Love Island Lexical Analysis](https://github.com/lyhjeremy/love-island-lexical-analysis): 61% of everything said is the top 100 words; about 1,250 words cover 95%. [Live](https://lyhjeremy.github.io/love-island-lexical-analysis/)
- [Podcastify](https://github.com/lyhjeremy/podcastify): turns a whole book or article into a two-host episode through `claude -p`. Every claim line cites its source sentences and is checked before it is voiced. Across four public-domain sources it covered 7.4 of 12 frozen key points against 4.4 for the rule-based mode. [Live](https://lyhjeremy.github.io/podcastify/)
- [EPUB to Audiobook](https://github.com/lyhjeremy/epub-to-audiobook): a desktop app for read-along audiobooks in English, Mandarin and Cantonese. [Live](https://lyhjeremy.github.io/epub-to-audiobook/)

#### Tools and finance
- [When Can I Retire?](https://github.com/lyhjeremy/fire-retirement-simulator): replays a retirement plan through every start year of US market history since 1871 (Shiller data), or a block bootstrap of it, with a stock/bond mix, guardrail spending and a solver for the smallest change that reaches 90%. Checked against the Trinity study and a 1946 to 1993 holdout. [Live](https://lyhjeremy.github.io/fire-retirement-simulator/)
- [Leave Time Optimizer](https://github.com/lyhjeremy/leave-time-optimizer): when to leave to arrive on time, from the Google Maps API. [Live](https://lyhjeremy.github.io/leave-time-optimizer/)
- [Connection Odds](https://github.com/lyhjeremy/connection-odds): how often a US connection fails, built from 21 million flights at the 30 busiest US hubs. A 45-minute layover (45 to 49 minutes) missed 17% of the time; the lookup gives the layover you need for 95%, and an agent reads a pasted itinerary and scores each connection with the model (also an MCP server). [Live](https://lyhjeremy.github.io/connection-odds/)
- [downtime-cli](https://github.com/lyhjeremy/downtime-cli): a zero-dependency npm CLI that fills a long build or test run with terminal trivia, and a Claude Code plugin whose hooks open a companion pane while a tool call or subagent works. [Live](https://lyhjeremy.github.io/downtime-cli)

</details>

## Toolkit

- **LLM systems:** Claude and MCP, tool use, agents (LangGraph), RAG (BM25, dense, reranking), LoRA fine-tuning, evals with frozen gold sets and LLM judges, grounding checks
- **Engineering:** Python, TypeScript, SQL, FastAPI, React, Git, CI/CD, GCP, Claude Code
- **Modeling:** scikit-learn, PyTorch, XGBoost; survival analysis, causal inference, time series, A/B testing; Gurobi optimization
- **Data:** Snowflake, dbt, Airflow, Spark; apps on Render, Vercel and GitHub Pages

## Education

MSBA, UCLA Anderson School of Management (Dec 2026, GPA 3.92) · graduate analytics coursework, Georgia Tech · BBA in Accounting and Finance, University of Hong Kong

<sub>Design and copy across these repos follow [these standards](DESIGN_STANDARDS.md).</sub>
