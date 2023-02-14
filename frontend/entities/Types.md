# Types

The standard used for `Typescript` is the following:

1. Every type should start with `T` e.g `TImage`.
2. Model types should have the same name as the factory e.g. `Image`.
3. Components should define the prop types with `TProps`.
4. Instances should be only used when there is a feature not supported by `Types`.

## Example Type

```ts
// types/Images.types.ts
export type TImage = {
  mimetype: string;
  size: number;
  name: string;
  id: string;
}

export type TRawImage = Partial<TImage>;
```
