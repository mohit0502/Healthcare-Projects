# Healthcare-Projects
Code base which has EDA and processing of EHR data
This notebook processes structured data from the NACC (National Alzheimer's Coordinating Center) dataset. It includes data loading, cleaning, transformation, and preparation steps intended for downstream machine learning or knowledge graph creation tasks.

# NACC_data.ipynb

## Key Features
- Loads and explores the NACC dataset
- Performs null value checks and metadata extraction
- Prepares a JSON dictionary of cleaned column descriptions
- Cleans and standardizes column names and values
- Outputs a cleaned DataFrame ready for integration into a Neo4j graph or RAG pipeline

## Usage
1. Place the NACC raw data CSV files in the appropriate directory.
2. Run the notebook step-by-step to preprocess the data.
3. Export the final cleaned dataset or metadata dictionary for further use.

## Requirements
- Python 3.8+
- pandas
- json
- numpy

## Output
- `finaldict_cleaned_v2.json`: Cleaned data dictionary
- A preprocessed DataFrame for structured analysis or graph creation

# NACC-graph.ipynb

## Overview
This notebook focuses on transforming cleaned NACC structured data into a Neo4j-compatible graph schema. It defines nodes, relationships, and properties for representing Alzheimer's patient data as a knowledge graph.

## Key Features
- Loads cleaned NACC structured data and dictionary
- Defines graph schema including nodes like `Patient`, `Visit`, and `Symptom`
- Uses Py2Neo or Neo4j driver to construct and push nodes/edges
- Embeds metadata and column descriptions into graph node properties

## Usage
1. Ensure Neo4j is running locally or accessible remotely.
2. Connect to the Neo4j database using authentication credentials.
3. Run each section of the notebook to build the graph.
4. Validate graph creation with Cypher queries.

## Requirements
- Python 3.8+
- pandas
- py2neo or neo4j
- json

## Output
- A populated Neo4j graph database with patient and clinical visit data
- Embedded metadata for better interpretation of nodes and relationships

# GraphRAG_setup.ipynb

This notebook, is a **Proof of Concept (POC)** for setting up a Graph-based Retrieval-Augmented Generation (RAG) architecture. The goal of this POC is to demonstrate the feasibility of integrating a Knowledge Graph with RAG workflows for enhanced automated structured data retrieval.

## Purpose

- To initialize and configure the components necessary for GraphRAG.
- To explore basic integrations between graph databases and LLM-based retrieval mechanisms.
- To provide a sandbox environment for testing GraphRAG queries and document retrieval workflows.

## `GraphRAG_setup.ipynb` includes:
- Graph database initialization.
- Sample schema creation for nodes and relationships to mimic the actual graph.
- Querying and retrieval experiments to test the integration.
- Llama and deepseek connection setup.

## Requirements
- Python 3.9+
- Neo4j or AuraDB
- LangChain 
- Ollama for deepseek, Hugging Face for Llama
- Additional libraries as imported in the notebook (e.g., pandas, py2neo, etc.)
