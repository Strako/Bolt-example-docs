# Separator Component

This code file defines a `Separator` component that serves as a visual divider in a user interface. It utilizes the `@radix-ui/react-separator` library to create a customizable separator element.

## Dependencies
- `@radix-ui/react-separator`: A library for creating accessible separator components in React.
- `React`: The core library for building user interfaces.
- `../../lib/utils`: A utility module that provides helper functions, including the `cn` function for class name manipulation.

## Separator Component

The `Separator` component is a wrapper around the `SeparatorPrimitive.Root` component from the Radix UI library. It allows for customization of the separator's orientation and styling.

### Key Functionalities
- Supports both horizontal and vertical orientations.
- Accepts additional class names for styling.
- Can be marked as decorative, which affects accessibility.

### Props
- `className` (string, optional): Additional class names to apply to the separator.
- `orientation` (string, optional): Determines the orientation of the separator. Defaults to `"horizontal"`. Acceptable values are `"horizontal"` and `"vertical"`.
- `decorative` (boolean, optional): Indicates whether the separator is purely decorative. Defaults to `true`.
- `...props`: Any additional props are passed to the `SeparatorPrimitive.Root` component.

### Return Value
- Returns a `SeparatorPrimitive.Root` element configured with the specified props and styles.

### Example Usage
```jsx
import { Separator } from './path/to/Separator';

const MyComponent = () => (
  <div>
    <p>Content above the separator</p>
    <Separator orientation="horizontal" className="my-custom-class" />
    <p>Content below the separator</p>
  </div>
);
```

### Edge Cases and Assumptions
- Assumes that the `className` prop will not conflict with the default styles applied to the separator.
- The component is designed to handle both orientations, but the layout should be tested to ensure proper rendering in different contexts.

