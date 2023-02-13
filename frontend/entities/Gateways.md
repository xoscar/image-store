# Gateways

The gateways encapsulate the I/O logic that will be used across the application, as well as Services, these are static modules that provide a list of functions.
As part of the gateway job is to generate the model instances based on the response as well as error handling.

```ts
const ImageGateway = () => ({
  async getUserById(userId: string) {
    const response = await fetch(path.replace('{{userId}}', userId));

    if (!response.ok) throw Error('user not found')

    const rawUser = await response.json();

    return User(rawUser);
  }
})

export default ImageGateway;
```
