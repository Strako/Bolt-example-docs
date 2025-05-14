# Chat Bubble Component

This code file defines a set of React components for creating chat bubbles, including message display, timestamps, and action buttons. It utilizes the `class-variance-authority` library for managing CSS class variants and includes utility functions for class name manipulation.

## Dependencies
- React
- class-variance-authority
- Custom utility functions from `@/lib/utils`
- Button component from a local module

## ChatBubble Component

### Purpose
The `ChatBubble` component serves as a container for chat messages, allowing for different layouts and styles based on whether the message is sent or received.

### Key Methods and Attributes
- **Props**:
  - `variant`: Determines the alignment of the chat bubble (received or sent).
  - `layout`: Defines the layout style (default or AI).
  - `className`: Additional CSS classes for customization.
  
### Usage
```jsx
<ChatBubble variant="sent" layout="ai">
  Your message here
</ChatBubble>
```

## ChatBubbleMessage Component

### Purpose
The `ChatBubbleMessage` component displays the actual message content within a chat bubble, with support for loading states.

### Key Methods and Attributes
- **Props**:
  - `variant`: Determines the background and text color based on message type (received or sent).
  - `layout`: Defines the layout style (default or AI).
  - `isLoading`: A boolean that indicates if the message is in a loading state.
  - `className`: Additional CSS classes for customization.

### Usage
```jsx
<ChatBubbleMessage variant="received" isLoading={true}>
  Loading message...
</ChatBubbleMessage>
```

## ChatBubbleTimestamp Component

### Purpose
The `ChatBubbleTimestamp` component displays the timestamp of a chat message.

### Key Methods and Attributes
- **Props**:
  - `timestamp`: A string representing the time the message was sent.
  - `className`: Additional CSS classes for customization.

### Usage
```jsx
<ChatBubbleTimestamp timestamp="10:30 AM" />
```

## ChatBubbleAction Component

### Purpose
The `ChatBubbleAction` component represents an action button within a chat bubble, such as reply or delete.

### Key Methods and Attributes
- **Props**:
  - `icon`: A React node representing the button's icon.
  - `onClick`: Function to handle button clicks.
  - `variant`: Button style variant (default is "ghost").
  - `size`: Size of the button (default is "icon").
  - `className`: Additional CSS classes for customization.

### Usage
```jsx
<ChatBubbleAction icon={<SomeIcon />} onClick={handleClick} />
```

## ChatBubbleActionWrapper Component

### Purpose
The `ChatBubbleActionWrapper` component wraps action buttons and controls their visibility based on the chat bubble's hover state.

### Key Methods and Attributes
- **Props**:
  - `variant`: Determines the position of the action buttons (sent or received).
  - `className`: Additional CSS classes for customization.

### Usage
```jsx
<ChatBubbleActionWrapper variant="sent">
  <ChatBubbleAction icon={<SomeIcon />} onClick={handleClick} />
</ChatBubbleActionWrapper>
```

## Edge Cases and Assumptions
- The code assumes that the `children` passed to `ChatBubble` are valid React elements.
- The `isLoading` prop in `ChatBubbleMessage` defaults to `false`, indicating that messages are not loading unless specified.
- The components are designed to work within a React application and may require additional styling to fit specific design requirements.

