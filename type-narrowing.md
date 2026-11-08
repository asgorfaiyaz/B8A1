What is Type Narrowing in TypeScript?

One of the most crucial thing we need to care in typescript is the idea of Type narrowing. If you don’t understand this properly you will never be able to have a good grasp on Typescript. Today I will make it simple for you.

So with that in mind, let’s start off with the definition : Type narrowing is the process of narrowing a broader type into a specific type. In typescript we have top types like Any, Unkown. For now let’s take Unknown type for narrowing example, if we were to narrow Unknown type down to more specific types maybe a string or an object. Here’s what we need : Type Guards.

You might be wondering what is a Type Guard ?
Good question, A type guard is simple a run-time check that lets you narrow down the type of a variable within a conditional block. Here the important thing to note is this (conditional block). That means within a conditional block, TypeScript can understand the more specific type of a variable based on the condition. Let’s have a look at some examples :

```typescript
function printId(value: unknown) {
  if (typeof value === "string") {
    // TypeScript knows `value` is a string here
    console.log(value.toUpperCase()); // so you can use any method related to string type
  }
}
```

Common type guards are : typeof, in, instance of, discriminated union etc.
Lemme give you more examples of narrowing with in and instanceof operators:

```typescript
type Dog = { bark: () => void };
type Cat = { meow: () => void };

function makeSound(animal: Dog | Cat) {
  if ("bark" in animal) {
    animal.bark(); // Narrowed to Dog
  } else {
    animal.meow(); // Narrowed to Cat
  }
}
```

```typescript
function checkDate(value: unknown): void {
  if (value instanceof Date) {
    console.log(value.toISOString());
  }
}
```

The bottom line is for narrowing down a type you need to know how to use type guards and the way you can see a specific type narrowed down is within a conditional block.
