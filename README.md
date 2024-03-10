## CFS1010 Lab 1

You've been hired to code a To Do list app! We'll build it step-by-step.

## Step 1

Create a component called `ToDoItem` that renders a checkbox and a text field. The component should track its state with the [useState hook](https://react.dev/reference/react/useState). This is an example of a common pattern - a [controlled component](https://codedamn.com/news/reactjs/what-are-controlled-and-uncontrolled-components-in-react)!

_Hints:_

- You can use `<input type="checkbox" />` and `<input type="text" />` for the checkbox and textfield
- Use the `onChange` prop to capture [change events](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event) and call `setState`

## Step 2 - Save/Edit

Add a "Save" button beside the text field.

_When the user clicks Save..._

- replace the text field with regular non-editable text
- replace the Save button with an Edit button

_When the user clicks Edit..._

- the Save button should reappear
- the text should be editable again.

Make sure to disable the Save button when the text field is empty!

## Step 3 - Hover Effects!

A designer has taken a look at your progress so far, and they have some feedback:

> When the text has been saved, the "Edit" button should only show up when the user is hovering over the task.

_Hints:_

- You can use the `onMouseEnter` and `onMouseLeave` props to capture [mouseenter](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event) and [mouseleave](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event) events

## Step 4 - Multiple To-Do list items

Underneath the To-Do list, add an "Add" button and a "Remove" button to add and remove tasks from the bottom of the To-do list.

_Hints:_

- Add a `useState` to track the number of todos. Add and Remove should increment/decrement the count respectively.

## Step 5 - Removing individual tasks

Next, we'll want to be able to remove specific tasks from the To-Do list. To accomplish this, we'll want to [lift state](https://react.dev/learn/sharing-state-between-components)

In `ToDoItem`:

- Add a "Remove" button, and a `handleRemove` prop
- convert the `useState` hooks for the checkbox and text field to props

In `App.jsx`:

- Add `const [todos, setTodos] = useState([{ title: 'Get groceries', isChecked: false }])`
- Map the `todos` state to the `<ToDoItem />` component
- Implement functions `setIsChecked` and `setTitle` for a to-do item at a particular index

Once we're done with that refactor, we can implement the remove button:

In `ToDoItem`:

- Add a "Remove" button, and a `handleRemove` prop

In `App.jsx`:

- Implement `handleRemove` for a to-do item at a particular index
