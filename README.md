# React Code Challenge

Hello developer, thank you for taking time to resolve this challenge. Please read carefully the instructions below before start and feel free to ask any question you may have.

This challenge contains 3 exercises that will help us to understand your way of coding.

1. Logical exercise (required)
2. Framework exercise (required)
3. SQL exercise (optional)

#### Notes:
- This repo was builded using [pnpm](https://pnpm.io/installation)
- This repo uses Jest for unit test

---
## Instructions:

1. **FORK** this repo, **DO NOT** clone it
2. Once you forked it, before to start change the `author` within the `package.json` file and add your name
3. Install the dependencies, run the `dev` script and go to: `http://localhost:5173/`
4. To start the challenge perform the first commit with the `author` change
>
> We will consider this commit as the start of the test, you will have 48 hours to complete this challenge.
>We will only consider the commits you make that are within the 48 hours range, you will have only 30 min of margin (because of the time it may take to make the commits).
5. Please, **DO NOT** use github copilot for this challenge, yes I know we use it daily but for this test, we want to evaluate your skills.
6. When you finish the test, please send the link of your repo through email at isantiago@merakimx.com

---

### Will be graded:
In order to properly assess the candidate's skills, problem-solving abilities, coding style, and overall suitability for the position. Here are some important factors we will consider.

**Correction:** The candidate ensures that the code works as expected and solves the problem described in the challenge. Look for bugs, logic errors and edge cases that might not have been addressed.

**Effectiveness:** We will evaluate the efficiency of the code in terms of time complexity, space complexity and performance. We will also evaluate whether the candidate has chosen appropriate data structures and algorithms to solve the problem efficiently.

**Readability:** We will evaluate the readability and maintainability of the code. Clear variable names, well-structured code, meaningful comments, and adherence to coding conventions and best practices.

**Scalability:** We will consider whether the code is designed to scale well as the size of the input data increases. We will evaluate the candidate's ability to write code that can handle larger data sets without compromising performance or functionality.

**Error handling:** We will check whether the code includes adequate error handling mechanisms to deal with unexpected input, exceptions and edge cases. We will evaluate the robustness of the code in handling potential errors and bugs.

**Testing:** We will consider with higher priority candidates who add unit tests to their code, for us it is very important that they have knowledge of testing.

**Commits:** We will consider with higher priority candidates who properly add commits to their code, we tried to perform good practices as much as we can.

**Documentation:** We will evaluate the quality and completeness of the attached documentation or comments provided by the candidate. As well as whether the documentation effectively explains the purpose of the code, its functionality and how to use it.

**Creativity:** We will consider whether the candidate has demonstrated creativity and innovation in their approach to solving the problem. We expect unique or elegant solutions that demonstrate a deep understanding of the problem domain.

**Collaboration and communication:** If the code challenge involved collaboration or communication with other team members, we will evaluate how effectively the candidate communicated ideas, solicited feedback, and incorporated suggestions from others.

**Overall fit:** We will consider the fit of the candidate's skills, experience and problem-solving approach with the organization's requirements and culture. Evaluate whether the candidate would be a good fit for the team and the position you are applying for.

---

### Have fun!
I know, all of this sounds kinda picky, but at the end of the day we consider that those are basics of any software engineer, and you'll be facing this kind of challenges daily, but we hope you love your job as much as we do, so don't worry if you couldn't complete the whole exercise, we value the effort and we will only evaluate the code you write, not if you complete the 100% of each exercise.

---

## Exercises:

### 1. Logical excercise

![Goku and Vegeta are training with Wiss](src/assets/goku-vegeta-trainning.png)

Goku and Vegeta are training with Wiss to increase their powers using training dummies. They both are taking turn to hit the dummies.
For each turn, the number of dummies is randomized and each dummy has a number written on it that represents the number of hits it can take before it is destroyed.

Wiss has given them the following conditions:
1. Only 2 dummies can be hit per turn.
2. Once you hit the first dummy, you can only hit dummies that are to the right of it, not to its left.
3. The subtraction of the number of the first dummy minus the second must not be negative.

As punishment they must change the Bills sheets according to the subtraction between the number of hits of the first dummy minus the second. So you must concentrate on making sure that the subtraction is always the smallest possible. (You wouldn't like to change Mr. Bills' sheets many times, would you?)

> 
> To make sure your code works, we have added some test cases.
> **DO NOT** modify the test cases files, only run the `pnpm test` script within the `package.json` file.

**Example:**
dummies = [10, 7, 20, 8, 4] // each number represent the number of hits it can take before it is destroyed

The minimum times they should change Bills sheets is by hitting the first dummy at `dummies[0] = 10` and the fourth dummy at `dummies[3] = 8`.
`Return 10 - 8 = 2`

**Description:**
Complete the `fewerChangeSheets()` function located at `src/modules/logical-exercise/result.ts` that accept following parameter(s):
* int dummies[n] array: a list of dummies (remember, the length of the array represent how many dummies appeared, and each position represent the number of hits each one can take)

**Returns:**
* int: the minimum possible change of sheets

**Constraints:**
- All the number of hits are distinct.
- A valid answer exists always.

**Sample Input 1**
```
5 10 3 9 7
```

**Sample Output 1**
```
1
```

**Explanation 1**
Vegeta hits the second dummy at `dummies[1] = 10` and the fourth dummy at `dummies[3] = 9`, as result he will only change Bills sheets once


**Sample Input 2**
```
8 15 6 22 11 30
```

**Sample Output 2**
```
2
```

**Explanation 2**
Goku hits the first dummy at `dummies[0] = 8` and the third dummy at `dummies[2] = 6`, as result he will change Bills sheets 2 times

---

### 2. Framework excercise

![Greninja](src/assets/greninja.jpg)

Using the [Poke Api](https://pokeapi.co) and [Firebase](https://firebase.google.com/docs/firestore), the goal is to create an application that allows users to interact with Pokémon data and save their favorite Pokémon to Firebase Firestore. 

The application should include the following features:

1. **List of Pokemons**: Display a list of Pokémon fetched from the [Poke Api](https://pokeapi.co).

2. **Dynamic Routes**: Clicking on a Pokémon should navigate the user to a dynamic route for the selected Pokémon based on its ID.

3. **Pokemon Details**: On the Pokémon detail page, display the following information:
   - Original sprites
   - Name of the Pokémon
   - Available types
   - Abilities
   - Switch to view shiny sprite

4. **Firebase Integration**: Implement Firebase Firestore to allow users to save their username and a list of their favorite Pokémon without requiring authentication. The app should ask the username at the beginning, and keep that user unless they want to switch to a different user. (No need to authenticate).

5. **Save Button**: Include a button on the Pokémon detail page that allows users to save the Pokémon as one of their favorites. When clicked, the Pokémon's data should be saved to Firestore (should be saved to the current user).

6. **User's favorite pokemons**: Implement a different route where you can select a user, and see their favorite pokemons from firebase in a table that includes the same information as the point 3, if the user clicks any pokemon in the table, they should go to the pokemon details page.

Your task is to create a web application that fulfills these requirements using NextJs for the frontend and Firebase for the backend data storage. Make sure to handle errors gracefully and provide a user-friendly interface.

Please document your code and provide clear instructions on how to run the application locally. You may also include any additional features or enhancements that you think would improve the user experience.

**Acceptance criteria:**
1. Must use [Redux Toolkit](https://redux-toolkit.js.org) as state management
2. Must use [RTK Query](https://redux-toolkit.js.org/rtk-query/overview) for fetching pokemon data
3. If the pokemon already exists in the store, should retrieve it from there instead of performing an api call
4. Only pokemon names are displayed within the list
5. User should be able to switch between original sprite and shiny as desired
6. Test the single pokemon route, to cover the following cases:
    * Should show the pokemon sprite if pokemon exists in local storage
    * Should retrieve pokemon sprite if doesn't exists in local storage
    * Should be able to switch between original sprite and shiny sprite as desired.

**Optional:**
(if you don't want do to this, we don't care, no, really... we don't care 😅)
1. Current state must persist on window reload
2. The user can change the number of pokemon to be displayed in the list

**Note:**
For this project you'll need to create a firebase project, feel free to leave or remove the firebase project credentials, it's up to you. If you leave them for make us life easy, we'll remind you to delete the project once we reviewed it.

---

### 3. SQL exercise (optional)

Using HackerRank, we'll perform this challenge, it's optional so feel free to do it if you want, since SQL is not required for your position, may be helpful to have some extra knowledge.

Please resolve [this exercise](https://www.hackerrank.com/challenges/salary-of-employees/problem?isFullScreen=true), and add your solution to the `src/sql-exercise/index.sql` file.