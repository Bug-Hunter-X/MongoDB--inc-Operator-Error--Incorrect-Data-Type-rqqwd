# MongoDB $inc Operator Error: Incorrect Data Type

This repository demonstrates an uncommon error related to the MongoDB `$inc` operator.  The error stems from providing a string value instead of a number when attempting to increment a field.

## Bug Description
The `$inc` operator in MongoDB is designed to increment a numerical field. If you provide it a non-numeric value, like a string, the update operation will fail silently (or throw an error depending on your driver and settings).  This is a subtle error that can be difficult to detect.

## Reproduction Steps
1. Create a MongoDB collection named `myCollection`.
2. Insert a document with a numeric field, e.g., `{" _id": 1, "field": 0}`.
3. Run the provided JavaScript code (`bug.js`) which attempts to increment the field using an incorrect string value.
4. Observe that the field remains unchanged or an error is thrown.

## Solution
The solution involves ensuring that the value passed to the `$inc` operator is a number (integer or float).