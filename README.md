# Turbocharging Treewidth Heuristics: PACE 2016 Submission

Contributors: Serge Gaspers, Joachim Gudmundsson, Mitchell Jones, Julian Mestre, Stefan Rummele.

This source code is distributed under the open source [MIT](https://opensource.org/licenses/MIT) license.

## Running the code

1) Compile with `make`.

2) Run the code by using the `tw-heuristic` script (may need to `chmod` beforehand to give executable permissions).

This script accepts one argument.

    ./tw-heuristic -s [seed]

where `[seed]` is a given seed. If nothing is given, a seed will be randomly generated and used. All instance data is passed via `stdin`, and output is printed to `stdout`.

3) Test it with an example.

    ./tw-heuristic -s 4321 < example.gr

This will output a tree decomposition.

    s td 5 2 5
    b 1 2 1
    b 2 3 2
    b 3 4 5
    b 4 3 4
    b 5 3
    1 2
    3 4
    2 5
    4 5

4) At any time you can send the script a UNIX signal to get a status update. On `SIGUSR1`, the process will output the size of the largest bag in the best tree decomposition found so far. This can be triggered with

    kill -SIGUSR1 [pid]

where `[pid]` is the pid of the script `tw-heuristic` (not the Java process running in the background).

Similarly, you can terminate the program and immediately print out the best tree decomposition found by sending a `SIGTERM` with

    kill -SIGTERM [pid]

Note: Requires Java 7 or higher.
