# JAM-mindmap

[Go to the mindmap](https://New-JAMneration.github.io/JAM-mindmap)

We want to explore the structure of the JAM protocol and its components. Please refer to
the LaTex mathematical symbols in the JAM graypaper to maintain this mindmap.

If a symbol is a function, please use `==highlight-text==` to indicate that it is a function.

## Development

To develop and work with the mindmap, you need to install `markmap-cli`. You can install it globally using either `yarn` or `npm`:

```bash
yarn global add markmap-cli
# or
npm install -g markmap-cli
```

You can also use `npx` to run `markmap-cli` in watch mode to automatically update the mindmap as you make changes:

```bash
# watch mode
# However, the watch mode does not support all LaTeX fonts.
# If you need to confirm the acccuracy of the LaTeX rendering,
# please use the export mode for verification.
npx markmap-cli mindmap.md -w
```

## Export to HTML

To export the mindmap to HTML, you can use the following command:

```bash
npx markmap-cli mindmap.md
```

## References

- [JAM graypaper](https://graypaper.com/)
- [markmap](https://markmap.js.org/)
- [KaTeX](https://katex.org/)
