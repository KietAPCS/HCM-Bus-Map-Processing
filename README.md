# Graph API

## Overview
This project provides a command-line interface for interacting with a transportation graph, enabling users to explore paths, shortest routes, and important stops. The graph is built using data from JSON files, and Dijkstra's algorithm is used for shortest path calculations.

## Features
- **Find Paths:** Retrieve all possible paths between two stops, including time, distance, and route details.
- **Shortest Path for All Pairs:** Compute and save the shortest paths between all stops using Dijkstra's algorithm.
- **Shortest Path for Two Stops:** Find the shortest path between a specific start and end stop.
- **Top 10 Important Stops:** Display the most important stops based on predefined criteria.
- **View All Edges:** Display all edges in the graph along with time, distance, and route information.

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/yourrepository.git
   cd yourrepository
   ```
2. Install dependencies (if any are required):
   ```bash
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
├── vars.json        # Stop and path variables
├── stops.json       # Stop data
├── paths.json       # Path data
├── main.py          # Entry point for the application
├── requirements.txt # Dependencies (if applicable)
└── README.md        # Project documentation
```

## Contributing
Feel free to fork this repository and submit pull requests with improvements or bug fixes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author
[Your Name](https://github.com/yourusername)

## Acknowledgments
- [Dijkstra's Algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) for shortest path computation.
- Open-source community contributions.

