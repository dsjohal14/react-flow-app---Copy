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

### 1. `onConnect` Function

This function handles the logic for connecting nodes within the application. Key changes include:

- **Branch Management**: When connecting nodes, the function checks if the source node starts a new branch or belongs to an existing one. It then appropriately assigns or propagates the branch information.
  
- **Connection Validation**: Added logic to prevent connections between parallel nodes.

- **Labeling Parallel Branches**: Implemented functionality to label the last node of each parallel branch  "Parallel End" tag.

### 2. `makeNodesEquispacedAndCentered` Function

This function dynamically positions nodes to create a balanced layout

- Identifies the initial node with zero incoming edges as the starting point.

- **Dynamic Positioning Based on Connectivity**: Nodes are positioned based on their connections, ensuring parallel nodes are equally spaced.

- **Handling Convergence Points**: For nodes appearing in multiple branches, their positions are calculated by averaging the x-coordinates and taking the maximum y-coordinate to represent convergence points accurately.