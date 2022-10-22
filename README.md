**Execute Program** progress:

- ~Javascript Arrays:~ **{100%}**
- ~Javascript Concurrency:~ **{100%}**<br>
- Regular Expressions: 85%<br>
- Modern Javascript: 13%<br>

---

Finished reading: **`"O'reilly's Javascript: The Good Parts"`**
<details>
<summary>Key points</summary><br>
  
- Always use scope 
- Demystified some grammar 

</details>

Started reading:<br><br>
**`"Don't Make Me Think: A Common Sense Approach To Web Usability by Steve Krug"`**<br>
**`"The Markdown Guide by Matt Cone"`**<br>
- Learned the word "satisfice", which is a portmanteau of "Satisfy" and "Suffice".

---

In some regex systems, .{,5} means "at most five characters". That's not true in JS. JS interprets it as a literal string.
```js
/^.{,5}$/.test('.{,5}');
```

---

Returns true.

Found out that there are two isNan() functions.<br>
```js
Number.isNan()
``` 
and 
```js
.isNan()
```
