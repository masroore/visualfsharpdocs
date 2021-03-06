---
title: SqlEntityConnection Type Provider (F#)
description: SqlEntityConnection Type Provider (F#)
keywords: visual f#, f#, functional programming
author: dend
manager: danielfe
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: visual-studio-dev14
ms.assetid: a86f4095-8a09-4ad9-8735-6d71efeedad3 
---

# SqlEntityConnection Type Provider (F#)

Provides the types to access a database, using a LINQ to Entities mapping. This type provider is useful when you are using the ADO.NET Entity Model for a database.

**Namespace/Module Path:** Microsoft.FSharp.Data.TypeProviders

**Assembly:** FSharp.Data.TypeProviders (in FSharp.Data.TypeProviders.dll)


## Syntax

```
type SqlEntityConnection<?ConnectionString : string,                         ?ConnectionStringName : string                         ?LocalSchemaFile : string,                         ?Provider : string,                         ?EntityContainer : string,                         ?ConfigFile : string,                         ?DataDirectory : string,                         ?ResolutionFolder : string,                         ?ForceUpdate : bool,                         ?Pluralize : bool,                         ?SuppressForeignKeyProperties : bool>
```

## Static Type Parameters


|Type Parameter|Description|
|--------------|-----------|
|?ConnectionString : string|The connection string for the database connection.|
|?ConnectionStringName : string|The name of the connection string for the database connection in the configuration file.|
|?LocalSchemaFile : string|The path to a .csdl file that contains the schema. This parameter is often used with ForceUpdate set to true.|
|?Provider : string|The name of the ADO.NET data provider to be used. The default is **System.Data.SqlClient**.|
|?EntityContainer : string|The name to use for the generated type that represents the container for the entities, also known as the data context. The default value is EntityContainer.|
|?ConfigFile : string|The name of the configuration file that’s used for connection strings. The default value is app.config or web.config.|
|?DataDirectory : string|The name of the data directory that replaces &#124;DataDirectory&#124; in connection strings. The default value is the project or script directory.|
|?Resolution Folder : string|A folder to be used to resolve relative file paths at compile time. The default value is the folder that contains the project or script.|
|?ForceUpdate : bool|Determines whether the type provider updates the generated types to reflect changes in the database schema. When **ForceUpdate** is false, the provider reacts to changes in the **LocalSchemaFile**. The default value is true.|
|?Pluralize : bool|If true, uses plural forms for the generated type names. The default value is false.|
|?SuppressForeignKeyProperties : bool|Exclude foreign key properties in entity type definitions. The default value is false.|

## Remarks
For a walkthrough that shows how to use this type provider, see [Walkthrough: Accessing a SQL Database by Using Type Providers and Entities &#40;F&#35;&#41;](Walkthrough-Accessing-a-SQL-Database-by-Using-Type-Providers-and-Entities-%5BFSharp%5D.md).

The Entity Data Model Framework is a library for the .NET Framework that allows you to define a database schema largely independent of a specific data source (such as a SQL database). For more information, see [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) and [Entity Framework Overview](https://msdn.microsoft.com/library/bb399567.aspx). Database schemas that are represented by the Entity Data Model are encoded in a specific XML format in files with the .edmx extension.

The following table describes types generated by the SqlEntityConnection type provider for a declaration of the form:

```
type MyDb = SqlEntityConnection<parameters>
```

In the following table, *EntityContainer* is the single type generated by edmgen.exe, which has base type **T:System.Data.Objects.ObjectContext**. This is the value of the static parameter **EntityContainer**, if it is given. Otherwise, it is the name chosen by edmgen.exe.



|Type|Description|
|----|-----------|
|MyDb|The overall container type.<br /><br />Contains a method **GetDataContext** that returns a simplified view of the data context. The method returns a new instance of MyDB.ServiceTypes.SimpleDataContextTypes.*EntityContainer*. The version with the connectionString parameter may be used when the connection string is determined at runtime.|
|MyDb.ServiceTypes|Contains the embedded full types and simplified types for the database.|
|MyDb.ServiceTypes.&#42;|The embedded types generated by EdmGen.exe.|
|MyDb.ServiceTypes.*EntityContainer*|The data context type, inherited from **T:System.Data.Objects.ObjectContext**.|
|MyDb.ServiceTypes.SimpleDataContextTypes.*EntityContainer*|Contains one method for each method of the full context type, including stored procedures and functions. The methods return **T:System.Data.Linq.ISingleResult&#96;1**.<br /><br />Contains one property for each property of the full context type. The properties return **T:System.Data.Linq.Table&#96;1**.<br /><br />The property Connection gets the database connection as an instance of **T:System.Data.Common.DbConnection**.<br /><br />The property DataContext gets the full data context, of type **T:System.Data.Objects.ObjectContext**. This is the base type of the *EntityContainer* type generated by the type provider.|
The Entity Data Model connection string that you specify at runtime when you call GetDataContext resembles the following:

```
metadata=res://*/entityNamespaceName.csdl|res://*/entityNamespaceName.ssdl|res://*/entityNamespaceName.msl;provider=provider;provider connection string="connectionString"
```

For more information about connection strings for the Entity Data Model, see [Connection Strings](https://msdn.microsoft.com/library/ms254494.aspx)


## Platforms
Windows 8, Windows 7, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 4.0


## See Also
[Microsoft.FSharp.Data.TypeProviders Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Data.TypeProviders-Namespace-%5BFSharp%5D.md)

[Walkthrough: Accessing a SQL Database by Using Type Providers and Entities &#40;F&#35;&#41;](Walkthrough-Accessing-a-SQL-Database-by-Using-Type-Providers-and-Entities-%5BFSharp%5D.md)

[EdmxFile Type Provider &#40;F&#35;&#41;](EdmxFile-Type-Provider-%5BFSharp%5D.md)

[EDM Generator &#40;EdmGen.exe&#41;](https://msdn.microsoft.com/library/bb387165)

[Entity Framework Overview](https://msdn.microsoft.com/library/bb399567.aspx)

