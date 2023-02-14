# Pages

The Pages are different from the Components as they first follow the Next.js Page standard, which specifies the way they need to be named and written.

## How to

As we are going to be following a container-component pattern, the Pages' main functionality is to gather information from the request (query params, path params, etc.), instantiate the used providers and render the main component.

```jsx
// pages/image/{imageId}.tsx
const ImageDetailPage: NextPage = () => {
  const {imageId = ''} = useParams();

  return (
    <ImageProvider imageId={imageId}>
     <ImageDetail />
    </ImageProvider>
  )
};
```
