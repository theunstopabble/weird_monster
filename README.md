# weird_monster
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/theunstopabble/weird_monster)

This repository contains a procedural animation project that generates an interactive "weird monster" using JavaScript and the HTML5 Canvas. The creature, composed of a series of connected segments, dynamically follows the user's mouse cursor around the screen. The movement is achieved through a custom physics and inverse kinematics engine, which gives the creature a life-like, crawling motion.

## Live Demo

You can interact with the live version of the project here:

**[https://weird-monster-theunstopabble.netlify.app/](https://weird-monster-theunstopabble.netlify.app/)**

## Features

- **Interactive Animation:** The creature actively tracks and follows the mouse cursor.
- **Procedural Generation:** A unique lizard-like creature with a randomized number of legs and tail length is generated on each page load.
- **Inverse Kinematics:** Limbs animate using an IK system that calculates joint angles to place the "feet" intelligently as the body moves.
- **Segment-Based Physics:** The creature is built from a hierarchy of `Segment` objects, allowing for complex and flexible body structures with simulated physics like stiffness and resistance.

## Getting Started

No build process or dependencies are required. Simply clone the repository and open the `index.html` file in a web browser.

```bash
git clone https://github.com/theunstopabble/weird_monster.git
cd weird_monster
# Open index.html in your browser
```

## Code Overview

The entire logic is contained within the `script.js` file.

- **`index.html`**: The main HTML file that loads the script and provides the canvas container.
- **`script.js`**:
    - **Input Handling**: Listens for mouse movement to serve as the target for the creature.
    - **Canvas Setup**: Dynamically creates an HTML5 canvas that fills the browser window.
    - **Core Classes**:
        - `Creature`: Represents the main body of the monster. It handles top-level physics for movement and rotation towards the target.
        - `Segment`: The fundamental building block. Each segment is a "bone" connected to a parent, forming the creature's skeleton.
        - `LimbSystem`: A generic class for controlling a chain of `Segment` objects, implementing the inverse kinematics logic.
        - `LegSystem`: A specialized version of `LimbSystem` that adds a stepping cycle, allowing the creature to "walk" by placing its feet on the ground.
    - **Setup Functions**:
        - `setupLizard()` (used by default) creates a complex creature with a spine, ribs, and a variable number of legs and tail segments.
        - Other functions like `setupSimple()`, `setupTentacle()`, and `setupTestSquid()` are included in the code and can be experimented with to generate different kinds of creatures.
