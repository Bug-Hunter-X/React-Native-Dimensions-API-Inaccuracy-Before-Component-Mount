# React Native Dimensions API Inaccuracy Before Component Mount

This repository demonstrates a common bug in React Native applications where using the `Dimensions` API to get screen dimensions before the component has fully mounted results in inaccurate or undefined dimensions.  This can lead to various UI issues, such as misaligned elements or incorrect sizing.

## Bug Description
The `Dimensions` API provides information about the screen dimensions, but if accessed prematurely, during the initial rendering of a component before the layout is established, the returned dimensions might be incorrect. This can cause elements to be positioned incorrectly, leading to overlapping or off-screen rendering.

## Reproduction Steps
1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npx react-native run-android` (or `npx react-native run-ios`) to start the application.
4. Observe the initial rendering of the screen. Note that the elements may be misaligned or sized incorrectly.

## Solution
The solution involves using the `useEffect` hook and checking the `dimensions` value in the subsequent render.