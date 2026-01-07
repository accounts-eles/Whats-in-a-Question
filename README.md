❓ What's in a Question: Interactive Reveal Activity

An interactive learning component designed to gamify the discovery of prompts, questions, or key concepts. This module uses a "Reveal on Click" mechanic to encourage active engagement and maintain a clean, uncluttered interface.

🚀 Live Demo

Interact with the Question Reveal Activity Here

✨ Project Overview

The "What's in a question" activity serves as a focal point for inquiry-based learning. By hiding the text behind a clickable "question mark" icon, users are encouraged to pause and mentally prepare for the information before it is revealed.

Key Features

Interactive Reveal Mechanic: Content is hidden by default. Clicking the circular "?" icon triggers a smooth vertical expansion of the text.

Micro-Interactions: Hovering over the question wrappers provides visual feedback via a teal border transition, signaling to the user that the element is interactive.

Animated Transitions: Utilizes CSS cubic-bezier timing functions to create a "snappy" yet smooth opening effect for the hidden text.

Accessibility Ready: Buttons include aria-label attributes to ensure screen readers can navigate the interactive triggers.

🎨 Design System

The activity adheres to a specific professional brand palette:

Midnight Blue (#1f2a52): Primary color for headers and the inactive state of question icons.

Teal (#00bec7): The "Active" state color, used to indicate which questions have already been explored.

Light Aqua (#d2f0f0): Used as a background for the question wrappers to separate prompts from the main page body.

Slate Grey (#abb5bf): Applied to instruction text to provide hierarchy and reduce visual noise.

🛠️ Technical Implementation

CSS Transition Strategy

Because standard CSS cannot animate height: auto, this project uses a max-height transition strategy:

.question-text-container {
    max-height: 0;
    opacity: 0;
    overflow: hidden;
    transition: max-height 0.5s cubic-bezier(0, 1, 0, 1), opacity 0.3s ease;
}

.question-text-container.active {
    max-height: 500px; /* High enough to accommodate content */
    opacity: 1;
}


This ensures that the content slides down smoothly regardless of the specific word count inside the paragraph.

Toggle Logic

The functionality is driven by a lightweight JavaScript function:

Target the clicked button.

Locate the immediate sibling (nextElementSibling).

Toggle the .active class on both, which updates the background color of the icon and triggers the CSS expansion.

📂 Project Structure

Whats_in_a_Question/
├── index.html          # Main standalone application
├── README.md           # This documentation
└── .github/workflows/  # Deployment configuration


📖 Customization

To add more questions to the activity:

Copy a .question-wrapper div block.

Update the aria-label for screen reader consistency.

Replace the question-text content with your desired prompt.

The layout is fully responsive and will automatically adapt the width of the question cards for mobile, tablet, and desktop viewports.

Note: This project is part of the accounts-eles instructional design toolkit.
