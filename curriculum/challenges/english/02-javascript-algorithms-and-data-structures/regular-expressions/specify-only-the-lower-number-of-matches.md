---
id: 587d7db9367417b2b2512ba6
title: Specify Only the Lower Number of Matches
challengeType: 1
forumTopicId: 301366
---

# --description--

You can specify the lower and upper number of patterns with quantity specifiers using curly brackets. Sometimes you only want to specify the lower number of patterns with no upper limit.

To only specify the lower number of patterns, keep the first number followed by a comma.

For example, to match only the string `"hah"` with the letter `a` appearing at least `3` times, your regex would be `/ha{3,}h/`.

```js
let A4 = "haaaah";
let A2 = "haah";
let A100 = "h" + "a".repeat(100) + "h";
let multipleA = /ha{3,}h/;
multipleA.test(A4); // Returns true
multipleA.test(A2); // Returns false
multipleA.test(A100); // Returns true
```

# --instructions--

Change the regex `haRegex` to match the word `"Hazzah"` only when it has four or more letter `z`'s.

# --hints--

Your regex should use curly brackets.

```js
assert(haRegex.source.match(/{.*?}/).length > 0);
```

Your regex should not match `"Hazzah"`

```js
assert(!haRegex.test('Hazzah'));
```

Your regex should not match `"Hazzzah"`

```js
assert(!haRegex.test('Hazzzah'));
```

Your regex should match `"Hazzzzah"`

```js
assert('Hazzzzah'.match(haRegex)[0].length === 8);
```

Your regex should match `"Hazzzzzah"`

```js
assert('Hazzzzzah'.match(haRegex)[0].length === 9);
```

Your regex should match `"Hazzzzzzah"`

```js
assert('Hazzzzzzah'.match(haRegex)[0].length === 10);
```

Your regex should match `"Hazzah"` with 30 `z`'s in it.

```js
assert('Hazzzzzzzzzzzzzzzzzzzzzzzzzzzzzzah'.match(haRegex)[0].length === 34);
```

# --seed--

## --seed-contents--

```js
let haStr = "Hazzzzah";
let haRegex = /change/; // Change this line
let result = haRegex.test(haStr);
```

# --solutions--

```js
let haStr = "Hazzzzah";
let haRegex = /Haz{4,}ah/; // Change this line
let result = haRegex.test(haStr);
```
