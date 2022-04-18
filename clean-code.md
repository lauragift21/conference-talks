build-lists: true

# [fit] _Writing Clean Code_

## for Humans

[.footer: _Women Coding The Future - Online, April 2022_]

---

## [fit] Why Does Clean Code _Matter?_

---

✅ A good way to keep your code maintainable?

---

✅ Its a good practice when you work with a large team?

---

### How do you classify _Bad Code?_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297133/clean-code-image_sqeerl.png)

Shh... Code Review In Progress!

---

## What's wrong with this code?

[.code-highlight: all]
[.code-highlight: 2, 2-6]

```js
// bad code
$.ajax({
  url: "/api/getWeather",
  data: {
    zipcode: 97201
  },
  success: function( data ) {
    $( "#weather-temp" ).html( "" + data + " degrees" );
  }
});
```

---

_Bad code is code that is difficult to understand and creates technical debt._

---

_No one understands it except the person who wrote it._

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650296868/IMG_1840.jpg_cbsffn.jpg)

What bad code looks like.

---

## _Later_ = Never[^⭐️]

[^⭐️]: Learn more about the [LeBlanc's Law](https://yiming.dev/clipping/2019/03/21/le-blanc's-law-a-k-a-later-equals-never/#:~:text=LeBlanc's%20Law%3A%20%22Later%20equals%20Never,fast%20you%20can%20deliver%20value.).

---
<!-- 
[.column]

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297019/FQjbylcacAIHFTH.jpeg_pszbor.jpg)

[.column]

--- -->

![inline]
(https://res.cloudinary.com/lauragift/image/upload/v1650297031/1__otRqc1VYyfa2m3enVmsuQ.png_im85be.png)

Messy code in a long term causes a lot of problems!

---

## Best Practices for Writing _Clean Code_

---

## What is Clean Code?

---

_Clean code is code that is comprehensive and easy to understand._

_Code that anyone can read and understand other than the developer who wrote it._

---

> Clean code always looks like it was written by
> **someone who cares!**

-- Michael Feathers

---

## Use Meaningful _Naming Conventions_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297061/1_7LO7JEAZbo6YmN8feAVCwg_g73zqy.png)

Who else is guilty?

---

## Write Clean _Functions_

---

## Good Code _Comments_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297074/1_JokD47K7oc3WPCcY86dKww_rzlcgx.jpg)

---

## Formatting _/ Style Guide_

---

## TDD _Principles_

---

## Error _Handling_

---

# _Clean Code_ Principles

---

## K.I.S.S

### _Keep it Simple, Stupid_

---

### D.R.Y

### _Don't Repeat Yourself_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297101/1_QemPnfHFxtlZhJRRdxna2Q_fxvsg0.jpg)

_W.E.T ( We enjoy typing!)_

---

### Y.A.G.N.I

### _You ain't gonna need it_

---

![inline](https://res.cloudinary.com/lauragift/image/upload/v1650297085/sketch_fbv0q2.png)

YAGNI PRINCIPLE

---

## Boy's Scout Rule

---

### _”Always leave the_ code cleaner _than you found it”_

---

## _How You Can Tell Your Code is Clean_

- Can someone else pick this up and understand what you wrote?
- How easy is it going to be to update or add new features further down the line?
- How easy is it going to be to maintain this codebase?
- Do you constantly break existing functionality when making changes?
- When you have to go back and add/modify a feature, is it difficult?

---

## What to do next?

---

## _Best Practices for Writing Clean Code_

- Use meaningful naming  conventions
- Write clean functions
- Good code comments
- Format and use a style guide
- Follow TDD principles
- Handle errors correctly

---

## _Remember:_

### "Always leave the code cleaner than you found it"

---

# _Resources_

- [Clean Code Book - Robert Martin](https://www.oreilly.com/library/view/clean-code-a/9780136083238/)
- [Code Complete - Steve McConnell](https://www.oreilly.com/library/view/code-complete-2nd/0735619670/)
- [Introduction to Clean Code and Software Design Principles](https://workat.tech/machine-coding/tutorial/introduction-clean-code-software-design-principles-nwu4qqc63e09)
- [Writing Clean Code for Humans - Cory House](https://www.pluralsight.com/courses/writing-clean-code-humans)
  
---

# Thank You!
