# Minimal repro

Minimal reproduction example for Tailwind Issue https://github.com/tailwindlabs/tailwindcss/issues/14290

## Reproduce the issue

```sh
pnpm install
# or npm install

pnpm run css
# or npm run css
```

**Output at this point**:
```css
...

.text-red-400 {
  --tw-text-opacity: 1;
  color: rgb(248 113 113 / var(--tw-text-opacity));
}
```

Now edit [index.html](./index.html)
For this example, replace `text-red-400` with `text-red-500`, then save the file.

**Expected result in output**:
```css
...

.text-red-500 {
  --tw-text-opacity: 1;
  color: rgb(239 68 68 / var(--tw-text-opacity));
}
```

**Actual result in output**:
```css
...

.text-red-400 {
  --tw-text-opacity: 1;
  color: rgb(248 113 113 / var(--tw-text-opacity));
}

.text-red-500 {
  --tw-text-opacity: 1;
  color: rgb(239 68 68 / var(--tw-text-opacity));
}
```
