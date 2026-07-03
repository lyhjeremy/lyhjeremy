# Hi, I'm Jeremy Lee 👋

Data scientist and UCLA Anderson MSBA. Formerly Chief Strategy Officer; now focused on applied analytics and machine learning. I turn ambiguous business problems into models and decision tools.

```bash
npx lyhjeremy
```
↑ run that in your terminal for the interactive version of this README

## What I work with
- **Modeling** · scikit-learn · PyTorch · XGBoost · regression / classification / clustering · time series · neural networks · causal inference · survival analysis · A/B testing
- **Optimization** · Gurobi · LP / IP / QP / non-convex programming · branch-and-bound · LP duality · gradient descent · simulation · Monte Carlo
- **GenAI** · LLM prompting · RAG · embeddings · vector databases · fine-tuning · OpenAI / Anthropic APIs · NLP
- **Agents & orchestration** · LangChain · LangGraph · agentic workflows · tool use · retrieval pipelines · multi-step reasoning
- **Data & tools** · Python · R · SQL · Snowflake · Airflow · Spark / PySpark · Tableau · Power BI · Excel · Git · GCS · Jupyter
- **Deployment & apps** · GitHub Pages · Streamlit · interactive dashboards · desktop apps · live demos · reproducible pipelines

## Featured projects
Selected work spanning generative AI, statistical modeling, and machine learning. Each title links to the code; the **Live** link opens a plain-language write-up in the browser. The full set of projects is in the dropdown below.

| Project | Methods | |
|---|---|---|
| [**Wine Sommelier RAG**](https://github.com/lyhjeremy/wine-sommelier-rag) | Semantic search over 130k wine reviews using hybrid BM25 and dense retrieval with a cross-encoder reranker, evaluated on retrieval quality (precision and nDCG up roughly 21%). | [Live](https://lyhjeremy.github.io/wine-sommelier-rag/) |
| [**Marathon Training Agent**](https://github.com/lyhjeremy/marathon-training-agent) | A LangGraph agent that iteratively drafts and revises a training plan until it satisfies explicit safety checks, with a Streamlit interface. | [Live](https://lyhjeremy.github.io/marathon-training-agent/) |
| [**World-Record Half-Lives**](https://github.com/lyhjeremy/world-record-half-lives) | Survival analysis (Kaplan-Meier and Cox regression) of how long track-and-field world records stand, estimating each record's probability of falling. | [Live](https://lyhjeremy.github.io/world-record-half-lives/) |
| [**Performance Continuum**](https://github.com/lyhjeremy/marathon-performance-continuum) | Distribution fitting and extreme-value theory locating any marathon time within a field of 31,842 finishers and quantifying how far the world record sits beyond it. | [Live](https://lyhjeremy.github.io/marathon-performance-continuum/) |
| [**National Strength Profiles**](https://github.com/lyhjeremy/national-strength-profiles) | K-means clustering and PCA of 43 nations across five athletics disciplines, identifying five distinct performance archetypes. | [Live](https://lyhjeremy.github.io/national-strength-profiles/) |
| [**Scoring-Table Fairness Audit**](https://github.com/lyhjeremy/athletics-scoring-fairness) | Non-parametric hypothesis testing (Kruskal-Wallis) on 6,400 elite marks, assessing whether World Athletics points are comparable across events. | [Live](https://lyhjeremy.github.io/athletics-scoring-fairness/) |

<details>
<summary><strong>More projects</strong> (16 additional repositories)</summary>

#### Generative AI & agents
| Project | Methods | |
|---|---|---|
| [**Marathon Strategy RAG**](https://github.com/lyhjeremy/marathon-strategy-rag) | Grounded retrieval-augmented Q&A that cites its sources, evaluated with an LLM-as-judge faithfulness metric; includes a LangChain LCEL implementation. | [Live](https://lyhjeremy.github.io/marathon-strategy-rag/) |
| [**Wine Pairing Agent**](https://github.com/lyhjeremy/wine-pairing-agent) | A LangGraph agent that infers a wine style and calls the retriever as a LangChain tool, with full run tracing. | [Live](https://lyhjeremy.github.io/wine-pairing-agent/) |

#### Running & sports analytics
| Project | Methods | |
|---|---|---|
| [**The Heat Tax**](https://github.com/lyhjeremy/marathon-heat-tax) | Regression of Boston Marathon field times on temperature: roughly one minute slower per °F (r = 0.86). | [Live](https://lyhjeremy.github.io/marathon-heat-tax/) |
| [**The Negative-Split Myth**](https://github.com/lyhjeremy/marathon-negative-split-myth) | Split analysis showing only 2.5% of 31,912 Boston finishers ran a faster second half. | [Live](https://lyhjeremy.github.io/marathon-negative-split-myth/) |
| [**Hitting the Wall**](https://github.com/lyhjeremy/marathon-pacing-decay) | Per-5K split analysis locating where marathon pace decays, around 30 km. | [Live](https://lyhjeremy.github.io/marathon-pacing-decay/) |
| [**Boston BQ Fairness**](https://github.com/lyhjeremy/boston-marathon-qualifying-fairness) | An equity analysis of Boston qualifying standards across age and gender brackets. | [Live](https://lyhjeremy.github.io/boston-marathon-qualifying-fairness/) |
| [**Marathon Majors Course Difficulty**](https://github.com/lyhjeremy/marathon-majors-course-difficulty) | A three-framework comparison of finishing speed across the six World Marathon Majors. | [Live](https://lyhjeremy.github.io/marathon-majors-course-difficulty/) |
| [**Marathon Shoe Revolution**](https://github.com/lyhjeremy/marathon-shoe-revolution-decomposition) | Decomposition of recent marathon progression into footwear effects versus other factors. | [Live](https://lyhjeremy.github.io/marathon-shoe-revolution-decomposition/) |

#### Language & NLP
| Project | Methods | |
|---|---|---|
| [**Are Song Lyrics Getting Simpler?**](https://github.com/lyhjeremy/lyrics-complexity-over-time) | Fifty years of Billboard lyrics: longer and more repetitive over time, with roughly stable vocabulary. | [Live](https://lyhjeremy.github.io/lyrics-complexity-over-time/) |
| [**Love Island Lexical Analysis**](https://github.com/lyhjeremy/love-island-lexical-analysis) | A corpus study of lexical complexity in reality-television dialogue. | [Live](https://lyhjeremy.github.io/love-island-lexical-analysis/) |
| [**EPUB Reading-Level Analyzer**](https://github.com/lyhjeremy/epub-reading-level-analyzer) | An in-browser tool reporting a book's reading level and vocabulary load from an EPUB file. | [Live](https://lyhjeremy.github.io/epub-reading-level-analyzer/) |
| [**Mandarin Learning Reader**](https://github.com/lyhjeremy/mandarin-learning-reader) | An interactive Mandarin reader built from any Chinese EPUB, with per-character pinyin, read-aloud, and offline pronunciation grading. | [Live](https://lyhjeremy.github.io/mandarin-learning-reader/) |
| [**Cantonese Learner**](https://github.com/lyhjeremy/cantonese-learner) | A mobile Cantonese speaking tutor built from current Hong Kong news articles. | [Live](https://lyhjeremy.github.io/cantonese-learner/) |

#### Consumer & finance
| Project | Methods | |
|---|---|---|
| [**Wine Score Inflation**](https://github.com/lyhjeremy/wine-score-inflation) | How 130k professional reviews cluster into an effective 8-point band on the nominal 100-point scale. | [Live](https://lyhjeremy.github.io/wine-score-inflation/) |
| [**When Can I Retire?**](https://github.com/lyhjeremy/fire-retirement-simulator) | A Monte-Carlo retirement simulator estimating the probability a portfolio lasts through retirement. | [Live](https://lyhjeremy.github.io/fire-retirement-simulator/) |

#### Apps & tools
| Project | Methods | |
|---|---|---|
| [**Leave Time Optimizer**](https://github.com/lyhjeremy/leave-time-optimizer) | A routing tool that computes when to depart to arrive on time, using the Google Maps API. | [Live](https://lyhjeremy.github.io/leave-time-optimizer/) |
| [**EPUB → Audiobook**](https://github.com/lyhjeremy/epub-to-audiobook) | A desktop app that converts e-books into read-along audiobooks (English and Chinese). | [Live](https://lyhjeremy.github.io/epub-to-audiobook/) |
| [**Podcastify**](https://github.com/lyhjeremy/podcastify) | Converts an e-book or article into a two-host podcast with synthetic voices. | [Live](https://lyhjeremy.github.io/podcastify/) |

</details>

## Experience & education
- **Co-founder & Chief Strategy Officer**, Casual Ace Learning Centre — grew enrollment 5.2× to over 1,000 students across six centers.
- **MSBA**, UCLA Anderson · graduate analytics coursework, Georgia Tech · **BBA** (Accounting & Finance), University of Hong Kong.

## Outside the terminal
14 marathons, Berlin personal best of 2:48 · WSET Level 3 in wine.

## Contact
[LinkedIn](https://www.linkedin.com/in/jeremylyh/) · [Email](mailto:lyhjeremy@gmail.com)
