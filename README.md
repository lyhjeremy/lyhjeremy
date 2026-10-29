# Jeremy Lee

Data scientist. I build models, the tests that show whether they work, and the apps people open to use them. UCLA Anderson MSBA. Before that I co-founded an education business and, as Chief Strategy Officer, grew it 5.2 times to more than 1,000 students across six centers.

**[lyhjeremy.com](https://lyhjeremy.com/)** has all 37 projects with their charts and screenshots · [LinkedIn](https://www.linkedin.com/in/lyhjeremy/) · [lyhjeremy@gmail.com](mailto:lyhjeremy@gmail.com)

## Selected work

| Project | What it is | Result | |
|---|---|---|---|
| [**SkillCompass**](https://github.com/lyhjeremy/skill-compass) | Two-minute skill checks in 40+ fields. Elo-style ability scoring against items with calibrated difficulty priors, placement routing, live peer percentiles, and three LLM features: resume-gap analysis, a mock-interview agent and a study guide. FastAPI backend. | Full stack running on $0 a month | [Live](https://lyhjeremy.github.io/skill-compass/) · [Write-up](https://lyhjeremy.github.io/skill-compass/overview/) |
| [**Leeway**](https://github.com/lyhjeremy/leeway) | EV trip planner for the battery a car has after five years. Range adjusted for elevation and weather, charger stops under a hard reserve, and a detour budget spent avoiding unprotected left turns and rail crossings. | Logged trips correct its own range estimates | [Live](https://lyhjeremy.github.io/leeway/) · [Write-up](https://lyhjeremy.github.io/leeway/overview/) |
| [**Wine Sommelier RAG**](https://github.com/lyhjeremy/wine-sommelier-rag) | Plain-English wine search over the 30,000 top-scored reviews of a 130k Wine Enthusiast set. Hybrid BM25 and dense retrieval with a cross-encoder reranker; every pick is cited. | Precision and nDCG up about 21% over a dense baseline | [Live](https://lyhjeremy.github.io/wine-sommelier-rag/) · [Write-up](https://lyhjeremy.github.io/wine-sommelier-rag/overview/) |
| [**World-Record Half-Lives**](https://github.com/lyhjeremy/world-record-half-lives) | Survival analysis of 248 track-and-field record reigns, treating standing records as right-censored. Kaplan-Meier and Cox regression. | Median reign about 1.5 years; fall odds for every current record | [Live](https://lyhjeremy.github.io/world-record-half-lives/) · [Write-up](https://lyhjeremy.github.io/world-record-half-lives/overview/) |
| [**One in a Hundred**](https://github.com/lyhjeremy/one-in-a-hundred) | What it takes to be in the top 1% of a group, on income, wealth, height, life expectancy and more. Each fact is graded A to D by source agreement, with the full distribution drawn underneath. | 950 facts from 72 sources; question parser 90.5% exact on a 200-question gold set | [Live](https://lyhjeremy.github.io/one-in-a-hundred/) |
| [**Cantonese Learner**](https://github.com/lyhjeremy/cantonese-learner-v2) | Today's Hong Kong news rewritten into spoken Cantonese by an LLM with a review pass, plus an everyday-conversation course. Neural zh-HK audio, jyutping, tap-to-compare and speech grading. | Rebuilt daily, costs nothing to run | [Live](https://lyhjeremy.github.io/cantonese-learner-v2/) · [Write-up](https://lyhjeremy.github.io/cantonese-learner-v2/overview/) |
| [**Fourier Pen**](https://github.com/lyhjeremy/fourier-pen) | Any picture or text prompt becomes one continuous line, drawn by a chain of rotating arrows. Canny edges, a minimum-spanning-tree Euler tour so the pen never lifts, and a direct DFT, all in the browser. | Exports wallpapers and video | [Live](https://fourier-pen.vercel.app/) · [Write-up](https://fourier-pen.vercel.app/overview/) |

## The fine-tuning series

Four photo-to-structured-data apps. Each one pairs an LLM pipeline with a small open model fine-tuned on my laptop (LoRA on Qwen2.5) for the same task, then benchmarks base vs. fine-tuned vs. Claude zero-shot on held-out data.

| App | Task for the fine-tuned model | Fine-tuned | Claude zero-shot | |
|---|---|---|---|---|
| [**Receipt Auditor**](https://github.com/lyhjeremy/receipt-auditor) | Spend category for merchants it has never seen | **90.5%** | 80.0%<sup>1</sup> | [Live](https://lyhjeremy.github.io/receipt-auditor/) · [Write-up](https://lyhjeremy.github.io/receipt-auditor/overview/) |
| [**Cellar Scanner**](https://github.com/lyhjeremy/cellar-scanner) | Grape variety from a blind tasting note (1.5B model) | **27.7%** top-1 | 23.0%<sup>2</sup> | [Live](https://lyhjeremy.github.io/cellar-scanner/) · [Write-up](https://lyhjeremy.github.io/cellar-scanner/overview/) |
| [**Menu Decoder**](https://github.com/lyhjeremy/menu-decoder) | Cuisine and 14-allergen tags from a bare dish name | **99.3%** cuisine with no schema in the prompt; 69.3% allergen recall | 79.2% allergen recall<sup>3</sup> | [Live](https://lyhjeremy.github.io/menu-decoder/) · [Write-up](https://lyhjeremy.github.io/menu-decoder/overview/) |
| [**Race Day Copilot**](https://github.com/lyhjeremy/race-day-copilot) | Km-by-km pacing plan from a course map, checked by six deterministic rules (3B model) | near parity on structure | ahead on split arithmetic | [Live](https://lyhjeremy.github.io/race-day-copilot/) · [Write-up](https://lyhjeremy.github.io/race-day-copilot/overview/) |

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
- [Marathon Training Agent](https://github.com/lyhjeremy/marathon-training-agent): a LangGraph agent that drafts a training plan and revises it until it passes explicit safety checks. Streamlit UI. [Live](https://lyhjeremy.github.io/marathon-training-agent/)
- [Wine Pairing Agent](https://github.com/lyhjeremy/wine-pairing-agent): a LangGraph agent that reasons from pairing principles to a style, searches 30,000 indexed reviews as a tool, and critiques its own pick. [Live](https://lyhjeremy.github.io/wine-pairing-agent/)

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
- [Podcastify](https://github.com/lyhjeremy/podcastify): turns an EPUB or article into a two-host podcast with free neural voices. [Live](https://lyhjeremy.github.io/podcastify/)
- [EPUB to Audiobook](https://github.com/lyhjeremy/epub-to-audiobook): a desktop app for read-along audiobooks in English, Mandarin and Cantonese. [Live](https://lyhjeremy.github.io/epub-to-audiobook/)

#### Tools and finance
- [When Can I Retire?](https://github.com/lyhjeremy/fire-retirement-simulator): replays a retirement plan through every start year of US market history since 1871 (Shiller data), or a block bootstrap of it, with a stock/bond mix, guardrail spending and a solver for the smallest change that reaches 90%. Checked against the Trinity study and a 1946 to 1993 holdout. [Live](https://lyhjeremy.github.io/fire-retirement-simulator/)
- [Leave Time Optimizer](https://github.com/lyhjeremy/leave-time-optimizer): when to leave to arrive on time, from the Google Maps API. [Live](https://lyhjeremy.github.io/leave-time-optimizer/)
- [Connection Odds](https://github.com/lyhjeremy/connection-odds): how often a US connection fails, built from 21 million flights at the 30 busiest US hubs. A 45-minute layover (45 to 49 minutes) missed 17% of the time; the lookup gives the layover you need for 95%. [Live](https://lyhjeremy.github.io/connection-odds/)
- [downtime-cli](https://github.com/lyhjeremy/downtime-cli): a zero-dependency npm CLI that fills a long build or test run with terminal trivia, then hands you back the untouched output. [Live](https://lyhjeremy.github.io/downtime-cli)

</details>

## Toolkit

- **Modeling:** scikit-learn, PyTorch, XGBoost; regression, classification, clustering, time series, survival analysis, causal inference, A/B testing
- **GenAI:** RAG (BM25, dense, reranking), embeddings and vector stores, LoRA fine-tuning, LLM-as-judge evaluation, LangChain, LangGraph, Anthropic and OpenAI APIs
- **Optimization:** Gurobi; LP, IP, QP and non-convex programs; Monte Carlo simulation
- **Data and deployment:** Python, R, SQL, Snowflake, Airflow, Spark, Tableau, Power BI; FastAPI, Streamlit, Render, Vercel, GitHub Pages

## Education

MSBA, UCLA Anderson School of Management · graduate analytics coursework, Georgia Tech · BBA in Accounting and Finance, University of Hong Kong

<sub>Design and copy across these repos follow [these standards](DESIGN_STANDARDS.md).</sub>
