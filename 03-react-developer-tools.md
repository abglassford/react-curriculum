# React Developer Tools

In this chapter, you'll learn what the React Developer Tools are, why they're important, and how to use them. By the end, you'll have used them to inspect and edit personal as well as production React applications.

| Duration by yourself | Duration as a class |
|----------------------|---------------------|
| TBD                  | TBD                 |

## What are the React Developer Tools?

React Developer Tools are a Chrome extension and Firefox add-on that allow you to inspect and edit React applications from within the browser's developer tools panel.

Go ahead and install the React Developer Tools for both browsers.

* [Chrome extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
* [Firefox add-on](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)

**WARNING:** Due to a [Chrome bug](https://github.com/facebook/react-devtools/issues/172), the next set of instructions only works in Firefox.

Once installed, open the **Hello world** application from the previous chapter in your browser, load up its developer tools panel, and click on the **React** tab. You should see something like this:

![Hello world in React Developer Tools](https://i.imgur.com/FjJThwt.png)

## Why are the React Developer Tools important?

The React Developer Tools are the fastest way to find bugs in a React application. For example, expanding and mousing over a component in the tree view on the left will highlight its corresponding DOM element in the browser window above.

![Highlighting components](https://dl.dropboxusercontent.com/s/azxubbiq211irvj/ED27249A-568E-48BC-A971-B6E560701DF3-40520-000107C8A563DA86.gif?dl=0)

**NOTE:** The colors of the collapsable triangles in the tree view provide extra information about their adjacent component.

| Triangle color | Component type  | Has state? |
|----------------|-----------------|------------|
| Red            | Component class | Yes        |
| Black          | Component class | No         |
| Gray           | HTML tag        | N/A        |

Additionally, selecting a component in the tree view on the left allows you to inspect and edit its current props and state in the panel on the right. When a props or state value is changed, the component hierarchy is updated and re-rendered.

![Editing a component's state](https://dl.dropboxusercontent.com/s/02ohh014d3mt1to/DF6C8888-3E88-48D6-BF76-00A6BEEA94ED-40520-00010832DD3ABD60.gif?dl=0)

**NOTE:** Not every change to a props or state value will result in the DOM being updated. When it comes to component classes, it depends on the `ReactElement` object that's returned from its `render` function.

### Exercise

Navigate your browser to [Codecademy's landing page](https://www.codecademy.com/) and open up the React Developer Tools. What changes can you make to the application's props and state values that will cause the browser window to render a different DOM?

## What else can you do with the React Developer Tools?

In the breadcrumbs bar, you can inspect the selected component, the component that created it, the component that created that one, and so on.

![Inspecting component breadcrumbs](https://dl.dropboxusercontent.com/s/8h3k0uu7wvxzg6j/F3082FCC-1F2C-44E4-8748-BC9BC80DB701-40520-000108DCB021CB13.gif?dl=0)

Below the breadcrumbs, you can use the search bar to find components by their name and content.

![Searching for a component](https://dl.dropboxusercontent.com/s/aoecnz8y8pod23m/0AFF4646-E807-4FA1-9B12-403396CC4BB3-40520-00010911BD7BAFB5.gif?dl=0)

### Exercise

Find another React application from this list of [sites using React](https://github.com/facebook/react/wiki/Sites-Using-React). What else you can uncover with your new x-ray vision?

## What's a React component exactly?

With the React Developers Tools, you can finally see that **components** are instances of React component classes and HTML tags. And, a component hierarchy is made up of a root component that possibly has children, grandchildren, etc.

We can confirm this by rendering a second component hierarchy inside the **Hello world** application using the same root component class. First, let's add another container element to the DOM right under the existing container element.

```html
<div id="helloAgain"></div>
```

Then, we'll add another `ReactDOM.render` function call right under the existing function call.

```jsx
ReactDOM.render(
  <Hello />,
  document.getElementById('helloAgain')
);
```

Refresh the browser and voilà! Now, the application now has two distinct and isolated component hierarchies.

![Two component hierarchies](https://dl.dropboxusercontent.com/s/o5tch5gpi5fgkj0/F2582C11-85FC-48B5-B7CB-F8FCFF246E32-40520-00010A39EC7A6348.gif?dl=0)

### Exercise

In your own words, write down how you might reuse a component hierarchy and for what specific use cases.

Then, log into your [Facebook](https://www.facebook.com/) account, if you have one, and see if you can figure out which component hierarchies are being reused on the timeline.

## Summary

In this chapter, you were exposed to the fundamentals of the React Developer Tools. You got to practice inspecting and editing both personal and production React applications. At this point, you're ready to write larger, more sophisticated React applications.

## Assignment

**WARNING:** Due to a [Chrome bug](https://github.com/facebook/react-devtools/issues/172), the first half of this assignment only works in Firefox.

If you haven't already, inspect and edit your **sportball team** assignment from the previous chapter using the React Developer Tools. Make sure you understand the application's component hierarchy and its state before moving on to the next part of the assignment.

Afterwards, read the article called [Thinking in React](https://facebook.github.io/react/docs/thinking-in-react.html) from the official React documentation. It's a great entry point to understanding how larger React applications are structured. When you're finished, write down the biggest lessons you learned from the article.

## Reference

[GitHub - facebook/react-devtools](https://github.com/facebook/react-devtools)
