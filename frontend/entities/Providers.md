# Providers

The providers are the main state management tool that is going to be used across the application, in this case these are in charge of spreading the data across the child components based on a custom hook.

## How to

```jsx
// providers/Image/Image.provider.tsx
type TContext {
  image?: Image;
  isLoading: boolean;
}

export const Context = createContext<IContext>({
  image: undefined;
  isLoading: false;
});

type TProps {
  children: React.ReactNode;
  imageId: string;
}

export const useEnvironment = () => useContext(Context);

const ImageProvider = ({children, imageId}: TProps) => {
  const {data: image = {}, isLoading} = useQuery(['image', imageId], () => ImageGateway.getById(imageId));

  const value = useMemo<IContext>(
    () => ({
      image,
      isLoading,
    }),
    [image, isLoading]
  );

  return <Context.Provider value={value}>{children}</Context.Provider>;
};

export default ImageProvider;
```

### Folder Structure

```
providers/
  Image/
    Image.provider.tsx
    index.ts
```
