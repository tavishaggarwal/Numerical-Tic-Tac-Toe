# Numerical Tic-Tac-Toe
Numerical Tic-Tac-Toe is a variant of game Tic-Tac-Toe where instead of X and O, the numbers 1 to 9 are used.

# About the game
 - In the 3x3 grid, numbers 1 to 9 are filled, with one number in each cell.
 - The first player plays with the odd numbers, the second player plays with the even numbers, i.e. player 1 can enter only an odd number in the cell while player 2 can enter an even number in one of the remaining cells.
 - Each number can be used exactly once in the entire grid.
 - The player who puts down 15 points in a line - (column, row or a diagonal) wins the game.

 `Play the Game:` You can try out the [game](!https://www.play123.in/game/numeric-tic-tac-toe).

# Rules of the Game:
- The game will be played on a 3x3 grid (9 cells) using numbers from 1 to 9. Each number can be used exactly once in the entire grid.
- There are two players: one is the Reinforcement Learning (RL) agent and other is the environment.
- The RL agent is given odd numbers {1, 3, 5, 7, 9} and the environment is given the even numbers {2, 4, 6, 8}
- Each of them takes a turn. The player with odd numbers always goes first.
- At each round, a player puts one unused number on a blank spot.
- The objective is to make 15 points in a row, column or a diagonal. The player can use the opponent's numbers in the grid to make 15.
- The game terminates when any one of the players makes 15.

In this project, I have build an RL agent that learns to play Numerical Tic-Tac-Toe with odd numbers (the agent will always make the first move). 

# Reward Structure
- If your agent wins the game, it gets 10 points, if the environment wins, the agent loses 10 points.
- If the game ends in a draw, agent gets 0.
- We want the agent to win in as few moves as possible, so for each move, it gets a -1 point.

# Technique followed in the project
1. Created an MDP for Numerical Tic-Tac-Toe game

    The basic framework for this is:

    1. Initialise the state and action space for each state.
    2. Defined the winning states: the sum of three numbers in a row, column or diagonal is 15.
    3. Defined the terminal states (win,tie,loss and build the reward structure.
    4. Defined a step function which takes in an input of the agent’s action and state; and outputs the next state and reward.

2. Build an agent that learns the game by Q-Learning.
    1. It is keept in mind that while updating the Q-values, if the next state is a terminal state, then the Q-values from that state are 0.

3. Checked the Q-values convergence by ploting 4 state-action pairs against number of episodes to understand the convergence.

`NOTE:` For a 64-bit system with 8GB RAM, it takes ~180 minutes to run 5 Million episodes.