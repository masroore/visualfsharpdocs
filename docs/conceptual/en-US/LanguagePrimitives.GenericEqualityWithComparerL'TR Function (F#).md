# LanguagePrimitives.GenericEqualityWithComparer<'T> Function (F#)

Compare two values for equality.

**Namespace/Module Path:** Microsoft.FSharp.Core.LanguagePrimitives

**Assembly:** FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD



```


// Signature:
GenericEqualityWithComparer : IEqualityComparer -> 'T -> 'T -> bool (requires equality)

// Usage:
GenericEqualityWithComparer comp e1 e2


```



#### CAPS_PARAMETERS_MD
*comp*
Type: **T:System.Collections.IEqualityComparer**


The comparer object.


*e1*
Type: **'T**


The first value.


*e2*
Type: **'T**


The second value.



**The result of the comparison.**
## CAPS_REMARKS_MD

## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0, Portable




## See Also
[Core.LanguagePrimitives Module &#40;F&#35;&#41;](Core.LanguagePrimitives+Module+%28F%23%29.md)

[Microsoft.FSharp.Core Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Core+Namespace+%28F%23%29.md)
