# modern-csharp

## Object Initialisation
Old way ❌
``` csharp
  // Old Way
  Dictionary<string, string> dictionary = new Dictionary<string, string>();
  dictionary.Add("Backend", ".Net");
  dictionary.Add("Frontend", "React");
  dictionary.Add("Database", "SQL");
```
Modern way ✔️
```csharp
  var dictionary = new Dictionary<string, string>
  {
      { "Backend", ".Net"},
      { "Frontend", "React"},
      { "Database", "SQL"}
  };
```
Old way ❌
```csharp
    public class Employee
    {
        public string Name { get; set; }
        public int Id { get; set; }
    }
    
    var emp = new Employee();
    emp.Name ="github";
    emp.Id = 123;
```
Modern way ✔️
```csharp
    public class Employee
    {
        public string Name { get; set; }
        public int Id { get; set; }
    }
   
    var emp = new Employee
    {
      Name ="github",
      Id = 123
    };
```
### All about Null
Old way ❌
```csharp
  if(emp == null)
  {
    // do something
  }
```
Modern way ✔️
```csharp
  if(emp is null)
  {
    // do something
  }
```
Old way ❌
```csharp
obj = obj == null ? new Employee() : obj;

// OR
  if(obj == null)
  {
    obj = new Employee();
  }

```
Modern way ✔️
```csharp
obj ??= new Employee();
```
Old way ❌
```csharp
  int? val = 0;
  if(anotherVal != null)
  {
    val = anotherVal;
  }

```
Modern way ✔️
```csharp
  int? val = anotherVal ?? 0;
```
Old way ❌
```csharp
  string fullName = "";
  if(obj != null)
  {
    fullName = obj.GetFUllName();
  }
```
Modern way ✔️
```csharp
  string fullName = obj?.GetFullName();
```
Old way ❌
```csharp
  if(obj == null)
  {
    throw new ArgumentNullException(nameof(obj));
  }
```
Modern way ✔️
```csharp
  _ = obj ?? throw new ArgumentNullException(nameof(obj));
```
## Lambda
Old way ❌
```csharp
  public string override ToString()
  {
     return $"{FirstName} {LastName}";
  }
```
Modern way ✔️
```csharp
  public string override ToString() => $"{FirstName} {LastName}";
```
Old way ❌
```csharp
  public class Employee
  {
    public string Name { get; set; }
    public Employee(string name)
    {
      Name = name;
    }
    
  }
```
Modern way ✔️
```csharp
  public class Employee
  {
    public string Name { get; set; }
    public Employee(string name) => Name = name;
  }
```
