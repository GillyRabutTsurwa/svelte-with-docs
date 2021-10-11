# Spread Props
- this topic was a bit tricky
- here i learnt how to use the spread operator to spread the properties of our component, instead of defining them one by one
- here's how we do it
  - in our JavaScript, make an object (can be called anything)
  - the properties of this object match *exactly* to the properties that the component accepts
  - the values of the properties are simply what they are
  - and so we can define our component like this:
```jsx
<Component {...objectName}>
```
- this is because props is (very very likely) an object and each time we define props for a component, the props object gets populated with the appropriate property name and value respectively
- so, we are taking the contents of our made object, and spreading them on the props object. i understand