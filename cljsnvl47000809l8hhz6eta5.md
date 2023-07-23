---
title: "Understanding TypeScript: A Comprehensive Overview and Installation Guide"
datePublished: Fri Jul 07 2023 14:17:48 GMT+0000 (Coordinated Universal Time)
cuid: cljsnvl47000809l8hhz6eta5
slug: understanding-typescript-a-comprehensive-overview-and-installation-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688738540680/e94cbc3a-b30b-451a-a387-f6b3359443fa.png
tags: javascript, web-development, typescript, wemakedevs

---

## What is typeScript?

TypeScript is a programming language that extends JavaScript by adding new features and advantages. It is not a separate language but rather a **superset of JavaScript**, meaning that any valid JavaScript code is also valid TypeScript code. TypeScript makes writing JavaScript code easier and more powerful by introducing features like static typing, interfaces, classes, and more.

In addition to adding new features, TypeScript also introduces type annotations. Type annotations allow developers to specify the types of variables, function parameters, and return values. This enables static type checking, where the TypeScript compiler can detect type-related errors during development before the code is executed. This type-checking feature helps catch common mistakes and prevents potential runtime errors, improving the reliability and maintainability of the codebase.

## Why should we use TypeScript?

TypeScript offers several benefits. Firstly, it enhances developer productivity by providing a more powerful and expressive language compared to plain JavaScript. It helps catch errors early in the development process, preventing them from occurring at runtime. This saves time and effort in debugging and fixing issues. TypeScript also improves code maintainability by providing better code organization, thanks to features like interfaces and classes. The type annotations and static typing enable better code documentation and facilitate collaboration among team members.

1. ### In order to understand why TypeScript is necessary and how it affects development, let's examine an example:
    

I am using the function`sumOfTwo` which takes two parameters and returns their sum.

```javascript
function sumOfTwo(num1,num2){
    const sum = num1 + num2;
    return `sum of two input is ${sum}`
}
console.log(sumOfTwo(2,3))
console.log(sumOfTwo(2,'12'))

// Output of the first console:
// sum of two input is 5

// Output of the second console:
// sum of two input is 212
```

**Let us analyze the output of the code provided above:**

In the first `console.log` statement, the function is called with the arguments `2` and `3` and you need to pay attention here that both arguments are numbers, the sum is calculated as `2 + 3 = 5`. The function returns the string `'sum of two input is 5'`, which is then printed to the console and this is exactly what we want to add two numbers.

In the second `console.log` statement, the function is called with the arguments `2` and `12`. If we evaluate the second console output, it can be observed that both arguments are numbers. In this scenario, the expected output should be `14` . However, the actual output we obtained is `212` .

Now, let's delve into why this discrepancy occurs and understand what is happening here.

Upon closer examination of the second `console.log` statement, one of the arguments is a string (`'12'`), and JavaScript performs implicit type coercion to concatenate the string with the number. So the sum is calculated as `'2' + '12' = '212'`. The function returns the string `'sum of two input is 212'`, which is then printed to the console.

1. ### Treating above error with JavaScript:
    

One way to address this issue in JavaScript is by adding an if check to validate the types of input values before performing the addition operation. If the input values are numbers, the calculation can proceed. Otherwise, you can throw an error or convert the input values to numbers using the unary plus operator (`+`).

```javascript
function sumOfTwo(num1,num2){
    let sum;
    if(typeof num1 === 'number' && typeof num2 === 'number'){
        sum = num1 + num2;
    }else{
        sum = +num1 + +num2;
    }
    return `sum of two input is ${sum}`
}
console.log(sumOfTwo(2,3))
console.log(sumOfTwo(2,'12'))

// Output of the first console:
// sum of two input is 5

// Output of the second console:
// sum of two input is 14
```

While this approach resolves the issue, it adds extra code and introduces the possibility of logical errors.

1. ### Why TypeScript is the superior choice:
    

This is where TypeScript can help. TypeScript is a superset of JavaScript that introduces **static typing**. With TypeScript, you can specify the types of variables and function parameters, ensuring that only the expected types are used. In this case, TypeScript would allow you to define the add function to only accept numbers as parameters, eliminating the need for additional type checks and conversions. This provides stronger type safety and helps prevent logical errors at compile time.

By leveraging TypeScript, you can keep the add function in its original state and ensure that it only operates on numbers. This helps maintain the integrity of the function and **reduces the risk of passing incorrect types of values**. TypeScript offers a valuable tool to enhance the development experience and improve code reliability in scenarios like this.

## Step-by-Step Guide: Installing and Utilizing TypeScript

1. ### The installation process of TypeScript:
    

To take advantage of TypeScript and understand how it helps us, we need to install it. You can visit [typescriptlang.org](http://typescriptlang.org) and navigate to the "Download" section to find instructions for installation. TypeScript installation relies on the NPM tool, which is part of the Node.js package. Even though we won't be writing Node.js code directly, we still need to install Node.js because some tools we use rely on it. By installing Node.js, we also get NPM, the Node Package Manager, which we can use to install TypeScript globally on our machine.

To install Node.js, visit [nodejs.org](http://nodejs.org) and click on the button to download and install the latest version available. The installation process is supported on all operating systems. Once you have Node.js installed, open your terminal or command prompt and enter the command provided to install TypeScript globally.

> command for installing typescript globally in your system - `npm install -g typescript`

On Mac and Linux, you may need to add "sudo" in front of the command to get the necessary permissions, but on Windows, this is not required. Enter your password if prompted.

With TypeScript installed globally, we now have the TypeScript compiler and all the necessary components to understand TypeScript code and convert it to JavaScript. It's important to note that TypeScript is a programming language, but it relies on the compiler to translate the code into JavaScript.

To check if TypeScript is installed on your machine, you can follow these steps:

1. Open your command prompt or terminal.
    
2. Type `tsc -v` and press Enter.
    
3. If TypeScript is installed, it will display the version number. For example, `Version 4.1.3`.
    
4. If TypeScript is not installed, it will display an error message like `'tsc' is not recognized as an internal or external command...`
    

1. ### Using TypeScript for the code mentioned above to comprehend its error-prevention capabilities:
    

To see TypeScript in action, let's add a new file to the project with an `.ts` extension, indicating it's a TypeScript file. You can choose any name for the file like `main.ts`. Copy the existing JavaScript code into the TypeScript file. When working with TypeScript in an appropriate IDE like Visual Studio Code (which is highly recommended), Visual Studio Code and similar IDEs provide excellent support for working with TypeScript files, analyzing the code and identifying weaknesses.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688733224575/94ceee2f-ad2e-482e-98c2-25aad3174169.png align="center")

By utilizing TypeScript and the recommended IDE, we benefit from enhanced code analysis, catching potential issues and providing helpful suggestions. TypeScript's integration with Visual Studio Code makes it a powerful combination for writing robust and maintainable code.

One of the main advantages of TypeScript is its addition of types. By specifying types for variables, parameters, and return values, TypeScript helps us catch potential errors during development. In the provided code example, hovering over a parameter `num1 or num2` reveals the type `any` indicating that TypeScript doesn't have enough information to infer the specific type.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688733871114/52c5d71a-46d0-4007-8405-1f7e359ad822.png align="center")

To make our code more explicit and prevent errors, we can add type annotations by appending a colon followed by the desired type, such as `number`

```typescript
function sumOfTwo(num1: number, num2: number) {
  const sum = num1 + num2;
  return `sum of two input is ${sum}`;
}
console.log(sumOfTwo(2, 3));
console.log(sumOfTwo(2, "12"));
```

By adding type annotations, we provide clearer intentions for our code and improve its readability. The TypeScript compiler checks these annotations and alerts us to any type-related errors, both in our integrated development environment (IDE) and during the compilation process. This ensures that our code is more reliable and less prone to unexpected runtime errors.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688734048679/bb7202aa-cc8f-4eb8-a78e-aaf282bc8588.png align="center")

the `sumOfTwo` function expects two parameters, `num1` and `num2`, to be of type `number`. However, in the second `console.log` statement, you're passing a string `"12"` instead of a number.

TypeScript is raising an error because you're attempting to add a number and a string together, which may lead to unexpected results. TypeScript wants to ensure that operations between variables are valid and predictable.

To fix the error, Pass a number instead of a string:

```typescript
console.log(sumOfTwo(2, 12));
```

1. ### Compilation process of TypeScript code:
    

One important thing to note is that TypeScript cannot be directly executed by JavaScript environments like browsers or Node.js. However, TypeScript provides a powerful compiler that transpiles TypeScript code into plain JavaScript code. This means that the TypeScript code you write is transformed into equivalent JavaScript code that can be executed by JavaScript environments.

The TypeScript compiler takes advantage of the new features introduced by TypeScript and compiles them into JavaScript workarounds. These workarounds enable the use of new syntax and easier ways of accomplishing tasks. While TypeScript cannot add features that are not possible in JavaScript, it can provide a more convenient and expressive syntax for writing code.

To compile TypeScript code, we can use the TypeScript compiler `tsc` through the command line. Navigating to the folder containing our TypeScript file, we run the `tsc main.ts` command, which invokes the compiler and generates a JavaScript file. During the compilation, the TypeScript compiler verifies the type correctness of our code. In case of errors, it provides helpful messages, such as the example error indicating an incompatible string argument for a function expecting a number parameter.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688734858810/ea1efd33-4055-4754-8303-610ea9f56462.png align="center")

Upon successful compilation, we obtain a JavaScript file that lacks the type annotations and additional TypeScript features. It contains plain JavaScript code equivalent to the TypeScript code we wrote. We can import this compiled JavaScript file into our HTML file and use it in our application, as browsers can only run JavaScript.

The process of using TypeScript forces us to write cleaner and more error-resistant code. We need to consider and explicitly define the types of our data, leading to clearer intentions and reducing the likelihood of type-related bugs. TypeScript's static typing feature improves code quality, readability, and maintainability, making it an invaluable tool for writing better JavaScript applications.

## Summary:

TypeScript is a special kind of code that helps programmers write JavaScript code easier and better. It has new features that make the code more powerful. It also helps find mistakes and prevents errors. It can't be used directly by computers, but there is a special program that changes it into code that computers can understand. This makes it easier for people to write code in TypeScript and use it on computers. TypeScript also adds new ways to do things, making it easier to write code.

Thank you for staying with me until the end. If you find this blog helpful and would like more regular updates, please follow me. I also tweet regularly, and you can follow me on [Twitter](https://twitter.com/1010nishant). Additionally, if you are interested in code referencing and future collaboration, you can check out my [GitHub](https://github.com/1010nishant).