# String Manipulation Library in C++
# Overview

This library provides a robust String class implementation with advanced string manipulation capabilities, including transformations, concatenation, comparison, and substring operations. The implementation is templated to support different character types and includes an interactive menu system for demonstration.
# Key Features

    Templated String<T> class supporting different character types

    Comprehensive string operations (concatenation, comparison, substring)

    Character transformation system using functors

    Memory-safe implementation with proper resource management

    Interactive menu system for testing functionality

    Exception handling for invalid operations

# Class Architecture
# Core Components

    Transformer Base Class: Abstract base for character transformations

    Predefined Transformers:

        ToUpper: Converts to uppercase

        ToLower: Converts to lowercase

        ToStar: Replaces with '*'

        Shift: Shifts ASCII value by 1

        ToX: Replaces with 'x'

    String Class: Main string implementation with:

        Constructors for various initialization methods

        Memory management

        Operator overloads

        Transformation methods

# Usage Examples
# Basic String Operations
cpp

String<char> s1("Hello");
String<char> s2("World");

// Concatenation
String<char> s3 = s1 + " " + s2;  // "Hello World"

// Comparison
bool equal = (s1 == s2);  // false

// Repetition
String<char> s4 = s1 * 3;  // "HelloHelloHello"

String Transformations
cpp

String<char> s("Test String");

// Apply transformations
s.apply(ToUpper());  // "TEST STRING"
s.apply(ToStar());   // "***********"

// Functional transformation
s.modify([](char c) { return c + 1; });  // Shift each character

Substring Operations
cpp

String<char> s("Hello World");

// Get substring
String<char> sub = s.substr(6, 5);  // "World"

// Create from pointer range
const char* arr = "Array";
String<char> from_range(arr, arr + 3);  // "Arr"

Interactive Menu System

# The program offers these menu options:

    Create new string - Initialize a string from user input

    Concatenate strings - Append strings together

    Compare strings - Test various comparison operations

    Transform string - Apply character transformations

    Get substring - Extract portions of strings

    Repeat string - Create repeated copies

    Display string info - Show string properties

    Exit - Terminate the program

# Implementation Details
# Memory Management

    Uses dynamic allocation with proper copy semantics

    Implements move-aware operations

    Includes destructor for resource cleanup

# Error Handling

    Throws out_of_range for invalid indices

    Throws invalid_argument for invalid pointer ranges

    Uses assertions for internal consistency checks

# Performance Considerations

    Minimizes unnecessary copying

    Uses efficient algorithms for operations

    Optimizes common cases (like small strings)

# Best Practices

    Resource Management:

        Always use the provided operators/methods rather than direct memory access

        Prefer transformation methods over manual loops

    Exception Safety:

        Wrap operations in try-catch blocks when needed

        Check string bounds before operations

    Performance:

        Reuse String objects when possible

        Prefer apply() over mapped() for in-place transformations

# Extensibility

# The architecture supports easy extension:

    New Transformations:

        Implement new Transformer classes

        Add to the transformation menu

    New Operations:

        Add methods to String class

        Extend the menu system

# Requirements

    C++11 or newer

    Standard Library headers:

        <iostream>

        <stdexcept>

        <cctype>

# Limitations

    Currently optimized for ASCII characters

    Unicode support would require additional implementation

    Fixed buffer size for stream input (1024 characters)

This implementation provides a solid foundation for string manipulation tasks with safety, flexibility, and good performance characteristics.
