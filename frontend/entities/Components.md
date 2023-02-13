# Components

A components should contain the bare minimum to render an UI section, in this case, I believe components should be treated as `Pure Functions`, which provides a simple standard to follow and makes them more reusable across the application.

## How to

Components are constituted by a main file, a styles file and an `index.ts` file to be exported. It looks as the following:

```
/Component
  Component.tsx
  index.ts
  Component.styled.ts
```

In case that there is a need to include a custom hook, it should be under a `hooks/` folder under the same component directoy.

```
/Component
  Component.tsx
  index.ts
  Component.styled.ts
  hooks/
    useTime.ts
```
