# assignment_HeroVired

# CalculatorPlus Application

## Repository Name: git_assignment_HeroVired

### Table of Contents

1. [Project Description](#project-description)
2. [Setup Instructions](#setup-instructions)
3. [Branching and Feature Implementation](#branching-and-feature-implementation)
4. [Version Releases](#version-releases)
5. [Git LFS Integration](#git-lfs-integration)
6. [Geometry Calculator Implementation](#geometry-calculator-implementation)
7. [Collaboration](#collaboration)
8. [Review and Feedback](#review-and-feedback)

## Project Description

This project is a simple Python application called "CalculatorPlus" which provides basic arithmetic operations including addition, subtraction, multiplication, and division. We have added support for calculating the square root of a number and implemented a geometry calculator to calculate the area of a circle and a rectangle.

## Setup Instructions

1. Clone the repository:
    ```sh
    git clone <your-github-repo-url>
    cd git_assignment_HeroVired
    ```

2. Install dependencies (if any):
    ```sh
    pip install -r requirements.txt
    ```

## Branching and Feature Implementation

### Initial Setup

1. Initialize the repository and set up remote:
    ```sh
    git init
    git remote add origin <your-github-repo-url>
    ```

2. Create and switch to the `dev` branch:
    ```sh
    git checkout -b dev
    ```

### Initial Code

Create `calculator.py` with the initial code:
```python
import math

class Calculator:
    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def multiply(self, a, b):
        return a * b

    def divide(self, a, b):
        return a / b

    def square_root(self, x):
        return math.sqrt(x)

if __name__ == "__main__":
    calculator = Calculator()
    num1 = 16
    num2 = 4

    print(f"{num1} + {num2} = {calculator.add(num1, num2)}")
    print(f"{num1} - {num2} = {calculator.subtract(num1, num2)}")
    print(f"{num1} * {num2} = {calculator.multiply(num1, num2)}")
    print(f"{num1} / {num2} = {calculator.divide(num1, num2)}")

    num3 = 25
    print(f"The square root of {num3} = {calculator.square_root(num3)}")



### Commit and push the initial code:
git add calculator.py
git commit -m "Initial commit with basic calculator functionality"
git push origin dev



## Merge with Main and Release Version 1
1. Merge `dev` into `main`:
git checkout main
git merge dev

2. Create a version 1 release:
git tag v1.0
git push origin main --tags


## Add Collaborators
On GitHub, navigate to the repository > Settings > Manage access > Invite a collaborator.

## Feature Branch for Square Root
1. Create a feature branch:
git checkout -b feature/sqrt

2.  Implement the square root feature (already implemented in initial code):
git add calculator.py
git commit -m "Implement square root feature"
git push origin feature/sqrt



1. Critical Bug Fix
### Switch to `dev` and fix the divide function:
git checkout dev
git pull origin dev

### Fix divide function in calculator.py
def divide(self, a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero.")
    return a / b

git add calculator.py
git commit -m "Fix divide by zero bug"
git push origin dev

2. `Rebase feature/sqrt` to include the fix:
git checkout feature/sqrt
git rebase dev
git push origin feature/sqrt --force



## Pull Request and Merge
1. Create a pull request on GitHub from feature/sqrt to dev.

2. Request code review and address feedback.

3. Merge feature/sqrt into dev:
git checkout dev
git merge feature/sqrt
git push origin dev

4. Merge dev into main and release version 2:
git checkout main
git merge dev
git tag v2.0
git push origin main --tags



## Git LFS Integration

1. Install Git LFS:
git lfs install

2. Track large files:
git lfs track "*.bin"
git add .gitattributes
git commit -m "Add Git LFS tracking for binary files"

3. Upload a large file:
git checkout -b lfs
echo "Large binary file content" > large_file.bin
git add large_file.bin
git commit -m "Add large binary file"
git push origin lfs

4. Verify on another machine:
git clone <your-github-repo-url>
cd git_assignment_HeroVired
git checkout lfs



## Geometry Calculator Implementation

1. Create a branch for circle area feature:
git checkout -b feature/circle-area

2. Stash changes:
git stash

3. Create a branch for rectangle area feature:
git checkout -b feature/rectangle-area

4. Stash changes:
git stash

5. Complete circle area feature:
git checkout feature/circle-area
git stash pop

# Complete the circle area feature
radius = 5
print(f"The area of the circle with radius {radius} = {calculator.calculate_circle_area(radius)}")

git add geometry_calculator.py
git commit -m "Complete circle area feature"
git push origin feature/circle-area

6. Complete rectangle area feature:
git checkout feature/rectangle-area
git stash pop

# Complete the rectangle area feature
length = 10
width = 6
print(f"The area of the rectangle with length {length} and width {width} = {calculator.calculate_rectangle_area(length, width)}")

git add geometry_calculator.py
git commit -m "Complete rectangle area feature"
git push origin feature/rectangle-area

7. Create pull requests and review:

On GitHub, create pull requests from feature/circle-area and feature/rectangle-area to dev.
Request code reviews and address feedback.

8. Merge features and release:
git checkout dev
git merge feature/circle-area
git merge feature/rectangle-area
git push origin dev

git checkout main
git merge dev
git tag v3.0
git push origin main --tags

