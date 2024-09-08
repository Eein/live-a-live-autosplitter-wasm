# Live A Live WASM Autosplitter

A multiplatform autosplitter for Live a Live (PC)

## Supported Features
- Auto start timer on character select
- Auto start timer when selecting NEW GAME
- Game Time through loading removal (not accurate)
- Split on next chapter start (only when timer is running)

# TODO:
- [~] Character Story Splits
   - partially done in `revamp` branch, going through to get scenario ids
- [x] Full game ending splits
    - [x] True Ending - Sin Odio end flash (this is the main and currently only official speedrun category)
    - [x] Incomplete Destiny Ending - cutscene after completing partial boss rush
    - [x] Never Ending - defeat Oersted? save prompt after completion? (a change in Scenario Progress after defeating Oersted is not guaranteed, particularly in the context of multi-ending runs like All Achievements)
    - [x] Sad Ending - skip cutscene after defeating all protagonists
    - [x] Armageddon (in Oersted route) - animation of activating the Armageddon action
- [x] Determine a better way to handle Present Day defeated enemies.
  - counting boss defeat animations

## Install

Go to "Edit Splits", and make sure Live a Live (2022) is selected as the game name, and click "Activate" then click "Settings" to change your splits.

To install a new version, restart LiveSplit

## Manual Install

Go to release page and select a release and add Auto Splitting Runtime component and add the file manually.

### For Any% Good Ending Runs

Select Automatic Start on New Game

Select "Start {Chapter name}" for all spits *except* the first characters split, unless you have a "menu split" before that character select.

Note: In the future, preconfigured autosplitter and splits file may be provided in the community discord/src page.

Ending split must be done manually for now.

### For Individual Level Runs

Select Automatic Start on character select

Ending split must be done manually for now.

### NOTE

!!! ENSURE YOU EITHER HAVE YOUR TIMING METHOD ON THE TIMER COMPONENT SET TO `GAME TIME` OR MAKE TWO TIMERS AND SET ONE TO `GAME TIME` !!!

## build

1. install rustup + stable rust https://rustup.rs/
2. install wasm target
  - `rustup target add wasm32-unknown-unknown`
3. build wasm file (--release optional)
  - `cargo build --target wasm32-unknown-unknown --release`
