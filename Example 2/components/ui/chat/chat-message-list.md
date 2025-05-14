# ChatMessageList Component

The `ChatMessageList` component is designed to display a list of chat messages in a scrollable container. It provides functionality to automatically scroll to the bottom of the list when new messages are added, and includes a button to manually scroll to the bottom if the user has scrolled up.

## Dependencies
- React: A JavaScript library for building user interfaces.
- Lucide React: A collection of icons for React applications.
- Custom UI components: Includes a `Button` component and a `useAutoScroll` hook from the project's UI library.

## ChatMessageList Component

### Purpose
The `ChatMessageList` component serves as a container for chat messages, allowing for smooth scrolling and user interaction.

### Key Features
- Automatically scrolls to the bottom when new messages are added.
- Provides a button to scroll to the bottom if the user is not currently viewing the latest messages.

### Props
- `className` (string): Additional CSS classes to apply to the outer container.
- `innerClassName` (string, optional): Additional CSS classes to apply to the inner message container.
- `smooth` (boolean, optional): If true, enables smooth scrolling behavior. Defaults to `false`.
- `...props` (HTMLAttributes<HTMLDivElement>): Any additional props to be passed to the outer div.

### Usage Example
```jsx
<ChatMessageList smooth={true} className="custom-class">
  <ChatMessage text="Hello, world!" />
  <ChatMessage text="How are you?" />
</ChatMessageList>
```

## Functionality

### useAutoScroll Hook
The `useAutoScroll` hook is utilized to manage the scrolling behavior of the chat message list. It provides the following functionalities:
- `scrollRef`: A reference to the scrollable container.
- `isAtBottom`: A boolean indicating whether the user is currently viewing the bottom of the message list.
- `scrollToBottom`: A function to programmatically scroll to the bottom of the message list.
- `disableAutoScroll`: A function to disable automatic scrolling when the user interacts with the scrollable area.

### Edge Cases and Assumptions
- The component assumes that the `children` prop will always contain valid React elements representing chat messages.
- If the user scrolls up, the automatic scrolling feature will be disabled until the user scrolls back to the bottom.
- The component does not handle cases where the `children` prop is empty; it will simply render an empty scrollable area.

## End-user Documentation
This component is intended for use in chat applications where displaying a list of messages is required. It enhances user experience by providing smooth scrolling and easy navigation to the latest messages.

