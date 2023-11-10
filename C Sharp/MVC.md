-> MVC stands for Model View Controller
-> MVC is a design pattern
->Model - Handles all data-related logic. Interacts with Database.
->View - Handles UI part of the application(data representation)
-> Controller - Handles request flow, and acts as an intermediary between view and model.

<b>Project File</b>
-> We can see project file in `Project.csproj` -> there is the syntax name `<ItemGroup></ItemGroup>` under here all packages comes which we installed.

<b>Program.cs File</b>
This is the main file

<b>Dependency Injection </b>
Tight Coupling -> Tight coupling is when a group of classes are highly dependent on one another. ex Class A can inherit member variable and methods from Class B and Class C. When certain things are changed in Class B or Class C then it will also affect to Class A. 
-> It is difficult to maintain
-> It is difficult to test

Loose Coupling -> Loose Coupling means that the classes are independent of each other. or classes are too less independent.
->Easy maintain
->Easy to test

->Dependency injection is achieved using interfaces.
-> Interfaces are a powerful tool to use for decoupling -> decoupling is the process of converting tight coupling to loose coupling.
->Classes can communicate through interfaces rather than other concrete classes.
-> Dependency injection is software pattern.
-> DI is basically providing the objects that an object needs, instead of having it constructs the objects themselves.
-> We the help of DI, we can write loosely code.
-> DI is achieved by writing loosely couple code.

-> 3 Types 
1) Constructor Injection
2) Setter or property Injection
3) Method Injection

1) Constructor Injection -> 

<i> Controller name should be `HomeController.cs ` and in View ->Home folder should be there  to define HomeController.cs  and name of view file should be as function or action method name inside the Controller like Index.cshtml if there is Index() method in Controller</i>

<i> Under View there folder called Shared folder which contains the partial view and `_Layout.cshtml` is the master page for all pages and `_ViewStart.cshtml` contains the default master page for the application, we can also define different master page for certain page.</i>

<b> Tag Helper </b>
ex -> `<form class="form-horizontal" method="post" asp-controller="Users" asp-action="Index"></form>`
-> `<form class="form-horizontal" method="post" asp-page="Users/Index"></form>`

<b> Action Result </b>
Both on MVC and Razor Pages certain action result have certain return type like `ViewResult` action will return `View` as well as in Razor Pages `PageResult` action will return `Page` but there will be condition arise where in one action method have to return based on conditions where return type will be two or more , in that case then using `ViewResut` or `PageResult` will not be used, we use `IActionResult` action which is flexible for many return types. `IActionResult ` is the parent class.