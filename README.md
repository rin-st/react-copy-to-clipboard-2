# react-copy-to-clipboard-2

React component for copying text to the clipboard.

## Features

- Based on the battle-tested [react-copy-to-clipboard](https://www.npmjs.com/package/react-copy-to-clipboard) package
- Functional component approach
- TypeScript support
- Adds possibility to focus on the element and copy its content by pressing Enter

## Installation

```bash
npm install react-copy-to-clipboard-2
```

```bash
yarn add react-copy-to-clipboard-2
```

```bash
pnpm add react-copy-to-clipboard-2
```

```bash
bun add react-copy-to-clipboard-2
```

## Usage

```jsx
import React, { useState } from "react";
import { CopyToClipboard } from "react-copy-to-clipboard-2";

function App() {
  const [value, setValue] = useState("");
  const [copied, setCopied] = useState(false);
  const handleCopy = (text: string, result: boolean) => {
    setCopied(result);
  };

  return (
    <div style={{ display: "flex", flexDirection: "column", gap: "4px" }}>
      <input value={value} onChange={(e) => setValue(e.target.value)} />
      {copied && <span style={{ color: "green" }}>Copied!</span>}
      <CopyToClipboard text={value} onCopy={handleCopy}>
        <button>Copy to clipboard</button>
      </CopyToClipboard>
      <textarea placeholder="Paste your copied text here" />
    </div>
  );
}
```

## API

#### Props

- `text` (string, required): The text to be copied to the clipboard.
- `children` (React.Element, required): The child elements to be wrapped by the component.
- `onCopy` ((text: string, result: boolean) => void, optional): Callback function called after copying.
- `options` ({
  debug?: boolean;
  message?: string;
  format?: string;
  }, optional): Additional options for clipboard behavior. See [copy-to-clipboard](https://www.npmjs.com/package/copy-to-clipboard#api) for details.

## License

MIT

## Contributing

Contributions are welcome! Please feel free to submit a PR.
