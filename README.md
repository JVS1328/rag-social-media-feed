# RAG-based Social Media Feed Generator for Fictional Universes

A Retrieval-Augmented Generation system that creates contextually accurate social media feeds for characters in fictional universes by leveraging knowledge graph relationships.

## Overview

This project demonstrates the implementation of a RAG system that:
1. Automatically generates and expands fictional universes from basic prompts
2. Creates interconnected knowledge graphs of characters, locations, events, and items
3. Uses these relationships to generate contextually relevant social media posts that maintain consistency with the universe's lore

The system demonstrates how vector embeddings and knowledge graphs can be used to provide relevant context to language models, resulting in more coherent and consistent outputs.

## Features

- **Automated Universe Generation**: Creates detailed fictional universes from just a name input
- **Knowledge Graph Construction**: Builds rich interconnected networks of entities and relationships
- **Vector-based Retrieval**: Uses FAISS and sentence embeddings for semantic search
- **Contextual Content Generation**: Produces social media posts that reference universe-specific knowledge
- **Visual Knowledge Graph**: Interactive visualization of entity relationships
- **User Interface**: Simple UI for universe creation and feed generation

## Technical Architecture

![RAG Architecture](https://i.imgur.com/XYZabc.png)

The system is built on these key components:

1. **Knowledge Graph Module**
   - Entity and Relationship models using Pydantic
   - NetworkX-based graph storage and traversal
   - Relationship generation between entities

2. **Vector Store**
   - FAISS-based vector database for semantic search
   - Entity and relationship embeddings using sentence-transformers
   - Context retrieval based on entity relationships

3. **RAG Pipeline**
   - Prompt templates optimized for contextual generation
   - Hugging Face transformers for text generation
   - Entity reference tracking in generated content

4. **Social Media Models**
   - User profile generation
   - Post formatting and display
   - Feed creation and chronological ordering

## Installation

```bash
# Clone repository
git clone https://github.com/JVS1328/rag-social-media-feed.git
cd rag-social-media-generator

# Install dependencies
pip install -r requirements.txt
```

Requirements:
- Python 3.8+
- langchain
- llama-cpp-python
- faiss-cpu
- sentence-transformers
- transformers
- torch
- networkx
- pyvis
- tqdm
- pydantic

## Usage

### Running via Jupyter Notebook

1. Launch the notebook:
```bash
jupyter notebook RAG_Social_Media_Feed_Generator.ipynb
```

2. Run the provided examples or create your own universe:

```python
# Create a new universe
universe = create_universe_from_name("Your Universe Name", auto_populate=True)

# Generate a social media feed
feed = generate_demo_feed(universe, num_posts=8)

# Visualize the knowledge graph
visualize_universe(universe)
```

### Using the Interactive UI

Execute the cell containing `create_universe_ui()` to launch the interactive interface with:
- Universe creation controls
- Entity count adjustments
- Feed generation options
- Knowledge graph visualization

## Example Output

The system generates social media posts like:

```
@elven_warrior42
Just spent the morning training with the Knights of Azura. Severian's sword skills 
have improved dramatically, but I still managed to best him in three out of five duels. 
The Blackforge blade that Master Thorne gifted me has proven its worth. Meeting at 
the Crystal Tower tonight to discuss the approaching shadow from the Northern Wastes.
❤️ 327 | 🔄 45 | 💬 18
```

Each post maintains consistency with the established universe lore and references other entities within the knowledge graph.

## Technologies Used

- **LangChain**: Framework for LLM application development
- **Hugging Face Transformers**: Text generation models (Phi-2)
- **FAISS**: Vector similarity search library
- **NetworkX**: Graph representation and manipulation
- **Pydantic**: Data validation and modeling
- **PyVis**: Interactive knowledge graph visualization

## Future Improvements

- Multi-universe cross-referencing for mashup content
- Fine-tuning of models on specific fictional universes
- Character conversation threads with realistic interactions
- Addition of image generation for visual content
- Expanded entity types and relationship models
- Persistent storage for generated universes

## License

MIT

## Author

John Skorcik - CSCI 539 Final Project
