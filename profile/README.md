# Lucidity GitHub Repository Overview

Welcome to Lucidity's GitHub organization! This repository ecosystem has been meticulously designed to separate concerns, modularize functionalities, and streamline workflows for efficient development and scalability. Below, we outline the purpose, structure, and operational philosophy behind our repository organization.

---

## Repository Structure

### 1. **Model Pipelines (`model-*` Repositories)**
These repositories focus on:
- Training and inference pipelines for machine learning models.
- Consuming prepared datasets for model-specific requirements.
- Generating predictions, insights, and analytical outputs.

### 2. **Data Fetching Pipelines (`data-*` Repositories)**
These repositories are dedicated to:
- Fetching structured and unstructured data from various sources.
- Processing and cleaning data to ensure high quality.
- Dumping processed data into GCP buckets for downstream consumption.

### 3. **Vectorization Pipelines (`vectors-*` Repositories)**
These repositories are responsible for:
- Converting raw or processed data into vectorized formats suitable for machine learning.
- Generating embeddings and other representations required for specific models.

### 4. **Automation Pipelines** (Planned Addition)
These pipelines will focus on:
- **Generic Model Training Pipelines:** Streamlining the development of training workflows for various machine learning models.
- **Continuous Retraining Pipelines:** Automating retraining processes to ensure models remain updated with the latest data.
- **Architecture Research Pipelines:** Facilitating automated experimentation with model architectures to discover optimal configurations.

---

## Key Design Principles

### 1. **Separation of Concerns**
The data fetching pipelines operate independently of the model training pipelines. This decoupling ensures:
- **Flexibility:** Data pipelines do not need to adapt to specific model requirements.
- **Reusability:** Different models can leverage the same data-fetching infrastructure.
- **Scalability:** Individual pipelines can scale or evolve without disrupting other systems.

### 2. **Unified Coordination Layer** (Planned Addition)
We are developing a coordination service that will:
- Sit on top of individual data-fetching pipelines.
- Index and track key metadata, including unique columns, feature IDs, and schema details.
- Enable model pipelines to directly interact with this layer to dynamically prepare their training datasets.

This service will act as the bridge between data-fetching and model-training pipelines, further enhancing modularity and efficiency.

---

## Development Workflow

### Data Fetching Pipelines
- **Purpose:** Pull data from diverse sources (structured and unstructured).
- **Outputs:** Processed data stored in GCP buckets.
- **Key Features:** Each pipeline operates independently, focusing solely on its source and preprocessing logic.

### Model Pipelines
- **Purpose:** Train, validate, and deploy machine learning models.
- **Inputs:** Leverage datasets prepared via the coordination layer.
- **Key Features:** Modular design to enable seamless integration of new datasets and features.

### Coordination Service (Planned)
- **Purpose:**
  - Provide a centralized metadata layer.
  - Simplify dataset preparation for models.
- **Key Features:** Tracks schema details, ensures consistency across pipelines, and reduces redundancy.

---

## Future Plans

1. **Enhanced Data Indexing:**
   - Comprehensive tracking of feature IDs, schemas, and unique columns.
   - Integration of versioning to maintain data lineage.

2. **Standardized APIs:**
   - Unified APIs for data access across models.
   - Streamlined interaction between pipelines and coordination layers.

3. **Scalability:**
   - Scaling data-fetching pipelines for increased throughput.
   - Enhancing model pipelines for distributed training and inference.

4. **Automation Pipelines:**
   - Implementation of generic model training pipelines.
   - Establishing continuous retraining workflows for improved model lifecycle management.
   - Introducing automated architecture research for systematic experimentation.

5. **Documentation and Transparency:**
   - Detailed READMEs and onboarding guides for all repositories.
   - Continuous updates to reflect changes in architecture and workflows.

---

## Contribution Guidelines
We encourage contributions from developers, data scientists, and researchers! Please refer to the `CONTRIBUTING.md` file in each repository for specific guidelines, or reach out to our team via issues or discussions for support.

---

## Contact Us
For any queries, feel free to create an issue in the respective repository or contact our team directly. We're always happy to collaborate and improve our systems!
