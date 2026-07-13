# Snowflake-Data-Warehousing-Workshop-Badge

📁 snowflake-badge-challenges
 └── 📁 badge-1-data-warehousing
      ├── 📁 01-setup-and-stages        # DORA validations, account admin tools, external stages (S3)
      │    ├── DORA_CHECKS_BADGE_1.sql
      │    └── Untitled.sql
      ├── 📁 02-garden-plants           # Core relational data warehousing & spinach tracking structures
      │    └── GARDEN_PLANTS_BADGE_1.sql
      ├── 📁 03-library-card-catalog    # Sequences, 3NF structures, semi-structured JSON ingestion
      │    ├── LIBRARY_CARD_CATALOG_BADGE_1.sql
      │    └── SEQ_AUTHOR_UID.sql
      ├── 📁 04-social-media-floodgate  # Flattening arrays, VARIANT data parsing, and normalized views
      │    └── SOCIAL_MEDIA_FLOODGATE.sql
      └── 📁 05-notebooks               # UI and advanced analytics scripts
           └── UNCLE_YER.ipynb


--  🛠️ KEY TECHNICAL CONCEPTS DEMONSTRATED
1. Through this badge, I implemented and mastered the following Snowflake features:
2. API Integration & External Verification: Designed and deployed functional API integrations (dora_api_integration) using AWS API Gateways to dynamically grade structural accuracy via Snowflake external functions.
3. Custom File Format Ingestion: Architected tailored file schemas including pipe-delimited (|) file formats with custom header skipping (PIPECOLSEP_ONEHEADROW) and tab-delimited (\t) parameters with error mismatch safety boundaries.
4. Advanced Semi-Structured Processing: Loaded raw text and JSON arrays into structured VARIANT columns, applying explicit casting rules (e.g., ::STRING, ::VARCHAR) to strip schema complexity on the fly.
5. Relational Data Modeling (3NF): Designed many-to-many lookup junction tables mapping complex entities together, backed by auto-incrementing identity values and centralized structural sequences.  JSON Array Flattening & Decoupling: Mastered nested object extraction using both LATERAL FLATTEN constructs and TABLE(FLATTEN()) wrappers to decouple array elements into analytical view layers.  


📖 Module Breakdowns

-- 🎛️ 01. SETUP AND STAGES

Focus: Establishing the environment baseline and connecting to cloud storage.
Implementation:
Configured compute resources and logical database structures.
Created file formats (CSV, JSON) and established External Stages pointing to S3 infrastructure.
Executed programmatic API validations via Snowflake’s automated DORA Check scripts to confirm architectural compliance.
Created the foundational administrative containers (DEMO_DB, UTIL_DB) and built the programmatic grader framework using api_provider = aws_api_gateway to verify 19 distinct compliance steps across multiple structural variations.  

🌿 02. GARDEN_PLANTS

Focus: Relational modeling and structured file ingestion.
Implementation:
Built structured tables to ingest agricultural/plant data.
mplemented targeted schemas (VEGGIES, FRUITS, FLOWERS) under a unified catalog.
Configured file loaders to process stage sources (VEG_NAME_TO_SOIL_TYPE_PIPE.txt) using dynamic column overrides. 
Applied analytic functions like QUALIFY ROW_NUMBER() OVER (PARTITION BY ...) to handle duplicate input payloads natively inside target warehouse sets.  

📚 03. LIBRARY_CARD_CATALOG

Focus: Sequence generation and working with semi-structured JSON payloads.
Implementation:
Created global sequences (SEQ_AUTHOR_UID) to automatically handle surrogate key generation across multi-table inserts.
Built an ingestion pipeline to load raw author and book catalogs directly into raw VARIANT storage columns.
Transitioned flat structures into efficient 3rd Normal Form (3NF) structures using SQL casting.

🌊 04. SOCIAL_MEDIA_FLOODGATE

Focus: ELT (Extract, Load, Transform) on streaming-style nested JSON data.
Implementation:
Handled deep-nested JSON payloads representing rapid social media feeds.
Mastered the use of FLATTEN to break down multi-layered arrays into distinct relational rows.
Built clean, optimized secure VIEWS over the raw variant tables, allowing downstream BI analysts to query JSON data using standard, high-performance ANSI SQL.

📓 05. NOTEBOOKS AND ADVANCED ANALYTICS

Focus: Blending programmatic analysis with standard SQL workflows.
Implementation:
Leveraged Snowflake's UI capabilities to execute advanced analytics on the processed badge data.
Documented EDA (Exploratory Data Analysis) paths to verify the cleanliness of the data processed throughout the previous modules.

🚀 HOW TO RUN THESE SCRIPTS
Prerequisites: You will need an active Snowflake account (Trial or Enterprise) with permissions to assume the SYSADMIN and ACCOUNTADMIN roles for the initialization steps.
Execution Order: Step through the folders sequentially).
Context Configuration: Ensure your worksheet context is correctly set to the target database and warehouse defined in the 01-setup-and-stages files before running downstream DDL/DML.

🏆BADGE COMPLETION
Snowflake Badge 1: Data Warehousing Collaboration (Issued by Snowflake via Acclaim/Credly)
