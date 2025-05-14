# Auto Scroll Hook Documentation

This code file defines a custom React hook, `useAutoScroll`, which provides functionality for automatically scrolling a container to the bottom when new content is added. It is particularly useful for chat applications or any interface where new messages or items are dynamically loaded.

## Dependencies
- React (version 16.8 or higher for hooks)

## Class/Module Documentation

### `useAutoScroll`
The `useAutoScroll` hook manages the scroll behavior of a specified container. It allows for automatic scrolling to the bottom when new content is added and provides the ability to disable this behavior when the user scrolls up.

#### Key Functionalities:
- Automatically scrolls to the bottom of the container when new content is added.
- Allows users to disable auto-scrolling when they manually scroll up.
- Provides a reference to the scrollable element.

## Function/Method Documentation

### `useAutoScroll(options: UseAutoScrollOptions = {})`
#### Summary
This hook initializes the auto-scroll functionality for a specified container.

#### Parameters
- `options` (optional): An object that can contain the following properties:
  - `offset` (number, default: 20): The distance from the bottom of the scrollable area to consider as "at bottom."
  - `smooth` (boolean, default: false): If true, scrolling to the bottom will be smooth.
  - `content` (React.ReactNode): The content to be monitored for changes.

#### Return Values
- An object containing:
  - `scrollRef`: A reference to the scrollable element.
  - `isAtBottom`: A boolean indicating if the scroll position is at the bottom.
  - `autoScrollEnabled`: A boolean indicating if auto-scrolling is enabled.
  - `scrollToBottom`: A function to programmatically scroll to the bottom.
  - `disableAutoScroll`: A function to disable auto-scrolling.

#### Exceptions
- No specific exceptions are raised, but the hook assumes that the `scrollRef` will always point to a valid HTMLDivElement.

## Code Block Comments
```javascript
// Check if the user has scrolled to the bottom of the container
const checkIsAtBottom = useCallback((element: HTMLElement) => {
  const { scrollTop, scrollHeight, clientHeight } = element;
  const distanceToBottom = Math.abs(scrollHeight - scrollTop - clientHeight);
  return distanceToBottom <= offset;
}, [offset]);

// Scroll to the bottom of the container
const scrollToBottom = useCallback((instant?: boolean) => {
  if (!scrollRef.current) return;
  const targetScrollTop = scrollRef.current.scrollHeight - scrollRef.current.clientHeight;
  if (instant) {
    scrollRef.current.scrollTop = targetScrollTop;
  } else {
    scrollRef.current.scrollTo({
      top: targetScrollTop,
      behavior: smooth ? "smooth" : "auto",
    });
  }
  setScrollState({
    isAtBottom: true,
    autoScrollEnabled: true,
  });
  userHasScrolled.current = false;
}, [smooth]);
```

## Usage Example
```javascript
const { scrollRef, isAtBottom, disableAutoScroll } = useAutoScroll({ offset: 30, smooth: true });

// In your component
<div ref={scrollRef} onScroll={disableAutoScroll}>
  {/* Your content here */}
</div>
```

## Edge Cases and Assumptions
- The hook assumes that the content will be rendered within a div that can be scrolled.
- It behaves as expected when new content is added, but if the content is removed or the height of the container changes unexpectedly, the auto-scroll behavior may need to be manually managed.
- The hook does not handle cases where the `scrollRef` is not attached to a valid DOM element.

## End-user Documentation
This hook is designed for developers looking to implement auto-scrolling behavior in their React applications. It is particularly useful in chat interfaces or any application where new content is frequently added to a scrollable area.

