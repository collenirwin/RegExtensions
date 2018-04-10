# RegExtensions
C# extension methods for Regular Expressions

This small project aims to provide extension method versions of every **static** method in the [`System.Text.RegularExpressions.Regex`](https://docs.microsoft.com/en-us/dotnet/api/system.text.regularexpressions.regex?view=netframework-4.7.1) class. Wrapped methods include `IsMatch`, `Match`, `Matches`, `Replace` (use `RegexReplace`), and `Split` (use `RegexSplit`) with all of their overloads.

`EnumerableMatches` is currently the only addition. It simply casts the result of `Matches` to `IEnumerable<Match>`.

# Examples

### IsMatch
```csharp
"1234".IsMatch(@"\d{4}"); // true
"Hello, world!".IsMatch("hello", RegexOptions.IgnoreCase); // true
```

### Match
```csharp
"123abc".Match("[a-z]"); // "a"
```

### Matches
```csharp
"123abc".Matches("[a-z]"); // "a", "b", "c"
```

### RegexReplace
```csharp
"123abc".RegexReplace("[a-z]+", "321"); // "123321"
"123abc".RegexReplace(@"\d", m => (int.Parse(m.Value) + 1).ToString()); // "234abc"
```

### RegexSplit
```csharp
"Wow     here's  lots of\nspace".RegexSplit(@"\s+"); // "wow", "here's", "lots", "of", "space"
```
