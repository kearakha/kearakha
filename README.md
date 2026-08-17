<div align="center">

# Muhammad Rakha Keanura

**Fullstack Developer** · Laravel & Next.js · Applied ML for Indonesian NLP

<a href="https://portofoliosrakha.vercel.app"><img src="assets/portfolio.svg" alt="Portfolio" /></a>
<a href="https://www.linkedin.com/in/rakha-keanura"><img src="assets/linkedin.svg" alt="LinkedIn" /></a>
<a href="mailto:keanuraka14@gmail.com"><img src="assets/email.svg" alt="Email" /></a>
<img src="assets/location.svg" alt="Jakarta, Indonesia" />

</div>

---

## About

Informatics Engineering student at Dian Nuswantoro University, based in Jakarta. I build backend and fullstack systems that go into actual production — most recently the Thesis domain of a faculty-scale academic system at Bengkel Koding, on Laravel 11 with a Next.js frontend on top. Alongside that I work on applied machine learning for Indonesian text: hoax classification, multi-label polarization detection, and retrieval-augmented generation over Indonesian news.

I care about systems that hold up under real data and real users, not demos.

<img src="assets/open-to.svg" alt="Open to backend, fullstack, and AI engineering roles" />

---

## Tech Stack

**Languages**<br>
<img src="https://skillicons.dev/icons?i=python,php,ts,js" alt="Python, PHP, TypeScript, JavaScript" />

**Backend**<br>
<img src="https://skillicons.dev/icons?i=laravel,fastapi,nodejs,express,prisma" alt="Laravel, FastAPI, Node.js, Express, Prisma" />

**Frontend**<br>
<img src="https://skillicons.dev/icons?i=nextjs,react,tailwind" alt="Next.js, React, Tailwind CSS" />

**ML & Data**<br>
<img src="https://skillicons.dev/icons?i=pytorch,sklearn,mysql,postgres,sqlite,supabase" alt="PyTorch, scikit-learn, MySQL, PostgreSQL, SQLite, Supabase" />

**Infra & Tooling**<br>
<img src="https://skillicons.dev/icons?i=git,github,linux,ubuntu,aws,nginx,vercel,postman" alt="Git, GitHub, Linux, Ubuntu, AWS, Nginx, Vercel, Postman" />

Also working with Hugging Face, XGBoost, FAISS, pandas, and NumPy.

---

## Selected Work

<details>
<summary><b>Academic System</b> — faculty-scale Laravel platform at Bengkel Koding</summary>
<br>

A faculty-scale academic system built by the Bengkel Koding web team. I own the **Thesis domain end-to-end**: lecturer quota plotting, submission flow, thesis monitoring, logbook recaps, PDF generation, and Excel reporting consumed directly by faculty staff — 46 controllers and 42 service classes. I also implemented study-program data isolation so each program reaches only its own data inside one shared system, and an Early Warning System that flags at-risk students from 5 risk indicators derived from roughly 10 years of academic records.

`Laravel 11` `PHP 8.2` `MySQL` `Next.js` — In production · Private, institutional

</details>

<details>
<summary><b>cus.site</b> — instant website generator for Indonesian small businesses</summary>
<br>

A shop owner completes a 5-step wizard covering business name, category, products, and photos. An OpenAI-compatible LLM (currently Gemini) writes the site copy — headline, product descriptions, SEO text — and the site goes live on its own subdomain (`namausaha.cus.site`), served by a single multi-tenant Next.js app. Three visual vibes: Casual, Professional, Elegant. Owners return through an emailed magic link to edit at any time.

`Next.js 14` `Prisma` `PostgreSQL` `Gemini API` — MVP complete · [Repository](https://github.com/kearakha/cus.site)

</details>

<details>
<summary><b>laris</b> — multi-tenant F&B SaaS</summary>
<br>

A SaaS platform for food and beverage businesses covering queue management, reservations, inventory, and sales, architected from the start for multi-branch scalability.

`Laravel 12` `Next.js 14` `TypeScript` `MySQL` — Complete · [Repository](https://github.com/kearakha/laris)

</details>

<details>
<summary><b>lumen-rag</b> — web layer for a Python RAG service</summary>
<br>

The web interface and orchestration layer for a retrieval-augmented generation service. Laravel owns the UI and the calls into the pipeline, while retrieval and generation run in Python as a separate service.

`Laravel` `PHP` `Python` — Complete · [Repository](https://github.com/kearakha/lumen-rag)

</details>

<details>
<summary><b>fineiro</b> — budget planning with spending prediction</summary>
<br>

A budget planning app with spending prediction. A standalone FastAPI service runs per-category linear regression on pandas-aggregated monthly spending, and a Node.js backend consumes it over HTTP. When the prediction service is unavailable the app degrades gracefully instead of failing.

`Python` `FastAPI` `Node.js` `React` `TypeScript` — Complete · [Repository](https://github.com/kearakha/fineiro)

</details>

<details>
<summary><b>agentic-cockpit</b> — local dashboard for Claude Code CLI</summary>
<br>

A local dashboard that wraps Claude Code CLI headless mode into one-click actions, with streaming output and session logging so every run stays reviewable afterwards.

`Next.js 15` `TypeScript` `Tailwind v4` `Prisma` `SQLite` — Personal tooling · [Repository](https://github.com/kearakha/agentic-cockpit)

</details>

---

## Research

<details>
<summary><b>Retrieval-Augmented Generation over Indonesian News</b></summary>
<br>

An end-to-end RAG pipeline over 3,249 Kompas.com articles, chunked into 37,741 passages and indexed with FAISS (IndexFlatIP) using 768-dimensional multilingual-e5-base embeddings. Grounding generation in the top-3 retrieved passages made the system abstain correctly on out-of-corpus questions where a retrieval-free baseline confidently hallucinated. The failure mode I identified: retrieval returns top-k unconditionally with no similarity threshold, so reranking and score cutoffs are the next step.

`Python` `FAISS` `Hugging Face` `Qwen 2.5-7B` — [Repository](https://github.com/kearakha/rag-indonesian-news)

</details>

<details>
<summary><b>Fake News Detection for Indonesian News</b></summary>
<br>

Indonesian hoax classification using TF-IDF n-gram features with a GridSearchCV-tuned XGBoost classifier, reaching 0.91 accuracy, 0.91 F1, and 0.97 ROC-AUC. I benchmarked CountVectorizer against TF-IDF across 6 classifiers to establish which feature extraction actually wins for Indonesian text, handled class imbalance with SMOTE, and built an Indonesian-specific preprocessing pipeline covering slang and regional stopwords.

`Python` `scikit-learn` `XGBoost` — First author, manuscript in preparation

</details>

<details>
<summary><b>Multi-label Polarization Detection — SemEval 2026 Task 9</b></summary>
<br>

Five-label multi-label classification where the gains came from threshold and loss design rather than a bigger model. Replacing a single global threshold with per-label tuning lifted Macro F1 from 0.444 to 0.512 and Micro F1 from 0.587 to 0.648. Using `pos_weight` in `BCEWithLogitsLoss` against a 15:1 imbalance rescued the worst minority label from F1 0.00 to 0.34, and moved the religious label from 0.36 to 0.59.

`PyTorch` `RoBERTa` `Hugging Face` — [Repository](https://github.com/kearakha/semeval-2026-polarization-detection)

</details>

---

## Experience

**Backend Developer & Lead of Web Developer Division** — Bengkel Koding · Jan 2025 – Present

Shipped the Thesis domain of the faculty academic system end-to-end (detailed above), and led a 19-person Web Developer division across multiple concurrent projects.

**Teaching Assistant** — Bengkel Koding · Jan 2026 – Aug 2026

Mentored 30+ students in a Web Developer Class covering PHP and Laravel fundamentals.

---

## Education

**Dian Nuswantoro University** — B.Sc. Informatics Engineering · Sep 2023 – Jun 2027 · Semarang · GPA 3.87 / 4.00

**Gadjah Mada University** — Student Exchange · Aug 2025 – Dec 2025 · Yogyakarta · GPA 3.83 / 4.00
Deep Learning, Information Retrieval, Artificial Intelligence, UI/UX and Frontend, Introduction to Blockchain.

---

## Certifications

- **NVIDIA** — Getting Started with Deep Learning
- **Cisco** — CCNA: Introduction to Networks
- **Digital Talent Scholarship, Kominfo** — Associate Data Scientist
- **Gadjah Mada University** — Student Mobility Certificate

---

## Currently

```yaml
learning:   [MLOps, model serving, IBM AS/400, Query/400]
building:   [sanmon]
exploring:  [AI, RAG, Go, Vue]
```

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/kearakha/kearakha/output/snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/kearakha/kearakha/output/snake-light.svg" />
  <img src="https://raw.githubusercontent.com/kearakha/kearakha/output/snake-light.svg" alt="Contribution snake animation" />
</picture>

<br /><br />

Open to backend, fullstack, and AI engineering roles — reach out if you are building something that has to work in production.

<a href="mailto:keanuraka14@gmail.com"><img src="assets/email.svg" alt="Email" /></a>
<a href="https://www.linkedin.com/in/rakha-keanura"><img src="assets/linkedin.svg" alt="LinkedIn" /></a>
<a href="https://portofoliosrakha.vercel.app"><img src="assets/portfolio.svg" alt="Portfolio" /></a>

</div>
