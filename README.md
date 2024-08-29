# Minimal repro

Minimal reproduction example for Tailwind Issue https://github.com/tailwindlabs/tailwindcss/issues/14290

Repro:
1. run `tailwindcss -i ./input.css -o ./output.css --watch`
2. start editing index.html, for example, replace `text-red-400` with `text-red-500`

Expected result in output:
```css
...

.text-red-500 {
  --tw-text-opacity: 1;
  color: rgb(239 68 68 / var(--tw-text-opacity));
}
```

Actual result in output:
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
