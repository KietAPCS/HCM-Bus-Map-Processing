# README: AI-Powered Graph Query System

## Overview
This project provides a command-line interface for exploring a transportation graph, allowing users to query bus stops, routes, and shortest paths. The graph is built using data from JSON files, and Dijkstra's algorithm is used for shortest path calculations. Additionally, it integrates an AI-powered system that leverages a hosted Large Language Model (LLM) from the Gorilla server to process natural language queries and convert them into function calls.

## Features
- Query information about stops, routes, and paths
- Find all possible paths between two stops, including time, distance, and route details
- Compute and save shortest paths between all stops using Dijkstra's algorithm
- Find the shortest path between two specific stops
- Retrieve the top ten most important stops in the graph
- Utilize AI to interpret and respond to user queries

## LLM Integration
This project uses the `gorilla-openfunctions-v1` model hosted at `http://luigi.millennium.berkeley.edu:8000/v1`. The AI model:
- Processes user queries and determines the appropriate function to call
- Extracts relevant parameters from user input
- Provides structured responses based on predefined function definitions

### LLM API Usage
The project communicates with the Gorilla model using OpenAI's API structure:
```python
completion = openai.ChatCompletion.create(
    model="gorilla-openfunctions-v1",
    temperature=0.0,
    messages=[{"role": "user", "content": prompt}],
    functions=functions,
)
response = completion.choices[0].message.content
```

### Error Handling
If the LLM encounters an issue, the `raise_issue` function generates an error report link to the Gorilla GitHub repository, enabling users to log issues efficiently.

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/KietAPCS/HCM-Bus-Map-Processing.git
   cd HCM-Bus-Map-Processing
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

## Usage
Run the script in a Python environment:
```bash
python main.py
```
Follow the on-screen menu to interact with the graph API.

### Menu Options
| Option | Description |
|--------|-------------|
| 1 | See all paths from one StopID to another, including time, distance, and route details. |
| 2 | Compute and save shortest paths between all StopIDs using Dijkstra's algorithm. |
| 3 | Find the shortest path between a specific start and end StopID. |
| 4 | Display the top 10 most important stops in the graph. |
| 5 | List all edges in the graph (Warning: Large data output). |
| 6 | Exit the program. |

## File Structure
```
.
├── graph2.py        # Graph implementation
├── var.py           # Variables and constants
├── stop.py          # Stop-related functions
├── path.py          # Path-related functions
├── llm.py           # LLM query processing
├── vars.json        # Stop and path variables
├── stops.json       # Stop data
├── paths.json       # Path data
├── main.py          # Entry point for the application
├── requirements.txt # Dependencies
└── README.md        # Project documentation
```

## Future Improvements
- Enhance natural language understanding for more complex queries
- Optimize shortest path calculations
- Improve response time by caching frequent queries

## Contributing
Feel free to fork this repository and submit pull requests with improvements or bug fixes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author
[KietAPCS](https://github.com/KietAPCS)

## Acknowledgments
- [Dijkstra's Algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) for shortest path computation.
- Open-source community contributions.
