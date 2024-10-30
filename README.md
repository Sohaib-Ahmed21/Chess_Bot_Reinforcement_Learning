# Chess_Bot_Reinforcement_Learning
### **Summary of Chess Bot Implementation**

1. **Environment**: Used the `python-chess` library for board creation, move validation, checkmate detection, and FEN parsing. 

2. **Initial Approach**:  
   - Attempted to implement a Monte Carlo Tree Search (MCTS) from scratch by generating random moves.
   - Created a `TreeNode` class to represent the board state in the tree and backpropagated scores to improve move selection.  
   - However, random moves yielded poor results due to the large search space in chess, so this approach was abandoned.

3. **Second Approach**:  
   - Used **Stockfish** (a powerful chess engine) at a low level to generate promising moves instead of random ones for MCTS.
   - Selected the top 5 Stockfish moves to build the tree, which gave better results within the tree itself.

4. **Training the Policy Network**:  
   - Collected data from the MCTS tree to train the policy network.  
   - Used sequences of **8 board states** as inputs and the corresponding best move as outputs, following AlphaZero’s method.
   - Encoded boards in binary and used **1969 output classes** for possible moves.

5. **Challenges**:  
   - Limited compute resources restricted the size of the Monte Carlo tree and the number of training iterations.

6. **Results**:  
   - Despite limited training, the policy network showed **improvement over random play**.
   - Developed code to use the trained model to create a new Monte Carlo tree for further iterations, though compute constraints prevented full execution.

7. **Next Steps**:  
   - With better compute resources, the iterative training process can continue to further improve the model.
   - The bot can now play against a human or another model, with potential for further enhancements.
