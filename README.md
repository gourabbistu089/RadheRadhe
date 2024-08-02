# CSS Concepts Summary

## Table of Contents
1. [CSS Combinators](#css-combinators)
2. [CSS Colors](#css-colors)
3. [Box Model in CSS](#box-model-in-css)
4. [Advanced Margin in CSS](#advanced-margin-in-css)
5. [Display in CSS](#display-in-css)
6. [Position in CSS](#position-in-css)
7. [CSS Specificity](#css-specificity)
8. [Flexbox in CSS](#flexbox-in-css)
9. [CSS Grid Layout](#css-grid-layout)
10. [CSS Variables](#css-variables)
11. [Transition in CSS](#transition-in-css)
12. [Transform in CSS](#transform-in-css)
13. [CSS Animations](#css-animations)

## CSS Combinators

CSS combinators define relationships between elements in HTML:

- Descendant Selector (Space): Selects a descendant element
- Child Selector (>): Selects a direct child element
- Adjacent Sibling Selector (+): Selects an immediately preceding sibling
- General Sibling Selector (~): Selects all siblings
- Universal Selector (*): Selects all elements

## CSS Colors

Ways to define colors:
- Named colors (e.g., "red")
- Hexadecimal values (e.g., "#FF5733")
- RGB values (e.g., "rgb(255, 87, 51)")
- RGBA values (e.g., "rgba(255, 87, 51, 0.5)")
- HSL values (e.g., "hsl(0, 100%, 50%)")
- HSLA values (e.g., "hsla(0, 100%, 50%, 0.5)")

Key Concepts:
- rgb() vs rgba(): rgba() includes an alpha channel for transparency
- Transparent text: Use `color: transparent;` or `color: rgba(0, 0, 0, 0);`
- currentColor keyword: Matches the color of another property in the same element

## Box Model in CSS

Components:
1. Content: The innermost part
2. Padding: Space between content and border
3. Border: Surrounds padding and content
4. Margin: Space outside the border

box-sizing property:
- content-box (default): Width/height based on content area
- border-box: Width/height includes content, padding, and border

## Advanced Margin in CSS

- auto value: Centers block-level elements horizontally
- Negative margins: Can overlap elements (use cautiously)
- Collapsing margins: Adjacent margins combine, larger takes precedence

## Display in CSS

Key concepts:
- block vs inline: Block elements start on new lines, inline elements don't
- display: none;: Removes element from layout and accessibility
- Centering with display: block;: Use `margin: 0 auto;`
- inline elements: Don't respect top/bottom margins/padding or width/height
- Making inline elements block-like: Use `display: inline-block;`

## Position in CSS

Types:
- static: Default, follows normal document flow
- relative: Positioned relative to normal position
- absolute: Positioned relative to nearest positioned ancestor
- fixed: Positioned relative to viewport
- sticky: Hybrid of relative and fixed positioning

## CSS Specificity

Hierarchy (from highest to lowest):
1. !important
2. Inline styles
3. IDs
4. Classes, pseudo-classes, attribute selectors
5. Elements and pseudo-elements

## Flexbox in CSS

One-dimensional layout model for flexible space distribution.

Container properties:
- display: flex;
- flex-direction
- justify-content
- align-items
- flex-wrap
- align-content

Item properties:
- order
- flex-grow
- flex-shrink
- flex-basis
- flex (shorthand)
- align-self

## CSS Grid Layout

Two-dimensional layout system for complex designs.

Key concepts:
- Grid container and grid items
- grid-template-columns and grid-template-rows
- Grid lines and tracks
- Placing items with grid-column and grid-row
- Grid gaps
- Explicit vs. Implicit grid
- Responsive grids
- Alignment and justification

## CSS Variables

Custom properties for reusable values:

- Syntax: --variable-name: value;
- Usage: var(--variable-name)
- Scope: Can be global (:root) or local

## Transition in CSS

Smooth property changes over time:

- transition-property
- transition-duration
- transition-timing-function
- transition-delay
- Shorthand: transition: property duration timing-function delay;

## Transform in CSS

Modify the appearance of elements:

- translate(): Move elements
- scale(): Resize elements
- rotate(): Rotate elements
- skew(): Slant elements
- transform-origin: Set the origin point for transformations

## CSS Animations

Create complex, keyframe-based animations:

- animation-name
- animation-duration
- animation-timing-function
- animation-delay
- animation-iteration-count
- animation-direction
- @keyframes rule for defining animation steps

This summary covers the main CSS concepts from the original content, organized for better readability and quick reference.
