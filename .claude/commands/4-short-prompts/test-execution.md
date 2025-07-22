Create the tests in a tests/ directory
Always “mock” calls to services like the DB and LLM so you aren’t interacting with anything “for real”.
For each function, test at least one successful scenario, one intentional failure (to ensure proper error handling), and one edge case.
