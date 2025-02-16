# Expo Linking.getInitialURL() Inconsistent Null Return

This repository demonstrates a bug in Expo's `Linking.getInitialURL()` function where it inconsistently returns `null` even after successfully opening a deep link.  This makes reliable deep link handling difficult.

## Bug Description

The `Linking.getInitialURL()` function is supposed to return the initial URL used to open the app, if any. However, in certain scenarios, it returns `null`, even when the app was clearly opened via a deep link.  This leads to unpredictable application behavior, making it hard to handle deep links reliably.

## Reproduction

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run the app using Expo Go.
4. Open a deep link (e.g., `exp://example.com`).
5. Observe the console output.  You may see that `Linking.getInitialURL()` returns `null` even though the app was opened with a deep link.

## Solution

A more robust approach is needed to handle this inconsistency.  This involves implementing a retry mechanism or using an alternative method to determine the initial URL if `getInitialURL()` returns `null`.