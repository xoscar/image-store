# Pages

The Pages are different from the Components as they first follow the Next.js Page standard, which specifying the way that need to be named and written.

## How to

As we are going to be followin a container-component pattern, Pages main functionality is to gather information from the request (query params, path params, etc), instantiate the used providers and render the main component.

```jsx
// pages/user/{userId}.tsx
const UserDetailPage: NextPage = () => {
  const {userId = ''} = useParams();

  return (
    <UserProvider userId={userId}>
     <UserDetail />
    </UserProvider>
  )
};
```
