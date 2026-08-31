# PROJECT DEVELOPMENT ROADMAP
## Two Substantial Projects for University Applications & Elevance Health Deployment

**Project 1:** Snowflake Cost Monitoring System with LLM-Powered Recommendations  
**Project 2:** Intelligent Data Pipeline Orchestrator (Natural Language to ETL Workflows)

**Weekend Work Schedule:** Saturdays 8 AM-3 PM (7 hours focused development time)  
**Total Project Time Available:** February-July 2026 = ~21 weekends × 7 hours = 147 hours across both projects

---

## PROJECT 1: SNOWFLAKE COST MONITORING SYSTEM
**Duration:** March 1 - May 10, 2026 (10 weekends = 70 hours)  
**Goal:** Production-ready system that monitors Snowflake usage, identifies cost inefficiencies, and provides LLM-powered optimization recommendations

### PHASE 1A: FOUNDATION & LEARNING (March 1-15, 2026 - 2 weekends)

**Weekend 1: March 1-2, 2026**  
**Saturday March 1 (8 AM-3 PM):**
- Hour 1-2 (8-10 AM): Watch comprehensive LLM introduction videos understanding transformer architecture at high level, attention mechanisms basics, why LLMs can generate coherent text
- Hour 3-4 (10 AM-12 PM): Read OpenAI API documentation thoroughly, understand concepts of prompts, tokens, temperature parameter, max tokens, system messages vs user messages
- Hour 4-5 (12-1 PM): Lunch break
- Hour 5-7 (1-3 PM): Create OpenAI account, obtain API key, write first Python scripts making simple API calls using requests library or OpenAI Python SDK, experiment with different prompts and see responses

**Deliverable:** Working Python scripts that can call GPT-4 API and receive responses, basic understanding of prompt engineering

**Sunday March 2:** ✨ COMPLETE REST DAY ✨

---

**Weekend 2: March 8-9, 2026**  
**Saturday March 8:**
Your focus this weekend is IELTS preparation, not project work. Use this time for mock tests.

**Sunday March 9:** Light rest before IELTS exam week

---

**Weekend 3: March 15-16, 2026**  
**Saturday March 15 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Design Project 1 architecture on paper or digital whiteboard (Excalidraw, draw.io), identify components: 
  - Data collection module (queries Snowflake metadata about queries run, warehouses used, credits consumed)
  - Cost calculation module (processes usage data, calculates costs per warehouse, per query, per user)
  - LLM recommendation module (analyzes patterns, generates optimization suggestions)
  - Dashboard/UI module (displays metrics and recommendations)
- Hour 3-4 (10:30 AM-12 PM): Research Snowflake metadata tables and views, understand ACCOUNT_USAGE schema, QUERY_HISTORY view, WAREHOUSE_METERING_HISTORY view
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Set up development environment: create Python virtual environment, install necessary libraries (snowflake-connector-python, pandas, openai, flask for later web dashboard)

**Deliverable:** Architecture diagram for Project 1, development environment ready

**Sunday March 16:** ✨ COMPLETE REST DAY ✨

---

### PHASE 1B: DATA COLLECTION MODULE (March 22-29, 2026 - 2 weekends)

**Weekend 4: March 22-23, 2026**  
**Saturday March 22 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Write Python module that connects to Snowflake using snowflake-connector-python, authenticate using credentials, execute test query to verify connection works
- Hour 3-4 (10:30 AM-12 PM): Write functions to query ACCOUNT_USAGE.QUERY_HISTORY table to retrieve all queries run in past 30 days with their execution times, credits used, warehouses used
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Write functions to query WAREHOUSE_METERING_HISTORY to get credit consumption per warehouse per day, store results in pandas DataFrames

**Deliverable:** Working data collection module that can pull Snowflake usage data programmatically

**Sunday March 23:** Regular study schedule (German + LeetCode + light AWS review)

---

**Weekend 5: March 29-30, 2026**  
**Saturday March 29 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Enhance data collection module to also pull metadata about tables accessed, users who ran queries, query patterns (SELECT vs INSERT vs DELETE distributions)
- Hour 3-4 (10:30 AM-12 PM): Implement data caching mechanism so you don't have to repeatedly query Snowflake during development, save retrieved data to local CSV or JSON files
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Write unit tests for data collection functions, handle edge cases (connection failures, empty result sets, malformed queries)

**Deliverable:** Robust data collection module with error handling and caching

**Sunday March 30:** ✨ COMPLETE REST DAY ✨

---

### PHASE 1C: COST CALCULATION ENGINE (April 5-12, 2026 - 2 weekends)

**Weekend 6: April 5-6, 2026**  
**Saturday April 5 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Implement cost calculation logic: for each warehouse, sum up total credits consumed, multiply by Snowflake credit cost (varies by region, typically three to four dollars per credit), calculate total spend
- Hour 3-4 (10:30 AM-12 PM): Break down costs by different dimensions: cost per warehouse, cost per user, cost per query type, cost per database/schema, identify which dimensions reveal most interesting insights
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Implement trend analysis: compare current week costs to previous week, identify queries whose costs are increasing over time, detect unusually expensive queries

**Deliverable:** Cost calculation engine that produces comprehensive cost breakdown from usage data

**Sunday April 6:** ✨ COMPLETE REST DAY ✨

---

**Weekend 7: April 12-13, 2026** (3-day block with leave on April 10)  
**Thursday April 10:** Leave day for AWS hands-on intensive  
**Friday April 11:** Regular work  
**Saturday April 12 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Build simple web dashboard using Flask web framework, create homepage that displays key metrics: total monthly spend, cost per warehouse chart (bar graph using Plotly or matplotlib), top ten most expensive queries table
- Hour 3-4 (10:30 AM-12 PM): Add filter functionality allowing user to select date range, specific warehouse, specific user to drill down into costs
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Style dashboard with basic CSS, make it presentable (doesn't need to be beautiful, but should be clean and readable)

**Deliverable:** Functional web dashboard displaying Snowflake cost analytics

**Sunday April 13:** Study day (German 1 hour, LeetCode 2 hours practice session)

---

### PHASE 1D: LLM RECOMMENDATION ENGINE (April 19-26, 2026 - 2 weekends)

**Weekend 8: April 19-20, 2026**  
**Saturday April 19 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Design prompt engineering strategy for cost recommendations. Create system prompt that instructs GPT-4 to act as Snowflake cost optimization expert. Prepare structured data format to send to LLM: list of expensive queries with their properties (execution time, data scanned, result size, warehouse size used)
- Hour 3-4 (10:30 AM-12 PM): Implement basic LLM integration: for top five most expensive queries, send query details to GPT-4 API with prompt asking for optimization suggestions based on Snowflake best practices
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Test LLM responses, refine prompts to get more actionable recommendations (add context about Snowflake features like clustering keys, materialized views, result caching that LLM can suggest)

**Deliverable:** Basic LLM recommendation engine generating optimization suggestions

**Sunday April 20:** ✨ COMPLETE REST DAY ✨

---

**Weekend 9: April 26-27, 2026** (3-day block with leave on April 25)  
**Friday April 25:** Leave day  
**Saturday April 26 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Enhance LLM recommendations: implement pattern detection where you analyze multiple expensive queries, identify common anti-patterns (like missing WHERE clauses, lack of clustering, oversized warehouses for small queries), create targeted prompts for each pattern type
- Hour 3-4 (10:30 AM-12 PM): Add recommendation prioritization: classify recommendations by potential impact (high impact savings vs nice to have improvements) and implementation difficulty (easy quick wins vs complex refactors)
- Hour 4-5 (12-1 PM): Lunch  
- Hour 5-7 (1-3 PM): Integrate recommendations into dashboard, display recommendations alongside cost metrics with clear action items

**Deliverable:** Intelligent recommendation system with prioritized, actionable suggestions

**Sunday April 27:** Regular study

---

### PHASE 1E: TESTING, DOCUMENTATION, DEPLOYMENT (May 3-10, 2026 - 2 weekends)

**Weekend 10: May 3-4, 2026** (3-day block with leave on May 5 Monday)  
**Saturday May 3 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Comprehensive testing: run system against different time periods of data, verify cost calculations are accurate by comparing against Snowflake billing, test recommendation quality by showing to colleagues or reviewing yourself
- Hour 3-4 (10:30 AM-12 PM): Fix bugs discovered during testing, handle edge cases (queries with null values, warehouses that were resized mid-query, suspended warehouses)
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Write comprehensive README documentation explaining what the system does, how to set it up, how to run it, what dependencies are needed, include architecture diagram and screenshots of dashboard

**Sunday May 4:** ✨ COMPLETE REST DAY ✨

**Monday May 5:** Leave day - use for project completion

---

**Weekend 11: May 10-11, 2026**  
**Saturday May 10 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Create demo video or presentation showing Project 1 in action: showing dashboard, walking through cost analysis, demonstrating LLM recommendations, explaining business value (how much money this could save Elevance Health)
- Hour 3-4 (10:30 AM-12 PM): Prepare for potential deployment at Elevance Health: discuss with your team if they'd like to use this tool, gather feedback on features they'd want, refine based on their input
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Polish code: add extensive comments explaining complex logic, refactor for readability, separate concerns into well-organized modules, ensure code quality is high for showcasing in university applications

**Deliverable:** PROJECT 1 COMPLETE - Production-ready Snowflake cost monitoring system with documentation

**Sunday May 11:** Study + rest

---

## PROJECT 2: INTELLIGENT DATA PIPELINE ORCHESTRATOR
**Duration:** May 17 - July 26, 2026 (10 weekends = 70 hours)  
**Goal:** LLM-powered system that generates ETL workflow code from natural language descriptions, optimizes pipelines, and handles error cases intelligently

### PHASE 2A: LEARNING LANGCHAIN & CODE GENERATION FOUNDATIONS (May 17-31, 2026 - 3 weekends)

**Weekend 12: May 17-18, 2026** (3-day block with leave on May 15 Thursday)  
**Saturday May 17 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Learn LangChain framework fundamentals: read official documentation, understand core concepts (chains, agents, memory, prompts), watch tutorial videos on YouTube about building LLM applications with LangChain
- Hour 3-4 (10:30 AM-12 PM): Install LangChain library, experiment with simple chains that link multiple LLM calls together, understand how to maintain context across conversation turns
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Build simple example: create chain that takes user question, searches documentation, formats answer - basically a mini RAG (Retrieval Augmented Generation) system to understand the pattern

**Deliverable:** Working knowledge of LangChain, simple demonstration applications

**Sunday May 18:** ✨ COMPLETE REST DAY ✨

---

**Weekend 13: May 24-25, 2026**  
**Saturday May 24 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Study prompt engineering for code generation: read research papers or blog posts about Codex, GitHub Copilot architecture, how LLMs can generate syntactically correct code, common techniques (providing examples in prompt, specifying programming language and libraries to use)
- Hour 3-4 (10:30 AM-12 PM): Experiment with code generation: give GPT-4 prompts like "write Python function that reads CSV file and calculates average of column X", evaluate quality of generated code, identify what makes prompts produce better code
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Build prototype: create system where user describes simple data transformation in natural language, your code uses LLM to generate Python pandas code that performs transformation, execute generated code and verify it works

**Deliverable:** Basic natural language to code generation working for simple cases

**Sunday May 25:** Study

---

**Weekend 14: May 31-June 1, 2026**  
**Saturday May 31 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Design Project 2 architecture: identify components needed (natural language parser that extracts intent and entities from user request, code generation module using LLM, validation module that checks generated code for safety, execution engine that runs code in isolated environment, optimization module that suggests improvements)
- Hour 3-4 (10:30 AM-12 PM): Set up Project 2 development environment: create new Python project, install dependencies (langchain, openai, pandas, sqlalchemy for database interactions if generating SQL, potentially Docker if you want isolated execution), organize code structure with separate modules
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Create sample dataset of common ETL patterns and their natural language descriptions: "load data from CSV and remove duplicates", "join two tables on common key", "aggregate data by group and calculate sum", "filter rows where value exceeds threshold" - these become your test cases and examples for LLM

**Deliverable:** Architecture design for Project 2, development environment ready, test dataset created

**Sunday June 1:** ✨ COMPLETE REST DAY ✨

---

### PHASE 2B: NATURAL LANGUAGE PARSER & INTENT UNDERSTANDING (June 7-14, 2026 - 2 weekends)

**Weekend 15: June 7-8, 2026** (3-day block with leave on June 5 Friday)  
**Saturday June 7 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Build natural language parser using LLM: create system prompt that instructs LLM to analyze user's ETL request and extract structured information (data sources mentioned, transformations requested, output format desired, any constraints specified)
- Hour 3-4 (10:30 AM-12 PM): Implement intent classification: determine whether user wants data loading, transformation, joining, aggregation, filtering, or combination of operations, classify into predefined categories
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Handle ambiguous requests: when user description is vague, generate clarifying questions to ask user (like "You mentioned joining tables, which column should be used as join key?"), implement back-and-forth conversation capability using LangChain memory

**Deliverable:** Natural language parser that can understand ETL requests and ask clarifying questions

**Sunday June 8:** Study

---

**Weekend 16: June 14-15, 2026**  
**Saturday June 14 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Entity extraction: identify specific entities in user request like table names, column names, filter conditions, aggregation functions, implement using combination of pattern matching and LLM analysis
- Hour 3-4 (10:30 AM-12 PM): Build request validation: check if mentioned tables and columns actually exist in your data catalog (you can create mock catalog for demo), validate that requested operations are logically sound (can't aggregate before grouping, can't join tables with no common columns)
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Test parser with your sample dataset of ETL requests, measure accuracy of intent detection and entity extraction, refine prompts to improve accuracy

**Deliverable:** Robust natural language parser with validation

**Sunday June 15:** ✨ COMPLETE REST DAY ✨

---

### PHASE 2C: ETL CODE GENERATION ENGINE (June 21-28, 2026 - 2 weekends)

Note: Week of June 15-21 might include your APS interview, adjust schedule if needed

**Weekend 17: June 21-22, 2026**  
**Saturday June 21 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Implement code generation module: based on parsed intent and entities, construct detailed prompt for LLM that includes context about available data sources, schema information, and specific transformation requested, ask LLM to generate complete Python code using pandas or PySpark
- Hour 3-4 (10:30 AM-12 PM): Implement code templates: create partial code skeletons for common patterns (data loading template, join template, aggregation template) that LLM fills in with specifics, this improves consistency and reduces errors
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Add code safety checks: analyze generated code before execution to ensure it doesn't contain dangerous operations (like deleting files, making network calls to external services, infinite loops), implement sandboxing or static analysis

**Deliverable:** Code generation engine that produces executable ETL code from natural language

**Sunday June 22:** Study

---

**Weekend 18: June 28-29, 2026**  
**Saturday June 28 (8 AM-3 PM):**
- This weekend you're focused on completing AWS course videos and preparing for AWS exam, so lighter project work
- Hour 1-3 (8-10:30 AM): Test generated code with various ETL scenarios, identify common failure modes (incorrect column references, type mismatches, missing error handling in generated code)
- Hour 3-7 (10:30 AM-3 PM with lunch break): Implement iterative refinement: when generated code fails, capture error message, send back to LLM with request to fix the code, repeat until code executes successfully or max iterations reached

**Deliverable:** Code generation with automatic error correction

**Sunday June 29:** ✨ COMPLETE REST DAY ✨

---

### PHASE 2D: OPTIMIZATION RECOMMENDATIONS (July 5-12, 2026 - 2 weekends)

Note: Week of July 6-12 includes AWS exam on July 6 and potentially APS interview

**Weekend 19: July 5-6, 2026**  
**Saturday July 5:** AWS exam final review (Project 2 work paused this weekend)  
**Sunday July 6:** Light review, relax before Monday exam

---

**Weekend 20: July 12-13, 2026**  
**Saturday July 12 (8 AM-3 PM):**
This is your celebration day after AWS certification and APS interview completion! Light project work only.
- Hour 1-4 (8 AM-12 PM): Design workflow optimization module: analyze generated ETL code and identify optimization opportunities (unnecessary data loading if only few columns needed, missing indexes that would speed up joins, inefficient loops that could be vectorized)
- Hour 4-7 (12-3 PM): Lunch break and relaxation

**Sunday July 13:** ✨ COMPLETE REST DAY ✨

---

### PHASE 2E: INTEGRATION & USER INTERFACE (July 19-26, 2026 - 2 weekends)

**Weekend 21: July 19-20, 2026**  
**Saturday July 19 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Build simple web interface using Flask or Streamlit: create form where user enters natural language description of ETL task, submit button that triggers your pipeline, display area showing parsed intent, generated code, and execution results
- Hour 3-4 (10:30 AM-12 PM): Add conversation interface: allow multi-turn interaction where system asks clarifying questions and user provides answers, maintain conversation history using session state
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Implement code review feature: display generated code with syntax highlighting, allow user to manually edit code before execution if they want, show optimization suggestions alongside code

**Deliverable:** User-friendly interface for Project 2

**Sunday July 20:** Study

---

**Weekend 22: July 26-27, 2026** (3-day block with leave on July 25 Friday)  
**Friday July 25:** Leave day for Project 2 completion  
**Saturday July 26 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Comprehensive testing: test with diverse ETL scenarios ranging from simple ("load CSV") to complex ("join three tables, apply multiple filters, aggregate by two dimensions, write to database"), verify generated code is correct and efficient
- Hour 3-4 (10:30 AM-12 PM): Error handling and robustness: add try-catch blocks around code execution, provide helpful error messages when things fail, implement logging so you can debug issues
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Create comprehensive documentation: architecture diagram showing how components interact, user guide explaining how to use the system, developer guide for future enhancements, include example use cases with screenshots

**Sunday July 27:** ✨ COMPLETE REST DAY ✨

---

### PHASE 2F: DEMO & DEPLOYMENT PREPARATION (July 31-August 1, 2026 - 1 weekend)

**Weekend 23: July 31-August 1, 2026**  
**Saturday July 31 (8 AM-3 PM):**
- Hour 1-3 (8-10:30 AM): Create demo video or presentation: record walkthrough showing Project 2 in action, demonstrate starting from natural language request through generated code to execution results, highlight intelligent features like clarifying questions and optimization suggestions
- Hour 3-4 (10:30 AM-12 PM): Prepare for showcasing to Elevance Health team: create presentation explaining business value (how this tool could accelerate ETL development, reduce errors, help less technical users create data pipelines)
- Hour 4-5 (12-1 PM): Lunch
- Hour 5-7 (1-3 PM): Polish and package: refactor code for clarity, add comprehensive comments, organize into professional package structure with setup.py, create requirements.txt for easy installation, push to GitHub with well-written README

**Deliverable:** PROJECT 2 COMPLETE - Intelligent pipeline orchestrator ready for demonstration

**Sunday August 1:** Study + rest

---

## BOTH PROJECTS COMPLETE BY AUGUST 1, 2026!

**What You've Built:**

**Project 1 Showcases:**
- Cloud architecture understanding (connecting to Snowflake, handling distributed data)
- Data analysis skills (processing query logs, calculating costs, identifying patterns)
- LLM integration (using GPT-4 API for intelligent recommendations)
- Full-stack development (backend data processing + web dashboard frontend)
- Business value awareness (cost optimization solves real company problem)

**Project 2 Showcases:**
- Advanced LLM application development (beyond simple API calls to complex agent behavior)
- Code generation and validation (making LLMs produce executable, safe code)
- Natural language processing (parsing user intent, entity extraction, conversation handling)
- Software engineering discipline (error handling, testing, documentation)
- Innovation (building genuinely novel tool that doesn't exist in market)

**For University Applications:**
- Both projects demonstrate technical depth expected of Master's students
- Show initiative to solve real problems, not just tutorial projects
- Illustrate understanding of current AI/ML trends (LLMs, agentic AI)
- Prove you can build complete systems, not just scripts
- Provide concrete evidence of skills mentioned in Statement of Purpose

**For Elevance Health:**
- Both tools solve actual problems your team faces
- Demonstrate your value beyond your current role responsibilities
- Position you for promotion or expanded responsibilities
- Create artifacts that continue benefiting company after you leave for Germany
- Strengthen recommendation letter by giving manager concrete achievements to cite

---

## DEVOPS SKILLS INTEGRATION THROUGH PROJECT WORK

As you build these projects, you'll naturally learn and apply DevOps practices:

**Containerization (Docker):**
- After completing Project 1 (May), containerize it: write Dockerfile that packages Python application with all dependencies, build Docker image, run container locally
- After completing Project 2 (August), containerize it similarly
- This makes projects portable and easy to deploy anywhere

**Orchestration (Kubernetes):**
- In August-September during lighter study periods, deploy your containerized projects to local Kubernetes cluster (minikube or kind)
- Learn Kubernetes concepts: pods, deployments, services
- Create deployment YAML files for your projects

**CI/CD Pipelines:**
- Set up GitHub Actions or GitLab CI for your project repositories
- Create pipeline that runs tests automatically on each commit, builds Docker images, pushes to container registry
- Implement basic deployment automation

**Timeline for DevOps Learning:**
- May-June: Docker basics (containerize Project 1)
- July-August: Kubernetes fundamentals (deploy projects to local K8s)
- August-September: CI/CD setup (automate build and test)
- These fit naturally into weekend project time after main project features are complete

---

## PROJECT SUCCESS METRICS

**You'll know you've succeeded when:**

✅ Both projects are fully functional and documented  
✅ You can demo each project live without errors  
✅ Projects are containerized with Docker  
✅ Code is clean, commented, and professional quality  
✅ You have demo videos or presentations for each  
✅ Your Elevance Health colleagues recognize the value  
✅ You can confidently discuss technical decisions in university interviews  
✅ Projects are mentioned prominently in your Statement of Purpose  
✅ Your manager can cite these projects in recommendation letter

**By August 2026, you'll have two substantial, impressive projects that set you apart from other applicants who only have academic coursework. These projects, combined with AWS certification, strong IELTS score, and successful APS interview, create a compelling narrative: you're not just a student seeking education, you're an engineer actively pushing boundaries of what's possible with modern AI technology while solving real business problems. That's exactly what German universities want to admit.**

---

This project roadmap integrates seamlessly with your daily study schedule. Weekends are dedicated primarily to hands-on building, weekdays to foundational learning (AWS, German, algorithms, APS prep). By carefully sequencing when you learn prerequisite knowledge and when you apply it in projects, you maximize learning retention and build genuine expertise rather than superficial familiarity.
