# CntxtPY Project Architecture

## Overview
CntxtPY is a Python codebase analyzer that generates comprehensive knowledge graphs optimized for LLM context windows. The project consists of a main analyzer module and several specialized regex-based component modules for extracting different types of information from Python codebases.

## Core Components

### Main Module (CntxtPY.py)
- Primary class: `PythonCodeKnowledgeGraph`
- Orchestrates the analysis process
- Manages the knowledge graph construction
- Integrates all component analyzers
- Handles file processing and graph serialization

### Component Architecture
The project follows a modular design with specialized components for different analysis tasks:

#### Code Analysis Components
1. **CodeIdentifierExtractor**
   - Extracts classes, functions, methods, and variables
   - Handles type hints and decorators
   - Processes docstrings and code structure

2. **CommentProcessor**
   - Processes inline comments, TODOs, and FIXMEs
   - Handles docstring extraction
   - Manages comment categorization

3. **LoggingAnalyzer**
   - Identifies logging statements
   - Maps logging levels
   - Extracts log message patterns

#### Configuration Analysis
1. **BuildConfigExtractor**
   - Processes build configuration files
   - Extracts package metadata
   - Handles CI/CD configurations

2. **ConfigFileParser**
   - Parses various config file formats
   - Handles environment variables
   - Processes INI, YAML, and other formats

3. **VersionAnalyzer**
   - Extracts version constraints
   - Handles deprecation warnings
   - Manages Python version compatibility

#### Dependency Analysis
1. **DependencyMapper**
   - Maps project dependencies
   - Processes requirements files
   - Handles package management files

#### Integration Analysis
1. **IntegrationMapper**
   - Identifies external integrations
   - Maps API endpoints
   - Tracks service connections

#### File Processing
1. **FileTypeProcessor**
   - Determines file types
   - Handles encoding detection
   - Maps file purposes

2. **LocalizationProcessor**
   - Processes localization files
   - Handles translations
   - Manages locale detection

3. **DocumentationAnalyzer**
   - Analyzes documentation files
   - Processes markdown and RST
   - Tracks documentation coverage

## Data Flow
1. Main analyzer walks through codebase
2. Files are categorized and routed to appropriate processors
3. Components extract relevant information
4. Data is integrated into knowledge graph
5. Graph is serialized and compressed

## Compression System
- Implements efficient graph compression
- Uses abbreviation mapping
- Maintains data relationships
- Optimizes for LLM context windows

## Output Format
The system generates:
1. JSON knowledge graph
2. Compressed graph format
3. Optional visualization
4. GraphML export capability

## Key Features
- Comprehensive code analysis
- Modular component architecture
- Efficient graph compression
- Multiple output formats
- Visualization capabilities
- Documentation coverage tracking

## Usage
```python
# Initialize analyzer
graph_generator = PythonCodeKnowledgeGraph(directory=codebase_dir)

# Analyze codebase
graph_generator.analyze_codebase()

# Save results
graph_generator.save_graph(output_file)

# Optional visualization
graph_generator.visualize_graph()
```

## Dependencies
- NetworkX for graph operations
- Matplotlib for visualization
- YAML/TOML parsers
- Chardet for encoding detection

## Future Considerations
- Additional file type support
- Enhanced integration detection
- Expanded compression options
- More visualization formats
