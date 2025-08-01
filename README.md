# achs2025_Spring
Code samples for Spring 2025 ACHS meeting. Includes Python, Go, and Rust samples.

## Python 
Multiple scripts for different purposes.

### approach1.py
Basic approach of illustration tool that sources a few rates from files and dumps out a Python dictionary

Stripping out docstrings, output (and related data capturing), and hardcoding rates would result in a much small set of instructions which might be a good place to start and then "build" up to this

Run a simple case by running the script from the command line. Update parameters at bottom of script as desired.
```
python approach1.py
```

### approach2.py
One object-oriented implementation

Create a UniversalLifePolicy by combining an Insured and a concrete implementation of a UniversalLifeProduct.

User would subclass UniversalLifeProduct or any concrete implementations to add new products

Run a simple case by running the script from the command line. Update parameters at bottom of script as desired.
```
python approach2.py
```

#### Insured class
Simple data structure for housing a few variables

#### UniversalLifeProduct
Abstract class for universal life products

Requires subclassing and concrete implementations for 
- product_rates_for_policy() --> should return a dictionary of rates that will be used by _monthly_processing
- _monthly_processing() --> rollforward mechanics for a single month

#### Product1
Concrete implementation, adds a few protected utility functions to gather rates from files and make product_rates_for_policy() easier to reason through

#### UniversalLifePolicy
Basically a wrapper class that helps simplify usage but relying solely on expected public methods of Insured and UniversalLifeProduct (and subclasses)

### mp_1.py
Multiprocessing example leveraging approach1.py

Run a simple case from the command line
```
python mp_1.py
```

### profiler.py
Speed profiling for appraoch1 and approach2 for both illustrations and premium solves

Comment / uncomment the test() calls as desired and run using the following command within the directory
```
python profiler.py
```

### app_old.py
Example shiny app #1 generated from an LLM prompt. See file for more details

### app.py
Expanded shiny app

## Go
### approach1.go
Functional / procedural implementation similar to approach1.py

single() and multi() are wrappers for speed tests. Adjust # workers (goroutines) in multi() as desired -- does not really correspond to # cores

Adjust case parameters as desired and move rates initialization in/out of loop for various tests.

Run from command line
```
go run .
```


## Rust
Contained within Rust subdirectory

### main.rs
Within rust/src this is the main execution file that implements process similar to approach1.py

Use cargo in parent directory (e.g. /rust) to build/run the code

May require download of C++ build tools