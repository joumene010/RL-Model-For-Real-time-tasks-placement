# Q-Learning Task Allocation Simulation

This project implements a Q-Learning-based simulation for task allocation in a multi-processor environment. It is part of a research study, and the corresponding research report can be found in the associated Git repository.

## Overview

The goal of this project is to simulate and optimize the allocation of tasks to processors using Q-Learning, a reinforcement learning algorithm. The environment models processors with limited utility and tasks with specific utility requirements. The Q-Learning algorithm is used to learn an optimal policy for task allocation to maximize efficiency while avoiding overloading processors.

## Features

- **State Generation**: Dynamically generates all possible states for task allocation.
- **Action Generation**: Defines all possible actions for task allocation.
- **Environment Simulation**: Models the environment with processors and tasks, including utility constraints.
- **Q-Learning Implementation**: Implements the Q-Learning algorithm to learn an optimal task allocation policy.
- **Visualization**: Outputs the Q-table and optimal task allocation strategy.

## Project Structure

- **State and Action Generation**:
  - `generate_states`: Generates all possible states for task allocation.
  - `generate_actions`: Generates all possible actions for task allocation.

- **Environment**:
  - `ENV`: A class that models the environment, including processors, tasks, and their utilities. It provides methods for resetting the environment, checking if all tasks are placed, and executing actions.

- **Q-Learning Algorithm**:
  - Implements the Q-Learning algorithm to iteratively update the Q-table based on rewards and state transitions.

- **Utilities**:
  - Helper functions like `Max_val` to compute the maximum Q-value for a given state.

## Usage

### Prerequisites

- Python 3.x
- Required libraries: `numpy`

### Running the Simulation

1. Clone the repository and navigate to the project directory.
2. Open the Jupyter Notebook file (`Q_table vf.ipynb`) in a Jupyter environment.
3. Run the cells sequentially to:
   - Generate states and actions.
   - Initialize the environment.
   - Execute the Q-Learning algorithm.
   - Visualize the results.

### Key Parameters

- `discount_factor`: Determines the importance of future rewards.
- `eps`: Controls the randomness in action selection (exploration vs. exploitation).
- `learning_rate`: Determines the rate at which the Q-table is updated.
- `num_episodes`: Number of episodes for training the Q-Learning algorithm.

### Example

The following example initializes an environment with 3 processors and 5 tasks, and trains the Q-Learning algorithm:

```python
env = ENV(3, 0.69, [0.2, 0.4, 0.16, 0.32, 0.32])
states = generate_states(len(env.Ut), len(env.Up))
Q = np.zeros((len(states), len(env.actions)))

# Training loop
for i in range(num_episodes):
    env.reset(3, 0.69)
    ...
```

## Results

The simulation outputs:
- The Q-table (`Q`), which represents the learned policy.
- The optimal task allocation strategy based on the Q-table.

## Research Context

This project is part of a research study on task allocation optimization using reinforcement learning. The detailed research report is available in the associated Git repository.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contact

For questions or feedback, please contact the research team via the Git repository.
