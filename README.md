**Execute Program** progress:

- ~Javascript Arrays:~ **{100%}** ⭐
- ~Javascript Concurrency:~ **{100%}** ⭐
- ~Regular Expressions:~ **{100%}** ⭐
- Modern Javascript: 81%<br> 

---

#### Finished reading: 
"O'reilly's Javascript: The Good Parts"
<details>
<summary>Key points</summary><br>
  
- Always use scope,
- Retrieval can be done with either dot notation, or with square brackets,
- A function always returns a value or if unspecified, it returns undefined,
- Javascript only has array-like objects which are slower than 'real' arrays,
- Inner functions have access to the actual parameters of the outer functions (not copies),
- Or `||` operand can be used to fill in default values for nonexistent data to prevent an undefined error,
- Do not use `for in` as it does not iterate through the properties in order and sometimes pulls in from further up the prototype chain,

- (Cascades, Memoization, Global Abatement)


</details>

#### Started reading:<br><br>
"Don't Make Me Think: A Common Sense Approach To Web Usability by Steve Krug"<br>
- Learned the word "satisfice", which is a portmanteau of "Satisfy" and "Suffice".<br>

"The Markdown Guide by Matt Cone"<br>

---

In some regex systems, `/.{,5}/` means "at most five characters". That's not true in JS which interprets it as a literal string.
```js
/^.{,5}$/.test('.{,5}'); // true
```

---

Found out that there are two functions to check if something is NaN.<br>
```js
Number.isNan(x) // good
isNan(x) // bad
``` 

---

Learned shorthand destructuring and .bind method

```js
const user = { name: 'Amir' };
const userName = () => { return this.name; }
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
const {cat: {name}} = user;
```

---

**Sets**:

A set's size reflects the number of unique values that it holds. Duplicates passed to the constructor or added with .add don't contribute to the size.
An array's method `.includes` slows down as an array gets longer, a set's method `.has` mostly fixes this problem.

```js
const names = new Set(['Amir', 'Betty', 'Amir']);
//methods
names.add("Jim");
names.delete("Jim");
names.clear();
names.has(name)
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
amir.name = 'Amir';
```

The setter tried to do `this.name = newName`, which called the setter again, which did `this.name = newName` again until we hit the maximum stack size, which causes the JavaScript runtime to error.

---

**Computed Properties in classes**

When the class is being constructed, the virtual machine evaluates the string to get the method or accessor name. After the class is defined, those names won't change.

```
