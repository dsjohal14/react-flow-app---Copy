# Application Setup Instructions and Changes Documentation

## Setup Instructions

### Getting Started

To run the application, follow these steps:

1. **Install Dependencies**: 
   Open a terminal in the project root directory and run:
   ```
   npm install
   ```

2. **Start the Application**: 
   Once the dependencies are installed, start the application by running:
   ```
   npm start
   ```

3. **Access the Application**: 
   The application will be available at [http://localhost:3000/](http://localhost:3000/).

## Changes Made

### Overview

Significant changes were made to two functions to enhance the application's functionality related to managing nodes and their connections within the flow diagram.

### 1. `onConnect` Function

This function handles the logic for connecting nodes within the application. Key changes include:

- **Branch Management**: When connecting nodes, the function checks if the source node starts a new branch or belongs to an existing one. It then appropriately assigns or propagates the branch information.
  
- **Connection Validation**: Added logic to prevent connections between parallel nodes that violate the workflow's integrity.

- **Labeling Parallel Branches**: Implemented functionality to label the last node of each parallel branch with a unique branch ID and a "Parallel End" tag for clarity.

### 2. `makeNodesEquispacedAndCentered` Function

This function dynamically positions nodes to create a balanced layout. Major adjustments include:

- **Dynamic Positioning Based on Connectivity**: Nodes are positioned based on their connections, ensuring parallel nodes are equally spaced.

- **Handling Convergence Points**: For nodes appearing in multiple branches, their positions are calculated by averaging the x-coordinates and taking the maximum y-coordinate to represent convergence points accurately.

### Implementation Details

#### `onConnect` Implementation

- Branch assignment is refined to support circular nodes starting new branches and non-circular nodes inheriting branch information.
- Prevents invalid connections and updates node labels to indicate the end of parallel branches.

#### `makeNodesEquispacedAndCentered` Implementation

- Identifies the initial node with zero incoming edges as the starting point.
- Recursively positions nodes, adjusting the horizontal distance dynamically to distribute branches uniformly.