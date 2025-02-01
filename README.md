# React Native AsyncStorage Bug: Handling Complex Objects

This repository demonstrates a common error encountered when using AsyncStorage in React Native to store complex JavaScript objects.  The problem arises because AsyncStorage only accepts strings, and attempting to directly store objects leads to serialization issues if the objects contain non-serializable properties (like functions). This example shows the bug and its solution.

## Bug
The `buggyCode.js` file contains code that attempts to store a JavaScript object with a method directly into AsyncStorage.  This results in an error because JSON.stringify cannot handle the function.

## Solution
The `fixedCode.js` file provides a solution by properly serializing only the serializable parts of the object before storing it in AsyncStorage, and then parsing it back into a usable JavaScript object after retrieval.

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install necessary dependencies.
3. Run the app (requires a React Native development environment). You will see an error message in the console if the buggy code is used, and a success message if using the fixed version.

## License
MIT