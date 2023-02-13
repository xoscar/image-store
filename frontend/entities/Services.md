# Services

As React is a UI library, we need to ensure to not overload components, providers or any other React entity with too much logic as it can become convoluted and more importantly hard to test.

Services are static modules that provide a list of pure functions that can be used across the application, can be used for calculations or data parsing/modeling.

## How to

```ts
// user service

const UserService = () => ({
  getUserDaysToBirthday(user: User): number {
    // ...logic

    return 0;
  },
});

export default UserService;
```
