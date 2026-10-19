# Day 1: The Black Box & Observability

## Concept Learned
Design for Debug (DFD) is about adding observability and controllability to a system so we can isolate failures quickly without destroying or re-designing the hardware.

## The Puzzle
In a chain of 3 components (Input -> A -> B -> C -> Output), the signal fails to reach Output. I am allowed to check only ONE internal node first.

## My Answer & Reasoning
* **Where I probed first:** Between Component B and Component C.
* **My Reason:** If the signal passes through A and B successfully to reach this point, then Component C must be the broken component preventing the output. If no signal reaches here, Component C is eliminated as the cause, narrowing the fault down to A or B.
