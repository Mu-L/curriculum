### Introduction

All HTML documents have the same basic structure or boilerplate that needs to be in place before anything useful can be done. In this lesson, we will explore the different parts of this boilerplate and see how it all fits together.

### Lesson overview

This section contains a general overview of topics that you will learn in this lesson.

- How to write the basic boilerplate for an HTML document.
- How to open HTML documents in your browser.

### Creating an HTML file

To demonstrate an HTML boilerplate, we first need an HTML file to work with.

Create a new folder on your computer and name it `html-boilerplate`. Within that folder create a new file and name it `index.html`.

You're probably already familiar with a lot of different types of files, for example doc, pdf, and image files.

To let the computer know we want to create an HTML file, we need to append the filename with the `.html` extension, as we have done when creating the `index.html` file.

It is worth noting that we named our HTML file `index`. We should always name the HTML file that will contain the homepage of our website `index.html`. This is because web servers will by default look for an `index.html` page when users land on our websites -- and not having one will cause big problems.

### The DOCTYPE

Every HTML page starts with a doctype declaration. The doctype's purpose is to tell the browser what version of HTML it should use to render the document. The latest version of HTML is HTML5, and the doctype for that version is `<!DOCTYPE html>`.

The doctypes for older versions of HTML were a bit more complicated. For example, this is the doctype declaration for HTML4:

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

However, we probably won't ever want to be using an older version of HTML, so we'll always use `<!DOCTYPE html>`.

Open the `index.html` file created earlier in your text editor and add `<!DOCTYPE html>` to the very first line.

### HTML element

After we declare the doctype, we need to provide an `<html>` element. This is what's known as the root element of the document, meaning that every other element in the document will be a descendant of it.

This becomes more important later on when we learn about manipulating HTML with JavaScript. For now, just know that the `<html>` element should be included on every HTML document.

Back in the `index.html` file, let's add the `<html>` element by typing out its opening and closing tags, like so:

```html
<!DOCTYPE html>
<html lang="en">
</html>
```

Noticed the word `lang` here? It represents an HTML attribute which is associated with the given HTML tag i.e. `<html>` in this case. These attributes provide additional information about HTML elements. (More about `HTML attributes` in the following lesson.)

#### What is the lang attribute?

`lang` specifies the language of the text content in that element. This attribute is primarily used for improving accessibility of the webpage. It allows assistive technologies, for example screen readers, to adapt according to the language and invoke correct pronunciation.

### Head element

The `<head>` element is where we put important meta-information **about** our webpages, and stuff required for our webpages to render correctly in the browser.
Inside the `<head>`, we **should not** use any element that displays content on the webpage.

Back in our `index.html` file, let's add a `<head>` element with a `<meta>` element and a title within it. The `<head>` element goes within the `<html>` element and should always be the first element under the opening `<html>` tag:

```html
<!DOCTYPE html>

<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Webpage</title>
  </head>
</html>
```

#### Meta element

We should always have the `<meta>` tag with the charset encoding of the webpage in the `<head>` element: `<meta charset="UTF-8">`.

Setting the encoding is very important because it ensures that the webpage will display special symbols and characters from different languages correctly in the browser.

#### Title element

Another element we should always include in the head of an HTML document is the `<title>` element:

 `<title>My First Webpage</title>`

The `<title>` element is used to give webpages a human-readable title, which is displayed in our webpage's browser tab. For example, if you look at the current tab's name of your browser, it will read "HTML Boilerplate &#124; The Odin Project"; this is the `<title>` of the current `.html` file.

If we didn't include a `<title>` element, the webpage's title would default to its file name. In our case that would be `index.html`, which isn't very meaningful for users; this would make it very difficult to find our webpage if the user has many browser tabs open.

There are many more elements that can go within the head of an HTML document. However, for now it's only crucial to know about the two elements we have covered here. We will introduce more elements that go into the head throughout the rest of the curriculum.

### Body element

The final element needed to complete the HTML boilerplate is the `<body>` element. This is where all the content that will be displayed to users will go - the text, images, lists, links, and so on.

To complete the boilerplate, add a `<body>` element to the `index.html` file. The `<body>` element also goes within the `<html>` element and is always below the `<head>` element, like so:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Webpage</title>
  </head>

  <body>
  </body>
</html>
```

### Viewing HTML files in the browser

The HTML boilerplate in the `index.html` file is complete at this point, but how do you view it in the browser? There are a couple of different options:

<div class="lesson-note lesson-note--warning" markdown="1">

#### Use Google Chrome

In order to avoid branching our lesson's instructions to accommodate for all of the differences between browsers, we are going to be using Google Chrome as our primary browser for the remainder of this course. All references to the browser will pertain specifically to Google Chrome. We **strongly** suggest that you use Google Chrome for all of your testing going forward.

</div>

1. You can drag and drop an HTML file from your text editor into the address bar of your browser.

1. You can find the HTML file in your file system and then double click it. This will open up the file in the default browser your system uses.

1. You can use the terminal to open the file in your browser:
   - Ubuntu: Navigate to the directory containing the file and type `google-chrome index.html`
   - macOS: Navigate to the directory containing the file and type `open ./index.html`
   - WSL: Navigate to the directory containing the file and type `explorer.exe index.html`. Note, this will open up the file in the default browser your system uses.

Using one of the methods above, open up the `index.html` file we have been working on. You'll notice the screen is blank. This is because we don't have anything in our body to display.

Back in the `index.html` file, let's add a heading (more on these later) to the body, and save the file:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Webpage</title>
  </head>

  <body>
    <h1>Hello World!</h1>
  </body>
</html>
```

Now, if you refresh the page in the browser, you should see the changes take effect, and the heading "Hello World!" will be displayed.

### VSCode shortcut

VSCode has a built-in shortcut you can use for generating all the boilerplate in one go. Please note that this shortcut only works while editing a file with the `.html` extension or a text file with the HTML language already selected. To trigger the shortcut, delete everything in the `index.html` file and just enter `!` on the first line. This will bring up a couple of options. Press the <kbd>Enter</kbd> key to choose the first one, and voila, you should have all the boilerplate populated for you.

You may notice that the boilerplate produced by this shortcut includes a line we have not yet mentioned:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

This is not something we need to know about until we discuss responsive design, an advanced topic involving different screen sizes which we will cover much later in the curriculum. For now, you can leave that line as it is.

It's still good to know how to write the boilerplate yourself in case you find yourself using a text editor like notepad (heaven forbid), which doesn't have this shortcut. Try not to use the shortcut in your first few HTML projects, so you can build some muscle memory for writing the boilerplate code.

### Assignment

<div class="lesson-content__panel" markdown="1">

1. Watch and follow along to Kevin Powell's brilliant [Building Your First Web Page video](https://www.youtube.com/watch?v=V8UAEoOvqFg&t=93s).

1. Build some muscle memory by deleting the contents of the `index.html` file and trying to write out all the boilerplate again from memory. Don't worry if you have to peek at the lesson content the first few times if you get stuck. Just keep going until you can do it a couple of times from memory.

1. Run your boilerplate through the W3 [HTML validator](https://validator.w3.org/#validate_by_input). Validators ensure your markup is correct and are an excellent learning tool, as they provide feedback on syntax errors you may be making often and aren't aware of, such as missing closing tags and extra spaces in your HTML.

</div>

### Knowledge check

The following questions are an opportunity to reflect on key topics in this lesson. If you can't answer a question, click on it to review the material, but keep in mind you are not expected to memorize or master this knowledge.

- [What is the purpose of the doctype declaration?](#the-doctype)
- [What is the HTML element?](#html-element)
- [What is the purpose of the head element?](#head-element)
- [What is the purpose of the body element?](#body-element)

### Additional resources

This section contains helpful links to related content. It isn't required, so consider it supplemental.

- Another option for opening your HTML pages in the browser is using the [Live Preview extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server) for VSCode. This will open your HTML document and automatically refresh it every time you save the document. However, we recommend avoiding this extension at first. Instead, open and refresh your HTML page manually in the browser. This helps you build a solid understanding of the basic development workflow before relying on tools and extensions.
- If you wish, you can add [the `lang` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang) to individual elements throughout the webpage.
- If you are curious about charset encodings, [W3C's article on character encoding](https://www.w3.org/International/articles/definitions-characters/) does a great job explaining it.
