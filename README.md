**Execute Program** progress:

- ~Javascript Arrays:~ **{100%}** ⭐
- ~Javascript Concurrency:~ **{100%}** ⭐
- Regular Expressions: 98%<br>
- Modern Javascript: 26%<br>

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

In some regex systems, .{,5} means "at most five characters". That's not true in JS. JS interprets it as a literal string.
```js
/^.{,5}$/.test('.{,5}');
```

---

Returns true.

Found out that there are two isNan() functions.<br>
```js
Number.isNan(x)
``` 
and 
```js
isNan(x)
```

---

Learned shorthand destructuring and .bind method

```js
const user = { name: 'Amir' };
const userName = () => { return this.name; }
userName.bind(user);
userNameBound(); //'Amir'
```
