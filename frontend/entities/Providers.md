# Providers

The providers are the main state management tool that is going to be used across the application, in this case, these are in charge of spreading the data across the child components based on a custom hook.

## How to

```jsx
// providers/User/User.provider.tsx
type TContext {
  user?: User;
  isLoading: boolean;
}

export const Context = createContext<IContext>({
  user: undefined;
  isLoading: false;
});

type TProps {
  children: React.ReactNode;
  userId: string;
}

export const useEnvironment = () => useContext(Context);

const UserProvider = ({children, userId}: TProps) => {
  const {data: user = {}, isLoading} = useQuery(['user', userId], () => UserGateway.getById(userId));

  const value = useMemo<IContext>(
    () => ({
      user,
      isLoading,
    }),
    [user, isLoading]
  );

  return <Context.Provider value={value}>{children}</Context.Provider>;
};

export default UserProvider;
```

### Folder Structure

```
providers/
  User/
    User.provider.tsx
    index.ts
```
