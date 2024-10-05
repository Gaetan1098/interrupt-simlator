markdown
# Interrupt Simulator

This project simulates an interrupt-driven CPU, focusing on how different types of work (CPU execution, I/O, system calls, and overhead) are handled in an operating system environment. It parses execution logs and analyzes the time spent on each type of work to calculate ratios and performance metrics, providing a comprehensive view of how interrupts affect system performance.

## Table of Contents
- [Overview](#overview)
- [Project Structure](#project-structure)
- [Key Components](#key-components)
- [Techniques Used](#techniques-used)
- [How to Run](#how-to-run)
- [Skills Demonstrated](#skills-demonstrated)
- [Debugging Techniques](#debugging-techniques)
- [Contact](#contact)

## Overview
The interrupt simulator models how a CPU interacts with interrupts, system calls, and I/O events during execution. The project includes:
1. **Interrupt Handling Simulation** - Written in C, it processes trace files that describe a sequence of CPU instructions, system calls, and I/O events.
2. **Log Analysis** - A Python script analyzes the simulator's execution logs and calculates the CPU, I/O, and overhead ratios, exporting the results to an Excel sheet.
3. **Automation** - Shell scripts compile and run the simulator with different trace files, allowing for easy testing and data generation.

## Project Structure

```
|-- interrupts.c            # Main simulator code in C
|-- interrupts.h            # Header file for simulator
|-- execution_analyzer.py    # Python script for log analysis
|-- trace1.txt              # Sample trace file
|-- execution1.txt          # Sample execution log file
|-- execution1_summary.xlsx  # Example output Excel summary
|-- test1.sh                # Shell script to run the simulator with trace1.txt
```

## Key Components

### 1. **interrupts.c & interrupts.h**
These files form the core of the simulator:
- **`interrupts.c`** handles the interrupt simulation by parsing a trace file, which lists the events (e.g., CPU execution, system calls, I/O events). The simulator tracks the time spent on each event type.
- **`interrupts.h`** contains function declarations and constants used in the simulator.

### 2. **execution_analyzer.py**
This Python script processes the log generated by the interrupt simulator:
- **Log Parsing**: Extracts time, duration, and action from the log file (e.g., `execution1.txt`).
- **Classification**: Categorizes each action as CPU work, I/O work, or overhead.
- **Analysis**: Computes total time spent in CPU work, I/O work, and overhead, then calculates the ratio for each.
- **Output**: Exports the results into an Excel file (e.g., `execution1_summary.xlsx`).

### 3. **Trace Files (trace1.txt)**  
Trace files provide the input for the simulator, listing sequences of CPU, system calls, and I/O events, along with their durations.

### 4. **Shell Scripts (test1.sh)**
These scripts automate the process of compiling and running the simulator with a specific trace file.

## Techniques Used

- **Interrupt Handling in C**: Demonstrates handling of interrupts, system calls, and I/O events.
- **File Parsing in Python**: Python’s regular expressions are used to parse execution logs and extract relevant details.
- **Excel File Generation**: `pandas` and `openpyxl` are used to generate detailed performance reports in Excel format.
- **Shell Scripting**: Automates the process of compiling and running the simulator for different trace files.

## How to Run

### Running the Interrupt Simulator

1. **Compile the Simulator**:
   Use the provided `test1.sh` to compile and run the simulator with the sample trace file:
   ```bash
   bash test1.sh
   ```
   This will produce an execution log (e.g., `execution1.txt`), showing a sequence of CPU operations, system calls, and I/O interactions.

2. **Analyzing the Execution Log**:
   Run the Python analysis script to generate a report:
   ```bash
   python execution_analyzer.py execution1.txt execution1_summary.xlsx
   ```

## Skills Demonstrated

- **Systems Programming**: Simulated interrupt handling in C.
- **File I/O and Parsing**: Handled trace and log files in both C and Python.
- **Data Analysis**: Generated performance reports using Python libraries.
- **Automation with Shell Scripting**: Automated compilation and execution.

## Debugging Techniques

1. **Print Statements**: Traced the flow of the program by printing key variables like time and action.
2. **Regex Debugging**: Printed lines before and after regex matching to adjust patterns for better parsing.
3. **Conditional Debugging**: Verified specific program branches, such as event categorization, with conditionals.
4. **Zero-Division Handling**: Ensured edge cases like zero `total_time` were handled gracefully to avoid errors.
5. **Manual Testing**: Tested different trace files to ensure correct parsing and categorization of log data.
6. **Cross-Referencing Outputs**: Verified simulator and analysis script outputs were consistent with input trace files.

## Contact

Feel free to reach out if you have any questions or suggestions for improvements!
