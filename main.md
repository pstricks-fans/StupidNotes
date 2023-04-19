# A counter-intuitive element addition

```csharp
using System;
using System.Collections.Generic;


var foo = new Foo
{
    data = { 4, 5, 6 }  // Appending in disguise! 
};

Console.Write(string.Join(", ", foo.data)); // 1, 2, 3, 4, 5, 6

class Foo
{
    public  IList<int> data = new List<int>() { 1, 2, 3 };
}
```

```csharp
using System;
using System.Collections.Generic;

var data = new List<int>() { 1, 2, 3 };

// However, it cannot be done outside object initializer
// data = { 4, 5, 6 };
// instead use
data.AddRange(new int[] { 4, 5, 6 });
Console.Write(string.Join(", ", data)); // 1, 2, 3, 4, 5, 6
```
