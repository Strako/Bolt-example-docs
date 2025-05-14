# Chat Message Component

This code file defines a React component for displaying chat messages, including both questions and responses. It also includes a utility function for parsing links within the response text.

## Dependencies
- `lucide-react`: A library for icons used in the chat interface.
- `ChatHistoryItem`: A type imported from the application’s page, representing the structure of chat history items.
- `ChatBubble` and `ChatBubbleMessage`: Custom components used to render chat bubbles.

## ChatMessage Component

The `ChatMessage` component is responsible for rendering individual chat messages, including the user's question and the corresponding response. It is designed to be part of a larger chat interface.

### Props
- `message` (ChatHistoryItem): The chat history item containing the question and response.
- `index` (number): The index of the message in the chat history, used as a key for rendering.

### Usage
```jsx
<ChatMessage message={chatHistoryItem} index={0} />
```

## parseLinks Function

The `parseLinks` function takes a string input and converts any URLs found within the text into clickable anchor tags.

### Parameters
- `text` (string): The input string that may contain URLs.

### Return Value
- (string): The input string with URLs replaced by anchor tags.

### Example
```javascript
const formattedText = parseLinks("Check this link: https://example.com");
```

### Exceptions
- No specific exceptions are raised, but the function assumes that the input is a valid string.

## Edge Cases and Assumptions
- The code assumes that the `message` object will always contain either a `question` or a `response`, but not necessarily both.
- The `parseLinks` function assumes that the input text is well-formed and does not handle malformed URLs.

