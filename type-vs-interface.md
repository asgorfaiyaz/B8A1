# What are the core differences between type aliases and interface in TypeScript? When should you choose one over the other?

Today we’ll find out the truth by seeing what kind of problem they solve. To be honest, there is no short answer. It’s based on the use case.

First up, both type aliases and interface help us create reusable types. Starting with type aliases, they help us create any type you could possibly imagine for instance : primitive, literal, union and even objects etc. Here’s some examples :

```typescript
type Username = string;
type Age = number;
type User = {
  id: number;
  name: string;
  email: string;
};
```

On the other hand, interface can only be used with Objects, Classes, it can't describe union or primitve values. Here’s how you can declare an interface :

```typescript
interface User {
  name: string;
  age: number;
}
```

The special feature interface have which makes it very special is what we call merging. When two interface declared with same name, guess what? They merge together. This feature becomes useful when we’re dealing with an existing feature like Window or Global Object. And it is also widely used when we work with Library stuff.

The bottom line is, you can use Type aliases everywhere in your code no matter it is an object or map or union type, it is versatile and super flexible. But for describing objects it is better to use Interface over Type aliases. As Typescript suggests we should use Interface unless we need the feature of type aliases
