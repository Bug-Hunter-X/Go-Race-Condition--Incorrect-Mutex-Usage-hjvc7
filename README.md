# Go Race Condition: Incorrect Mutex Usage

This repository demonstrates a common race condition in Go that can occur when using mutexes. The program attempts to increment a counter in a concurrent manner, using a mutex to protect the counter from race conditions. However, due to an error in how the goroutines are launched, the race condition still occurs.

## Bug Description
The bug is present in the `main` function of the `bug.go` file.  A race condition occurs because the goroutines might access and modify the `count` variable concurrently. Even though a mutex is used to protect this variable, the way in which goroutines are handled is faulty which can still cause errors. This code might compile but will not produce consistent results.

## Solution
The solution is provided in the `bugSolution.go` file. It demonstrates the correct way to handle the `count` variable in order to prevent race conditions from occurring.

## How to Run
1. Clone the repository.
2. Navigate to the repository's directory.
3. Run `go run bug.go` to observe the bug.
4. Run `go run bugSolution.go` to observe the solution.
