[![Gitpod Ready-to-Code](https://img.shields.io/badge/Gitpod-Ready--to--Code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/dhruvkapur91/help-deduplication)  [![Build Status](https://travis-ci.org/dhruvkapur91/help-deduplication.svg?branch=master)](https://travis-ci.org/dhruvkapur91/help-deduplication) 

Hey there, thanks for helping Syed :smiley:

So Syed learned about Set and that set does not store duplicates. Syed was super happy knowing that. Syed had a requirement of getting a list of Points, and he had to deduplicate them. It seemed like Syed found the solution! Just put them in a Set, and it'll automatically deduplicate it for him.

So he went ahead, created Point class and override the equal method. The equality worked like a charm. However much to his surprise, the set did not deduplicate the Points at all :roll_eyes: and he has a failing that he just cannot get to pass.

He verified his understanding of Set with Integers, and it worked just fine. He now wonders if Set deduplicate elements only for pre-defined or if he is doing something wrong. Can you help him pass his test? :handshake:

# Solution

## Problem

The problem with Syed implementation is, he doesn't override [hashCode](https://pip.pypa.io/en/stable/) method.


## Usage

```java
 @Override
    public int hashCode() {
        return Objects.hash(x, y);
    }

```

## Reason 
If two objects are equal, according to the equals(Object class) method, then calling the hashCode method on each of the two objects must produce the same integer result.

In HashSet , which implementated from Set class,it internally creates a HashMap and if we insert an element into this HashSet using add() method, it actually call put() method on internally created HashMap object with element you have specified as it’s key and constant Object called “PRESENT” as it’s value.

Now,Key is duplicated,if we not overide hasCode and equal, when we say the two objects are equal.so we need to overide this two methods.

## Reference

[Geek For Geeks](geeksforgeeks.org/internal-working-of-sethashset-in-java/)

