# Uncommon React useEffect Bug: Infinite Loop

This repository demonstrates a subtle bug that can occur when using the `useEffect` hook in React. The bug is caused by unintentionally creating an infinite loop due to a missing or incorrect dependency array.

## Bug Description
The `useEffect` hook in the provided code runs on every render because the dependency array is missing.  This is not immediately obvious as the `count` variable is being updated by the state update, making the console statement fire infinitely. The goal is to only log the count when it changes.

## How to Reproduce
Clone the repository and run `npm start`. Observe that the console continuously logs 'Count updated:' with the current count.  This leads to performance issues and possibly a crashed browser.

## Solution
The solution involves correctly specifying the dependency array for `useEffect`. The dependency array `[count]` ensures that the effect only runs when the value of `count` changes.