### Execute Program:

- [x] :star: Javascript Arrays,
- [x] :star: Modern Javascript,
- [x] :star: Regular Expressions,
- [x] :star: Javascript Concurrency.

---

**Finished reading:**

- [x] "Javascript: The Good Parts"
- [x] "Don't Make Me Think: A Common Sense Approach To Web Usability"

<details>
<summary>Learnings</summary><br>
  
  From _**"Javascript: The Good Parts"**_
  
- Always use scope,
- (Cascades, Memoization, Global Abatement),
- Retrieval can be done with either dot notation, or with square brackets,
- A function always returns a value or if unspecified, it returns undefined,
- Javascript only has array-like objects which are slower than 'real' arrays,
- Inner functions have access to the actual parameters of the outer functions (not copies),
- Or `||` operand can be used to fill in default values for nonexistent data to prevent an undefined error,
- Do not use `for in` as it does not iterate through the properties in order and sometimes pulls in from further up the prototype chain.
---
From _**"Don't Make Me Think"**_

- People make decisions through satisficing,
- People don't read web pages (they scan them),
- Pages should be self-evident. Don't make me think, don't waste my time,
- "Satisfice" (a blend of "**Satis**fy" and "Suff**ice**") is the idea of choosing the first reasonable option instead of the best possible option.

---

</details>

**Started reading:**

- [ ] "Code Complete 2" (referential?)
---
### Diary:

#### Metaphors for a Richer Understanding:

- Metaphors are heuristics, not algorithms. Combine metaphors as necessary,
- Metaphors help you understand the software development process by relating it to other activities you already know about,
- They can lead you in the wrong direction if extended too far,
- Software construction and building construction: careful preparation, difference between small and large projects,
- Development practices as tools in a toolbox - no single tool is right for every job. Choosing the right tool is key to being an effective programmer.
- Metaphors are not mutually exclusive. Use a combination that works well for you.

<details>
<summary>Historical</summary>

#### Javascript Iterables

<details>
  <summary> Class approach </summary>
  
```js
class NumberIterator {
  constructor() {
    this.value = 0;
  }
  
  next() {
    if (this.value < 3) {
      const value = this.value;
      this.value += 1;
      return {value, done: false};
    } else {
      return {value: undefined, done: true};
    }
  }
}

class NumbersBelowThree {
[Symbol.iterator]() {
return new NumberIterator();
}
}

const numbers = [];
for (const n of new NumbersBelowThree()) {
numbers.push(n);
}
numbers;

````

</details>
<details>
  <summary>Object approach</summary>

```js
const numbersBelowThree = {
  [Symbol.iterator]: () => makeIterator()
};

function makeIterator() {
  let currentValue = 0;

  return {
    next() {
      const value = currentValue;
      currentValue += 1;

      if (value < 3) {
        return {value, done: false};
      } else {
        return {value: undefined, done: true};
      }
    }
  };
}

const numbers = [];
for (const n of numbersBelowThree) {
  numbers.push(n);
}
numbers;
````

</details>

---

In some regex systems, `/.{,5}/` means "at most five characters". That's not true in JS which interprets it as a literal string.

```js
/^.{,5}$/.test(".{,5}"); // true
```

---

Found out that there are two functions to check if something is NaN.<br>

```js
Number.isNan(x); // good
isNan(x); // bad
```

---

Learned shorthand destructuring and .bind method

```js
const user = { name: "Amir" };
const userName = () => {
	return this.name;
};
userName.bind(user);
userNameBound(); //'Amir'
```

---

Wild idea: Separate javascript file for appending classes to avoid html clutter.

Destructuring can be written as either (for nested objects)

```js
const name = user.cat.name;
```

or

```js
const {
	cat: { name },
} = user;
```

---

**Sets**:

A set's size reflects the number of unique values that it holds. Duplicates passed to the constructor or added with .add don't contribute to the size.
An array's method `.includes` slows down as an array gets longer, a set's method `.has` mostly fixes this problem.

```js
const names = new Set(["Amir", "Betty", "Amir"]);
//methods
names.add("Jim");
names.delete("Jim");
names.clear();
names.has(name);
names.size;
//convert to array with
Array.from(names.values());
```

---

Learned about testing and the TDD process.

---

**Accessor properties stack error**

```js
class User {
	set name(newName) {
		this.name = newName;
	}
}

const amir = new User();
amir.name = "Amir";
```

The setter tried to do `this.name = newName`, which called the setter again, which did `this.name = newName` again until we hit the maximum stack size, which causes the JavaScript runtime to error.

---

**Computed Properties in classes**

When the class is being constructed, the virtual machine evaluates the string to get the method or accessor name. After the class is defined, those names won't change.

```
</details>
```
