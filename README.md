# recommit
Recommit - A (Conventional) Git Commits processor powered by plugins

Probably a continuation of the [parse-commit-message](https://github.com/tunnckoCoreLabs/parse-commit-message), [commitlint](https://ghub.io/commitlint) and the related libraries stack.

## AST Nodes

This draft represents the "Recommit AST", extended from the base [Unist AST](https://github.com/syntax-tree/unist) by the [unifiedjs collective](https://github.com/unifiedjs).

## Root

```ts
interface Root {
  type: 'root',
  children: [
    Header,
    Body,
    Footer,
  ],
  position: Position?,
}
```

### Header

```ts
interface Header {
  type: 'header',
  value: {
    type: string,
    scope: string | null;
    subject: string;
  },
  position: Position?,
}
```

### Body

```ts
interface Body {
  type: 'body',
  value: string,
  position: Position?,
}
```

### Footer

```ts
interface Footer {
  type: 'footer',
  value: string,
  position: Position?,
}
```
