# CourseSelector

CourseSelector is a C++17 schedule optimizer that finds compact sets of UC Merced courses satisfying multiple general-education requirements. It uses breadth-first search and hash-based state tracking to explore possible schedules while discarding duplicate or suboptimal combinations.

## Engineering highlights

- Parses requirement and course data from plain-text inputs
- Finds courses that satisfy multiple requirements simultaneously
- Uses breadth-first search to identify schedules with the fewest courses
- Tracks explored schedules with hash-based data structures to avoid duplicate work
- Reports execution time and writes the best alternatives to `best_schedules.txt`

## Features
- **Requirement Parsing**: Reads and processes UC Merced's General Education requirements from input files.
- **Course Selection**: Identifies courses that fulfill multiple requirements and ensures the most efficient schedule.
- **Schedule Optimization**: Outputs the optimal and alternative schedules based on the courses selected.
- **Duplicate Prevention**: Eliminates duplicate or suboptimal schedules to ensure clarity.
- **Performance Metrics**: Displays execution time for the algorithm to highlight efficiency.

## How It Works
#### Workflow
- **Input Requirements**: A list of requirements is read from files, and their metadata is extracted.
- **Course Database**: Builds a database of all courses and their associated requirements.
- **Schedule Generation**:
  - Starts with an empty schedule.
  - Iteratively adds courses, ensuring that no duplicate requirements are fulfilled unnecessarily.
- **Optimization**: Compares all potential schedules to find the one that satisfies all requirements with the least number of courses.
- **Output Results**:
  - Prints optimal schedules to the console.
  - Saves the best schedules to a file named best_schedules.txt.
  
## Installation and Usage
#### Requirements
- A C++ compiler that supports C++17 or later.
- Input files structured with the UC Merced general education requirements and courses.
  - (Can be copied and pasted directly from the UC Merced Gen Ed. Requirement Listing website)
#### Compilation
- Build with the included Makefile:

```bash
make
```

#### Running the program

```bash
./courseSelector
```

Place input files in the same directory or provide paths in the code.

#### Example Output
`best_schedules.txt:`
```
Optimal schedule found with 2 courses.
Courses:
COURSE101
COURSE102
----------------------------------------
```

## Performance
The algorithm is designed to handle large input files efficiently by leveraging breadth-first search and hash-based tracking of unique schedules. Execution time is logged for performance monitoring.

## Future Improvements
- **GUI Integration**: Provide a user-friendly interface for course selection.
- **Dynamic Input Parsing**: Support for real-time requirement updates.
- **Advanced Optimization**: Incorporate additional constraints like time slots and prerequisites.

## License
This project is licensed under the Apache License 2.0. See `LICENSE` for details.
