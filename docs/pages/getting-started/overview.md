#Overview

## Introduction

Entity Framework Core is a lightweight, extensible and cross-platform version of Microsoft's object-relational mapper (ORM), Entity Framework is the official data access platform for Microsoft. 

 - As .NET evolves towards a lighter weight cross-platform environment, Entity Framework is making the same transition. 
 - In other words, this was not simply an update from the latest Entity Framework (EF6), but it is a different kind of Entity Framework. 
 - It includes a set of .NET APIs for performing data access in your application. 

## History

 - EF team has made some significant changes over Entity Framework 6 and called it EF7, but later they rename it to EF Core.
 - EF Core was first released in late June of 2016 after over 2 years of effort, this first version was followed by a great amount of change with EF Core 2, which was released a year later along with .NET Core and ASP.NET Core. 
 - EF Core 2 is seen by many as the first solid version, although EF Core 1 is still supported.

```csharp
public class Customer
{
    public int CustomerId { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public string Address { get; set; }
    public virtual List<Invoice> Invoices { get; set; }
}

public class Invoice
{
    public int Id { get; set; }
    public DateTime Date { get; set; }

    public int CustomerId { get; set; }

    [ForeignKey("CustomerId")]
    public virtual Customer Customer { get; set; }
    public virtual List<InvoiceItem> Items { get; set; }
}

public class InvoiceItem
{
    public int InvoiceItemId { get; set; }
    public int InvoiceId { get; set; }
    public string Code { get; set; }

    [ForeignKey("InvoiceId")]
    public virtual Invoice Invoice { get; set; }
}
```
