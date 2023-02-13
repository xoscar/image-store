# Models

Models are the representation of the structured data that used in the application, often defined by the I/O responses from the third party services.
The job of the models includes the following:

1. Validating data. Verifying nullable values, adding defaults to prevent the app from breaking.
2. Calculating derived values. This way you can calculate values that will be often done at during the rendering cycle.
3. Adding functionality. You can attach custom functionality to models to be latter use by components or services.

## How to

A model should specify a factory function to generate the object structure, receive the unchecked data and return the verified values.

```ts
// models/Image.model.ts
type Image = {
  fileName: string;
  type: string;
  date: Date;
}

type TRawImage =  Partial<Image & {
  date: string;
}> 


const Image = ({firstName = '', type = '', date = new Date().toISOString()}: TRawImage): Image => ({
  fileName,
  type,
  date: new Date(date)
});

export default Image;
```
