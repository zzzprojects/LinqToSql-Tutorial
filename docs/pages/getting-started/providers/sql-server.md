# SQL Server

## Introduction

In LINQ to SQL, you can access SQL Server databases just like accessing an in-memory collection by using the LINQ technology.

```csharp

using (var db = new CustomerDbDataContext(@"Data Source=(localdb)\ProjectsV13;Initial Catalog=CustomerContextDB;"))
{
    var customers = db.Customers.ToList();

    foreach (var customer in customers)
    {
        Console.WriteLine(customer.FirstName + ", " + customer.LastName);
    }
}
```
