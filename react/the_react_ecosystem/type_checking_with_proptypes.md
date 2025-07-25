### Introduction

Type Checking is a process of verifying that a piece of code is using the correct data types for variables, function parameters and return values. In the context of React applications, we are going to use PropTypes to do that job.

PropTypes is a way to type check the props that a React component receives. It helps to catch potential type errors during development, making it easier to spot and fix bugs. If you have used a linter in your previous React projects, there's a good chance it ended up yelling at you about certain props missing in prop validation, however if that isn't the case- well, lucky you!

### Lesson overview

This section contains a general overview of topics that you will learn in this lesson.

- Setting up PropTypes.
- Using common PropTypes features.

### Getting started

<div class="lesson-note lesson-note--critical" markdown="1">

#### Important Note on React Version

propTypes and defaultProps are discontinued from React version 19. Please use React versions lesser than 19 to follow this lesson:

1. Set up React with Vite as usual. It does not matter whether you run `npm install` here or not.

1. Change the versions for the following four packages in `package.json` to `"^18"`:
    - `react`
    - `react-dom`
    - `@types/react`
    - `@types/react-dom`

1. Run `npm install`.

</div>

To start using PropTypes in our React projects, we first need to install the corresponding library. We can do that with `npm`. In your React project run the following command:

```bash
npm install --save prop-types
```

Next, we want to import the PropTypes package in the component whose props we want to validate.

```javascript
import PropTypes from 'prop-types';
```

### Using propTypes

Here is a very basic example of how we would use it in a component that renders out a name prop.

```jsx
import PropTypes from 'prop-types';

const RenderName = (props) => {
  return <div>{props.name}</div>;
};

RenderName.propTypes = {
  name: PropTypes.string,
};

export default RenderName;
```

In this example, the component RenderName expects to receive a prop called `name` which is a string. If this prop is not a string, a warning will be displayed. If you want to make sure a prop is being passed in, use isRequired like so:

```javascript
RenderName.propTypes = {
  name: PropTypes.string.isRequired,
}
```

### Using defaultProps

Another cool thing we can do in combination with PropTypes is passing in default props:

```jsx
import PropTypes from 'prop-types';

const RenderName = (props) => {
  return <div>{props.name}</div>;
};

RenderName.propTypes = {
  name: PropTypes.string,
};

RenderName.defaultProps = {
  name: 'Zach',
};

export default RenderName;
```

In this example, with the help of the defaultProps property we are defining a default value for the `name` prop. This way, if the `RenderName` component is called without passing in the `name` prop, it will default to "Zach". When you do pass in props, they will take precedence over the default props.

### What about TypeScript?

Now is also a good time to mention TypeScript - a strongly typed language that builds on JavaScript. We do not cover it in our curriculum and thus do not recommend looking into it now, but in the future, it may be worth learning if you’d like more type safety while writing your code.

Learning TypeScript can be a lot of overhead when you’re already learning React and the best way to prepare for this is to continue developing your JavaScript fundamentals. The TypeScript documentation encourages enhancing JavaScript skills before tackling TypeScript complexities, as highlighted in their [discussion on the importance of JavaScript fundamentals](https://www.typescriptlang.org/docs/handbook/typescript-from-scratch.html#learning-javascript-and-typescript). In the future however, if you do decide to go in the direction of learning TypeScript, our recommendation would be picking up a previous project and refactoring the components one by one to TypeScript.

### Assignment

<div class="lesson-content__panel" markdown="1">

1. Read through the [PropTypes documentation](https://reactjs.org/docs/typechecking-with-proptypes.html). It shows all of the types you can specify and some other useful things that can be done with it!
   - You may notice this resource suggests using TypeScript over PropTypes in modern React. This may well be true for production apps but for our purposes, we are solely interested in the concept of type checking within React, where TypeScript is out of scope.
1. You can even set up custom validators in PropTypes. For a more in-depth look into the benefits and use cases of PropTypes, read this comprehensive guide [Validating React Props with PropTypes on LogRocket](https://blog.logrocket.com/validate-react-props-proptypes/).
1. Dive into the nuanced comparison between PropTypes and TypeScript for type safety in React with this [StackOverflow post on differences between PropTypes and TypeScript](https://stackoverflow.com/questions/41746028/proptypes-in-a-typescript-react-application).

</div>

### Knowledge check

The following questions are an opportunity to reflect on key topics in this lesson. If you can't answer a question, click on it to review the material, but keep in mind you are not expected to memorize or master this knowledge.

- [How would we set up a basic implementation of PropTypes?](#using-proptypes)
- [If we pass in a prop to a component that has a defaultProp defined, what would happen?](#using-defaultprops)
- [What is the difference between PropTypes and TypeScript?](https://stackoverflow.com/questions/41746028/proptypes-in-a-typescript-react-application)

### Additional resources

This section contains helpful links to related content. It isn't required, so consider it supplemental.

- It looks like this lesson doesn't have any additional resources yet. Help us expand this section by contributing to our curriculum.
