# Memaar-El-Morshedy
🎓 Graduation project: a full-scale Business Intelligence solution built for El-Morshedy Real Estate, a developer managing installment sales and collections across 8 residential projects — Degla Palms, Degla Landmark, Crystal Plaza Maadi, Lake, Skyline Katameya, Rihana, Zahra, and One Katameya.

📌 The Problem:
Each project tracked its installment schedules in its own standalone Excel workbook. That meant:
– No way to compare performance across projects
– Overdue installments surfacing too late for the collections team to act
– Cash and bank collections mixed together, hiding channel and bank-level performance
– Recurring reports rebuilt manually every cycle

🔧 What We Built:
– A unified star-schema data model in Power BI, with one fact table of installments per project joined to Customer, Unit, Payment, and Date dimensions

– A 9-stage Power Query pipeline to clean and standardize all 8 source files — including unpivoting a wide P1–P7 installment schedule into a proper long format so DAX could filter, sum, and rank by installment number.

– 13 core DAX measures (Sold Count, Collection Rate, Outstanding Amount, Project Completion %, and more), replicated per project and rolled up into a Global Summary using TREATAS and REMOVEFILTERS to handle cross-table filtering and fixed-denominator ratios.

– 35 designed dashboard pages with a consistent Overall / Cash / Bank / Bank-wise navigation structure per project, plus company-wide Global Summary and Collection-by-Date views.

– Custom Deneb (Vega-Lite) visuals to chart collection rate curves by installment number — something native Power BI visuals couldn't do out of the box.

📊 Key Metrics Delivered:
– 8 projects, 35 report pages, ~51 tables unified into one model
– Company-wide and per-project: Sold %, Collection Rate, Outstanding Balance, Project Completion %
– Bank-wise ranking of collection performance across payment channels.


💡 Key Insight:
Sales progress and collection progress often diverge — a project can look almost fully sold while its actual collection rate tells a very different story. That gap is exactly what this dashboard was built to surface.

🚧 Challenges We Tackled:

– Reconciling inconsistent project naming (Arabic/English variants, typos) across 8 independently maintained files.

– Avoiding double-counting after unpivoting installment columns, by using DISTINCTCOUNT instead of simple row counts.

– Simulating relationships between 8 independent star schemas for a single company-wide filter, using TREATAS.

– Keeping fixed-denominator ratios (like Sold %) stable under slicer filters.
