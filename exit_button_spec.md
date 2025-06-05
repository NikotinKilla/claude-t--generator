
# Feature: Exit to Main Menu Button (Mobile Game)

## Overview
This feature introduces a new button that allows the player to exit the current gameplay session and return to the main menu. The button should be accessible from the in-game pause menu and during non-combat moments.

## Goals
- Provide an intuitive way for players to return to the main menu.
- Prevent accidental exits by adding a confirmation dialog.
- Ensure consistent behavior across different game states.

## Requirements

### Functional Requirements
1. The "Exit to Menu" button must be displayed in the pause menu.
2. When pressed, a confirmation dialog appears:
   - Title: "Exit Game"
   - Message: "Are you sure you want to return to the main menu? Unsaved progress will be lost."
   - Buttons: [Yes, No]
3. If "Yes" is selected:
   - Current game state is cleaned up (unloaded).
   - The main menu scene is loaded.
4. If "No" is selected:
   - Dialog is dismissed; gameplay resumes or pause menu remains.

### UI/UX Specifications
- Button Label: "Exit to Menu"
- Font Size: 16sp
- Minimum Tap Area: 48x48 dp
- Button Placement: Below the "Resume" button in pause menu
- Confirmation Dialog Style: Matches system dialog or game UI theme

### Platforms
- Android, iOS

## Technical Notes
- Use the existing SceneManager to load `MainMenuScene`.
- Call `GameSessionManager.cleanup()` before scene change.
- Pause the game loop while the dialog is active.

## Edge Cases
- If the game is already saving when the player exits, show a "Please wait…" dialog.
- If the player is in a tutorial and the exit is restricted, disable the button with tooltip: "Unavailable during tutorial."

## Analytics
- Log the event `exit_to_menu_pressed` with context (e.g., level, session time).

## QA Notes
- Ensure button is not active during combat.
- Ensure memory is properly cleared before loading main menu.
- Confirm that exit flow works on both Android and iOS.

## Status
- Design: ✅ Approved
- Implementation: ⬜ In Progress
- QA: ⬜ Not Started
