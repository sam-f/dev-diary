# Template literal types

You can define string types that perform validation like this:

```typescript
type URL = `${'http' | 'https'}://${string}.${string}`
```

Which will validate that your URL begins with either `HTTP` or `HTTPS` and has the `://` as well as atleast one `.`.
