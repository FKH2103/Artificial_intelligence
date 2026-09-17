# AI CA2: Genetic Algorithms & Minimax

This repository contains two distinct Artificial Intelligence implementations developed for Computer Assignment 2 (Genetic and Games Algorithm). It features a Genetic Algorithm designed to automatically solve scrambled Jigsaw puzzles, and a Minimax agent built to play the classic Dots and Boxes game.

## Genetic Algorithm: Jigsaw Solver
*   **Fitness Evaluation:** Calculates the Sum of Squared Differences (SSD) of pixel values along the horizontal and vertical edges of adjacent pieces to measure dissimilarity, defining fitness as the inverse of this total dissimilarity score.
*   **Selection Mechanisms:** Implements both Roulette Wheel Selection (using cumulative probabilities) and Tournament Selection to effectively balance selection pressure and maintain genetic diversity.
*   **Permutation Crossover:** Utilizes a custom priority-based crossover managed via a Min-Heap (`heapq`), prioritizing "Shared Pieces" and "Buddy Pieces" to seamlessly build valid chromosome permutations without missing or duplicate pieces.
*   **Mutation:** Applies a Swap Mutation operator uniquely tailored for permutation problems to prevent premature convergence and help the algorithm escape local optima.

## Adversarial Search: Dots & Boxes
*   **Agent Architecture:** Deploys a `MinimaxAgent` to navigate the game tree, aiming to maximize the agent's score difference while minimizing the opponent's scoring opportunities.
*   **Alpha-Beta Pruning:** Integrates Alpha-Beta pruning to systematically eliminate irrelevant decision branches, drastically reducing the computational cost at deeper search horizons.
*   **Heuristic Evaluation & Move Ordering:** Evaluates non-terminal states based on score differentials and near-filled boxes. It highly enhances pruning efficiency by ordering moves contextually: completing moves first, followed by safe moves, and finally risky moves.

## Experimental Results
*   **Jigsaw Convergence:** Empirical tests on resolutions from 32x32 to 128x128 demonstrate that larger piece sizes and higher generation limits improve puzzle accuracy, though requiring a balance to optimize runtime. The algorithm struggles on uniform patterns (like chessboards) due to flat fitness landscapes offering no clear gradient for selection.
*   **Minimax Efficiency:** The integration of Alpha-Beta pruning reduced evaluated nodes by approximately 98% at Depth 4, accelerating execution speeds by 50x compared to standard unpruned Minimax.
*   **Optimal Depth Trade-off:** Depth 4 provides the optimal balance of precision and sub-second decision-making efficiency on a 6x6 grid, while higher depths (Depth 6) become computationally expensive despite optimization techniques.

**Author:** Faezeh Khanmohammadi
