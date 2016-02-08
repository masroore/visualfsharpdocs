# IntrinsicFunctions.SetArray3D<'T> Function (F#)

The standard overloaded associative (3-indexed) mutation operator

**Namespace/Module Path**: Microsoft.FSharp.Core.LanguagePrimitives.IntrinsicFunctions

**Assembly**: FSharp.Core (in FSharp.Core.dll)


## Syntax


```


// Signature:
SetArray3D : 'T [,,] -> int -> int -> int -> 'T -> unit

// Usage:
SetArray3D target index1 index2 index3 value

```



#### Parameters
*target*
Type: **'T**[[,,]](http://msdn.microsoft.com/en-us/library/b4e5b35b-dc83-4b50-94aa-85fcf3ccb2b0)


A three-dimensional array.


*index1*
Type: [int](http://msdn.microsoft.com/en-us/library/025d5455-3622-4ea5-9573-3ecbd4ee1375)


The index along the first dimension.


*index2*
Type: [int](http://msdn.microsoft.com/en-us/library/025d5455-3622-4ea5-9573-3ecbd4ee1375)


The index along the second dimension.


*index3*
Type: [int](http://msdn.microsoft.com/en-us/library/025d5455-3622-4ea5-9573-3ecbd4ee1375)


The index along the third dimension.


*value*
Type: **'T**


The new value to set at the specified indices.




## Remarks

## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0, Portable




## See Also
[LanguagePrimitives.IntrinsicFunctions Module &#40;F&#35;&#41;](LanguagePrimitives.IntrinsicFunctions+Module+%28FSharp%29.md)

[Core.LanguagePrimitives Module &#40;F&#35;&#41;](Core.LanguagePrimitives+Module+%28FSharp%29.md)
