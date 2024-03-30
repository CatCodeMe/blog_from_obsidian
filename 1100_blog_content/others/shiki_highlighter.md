---
{"title":"test shiki highlighter","description":null,"dg-publish":true,"dg-path":null,"date":"2024-03-29 12:24:06","updated":"2024-03-29 12:28:51"}
---


```jsx {"1":5} del={"2":7-8} ins={"3":10-12} /active/ showLineNumbers
// labeled-line-markers.jsx
<button
  role="button"
  {...props}
  value={value}
  className={buttonClassName}
  disabled={disabled}
  active={active}
>
  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>
```