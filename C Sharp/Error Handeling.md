<b> Server Side Handeling </b>
-> we can use `ModelState.IsValid` property to check if it is valid or not.

<b>Client Side Validation </b>
->we can do client side validation by adding _validationScripts from Shared folder -> we can add by this ->
```
@section Scripts
{
<partial name="_ValidationScriptsPartial" />
}
```

this is the way we can send error message to client side using client side validation and server side-> `<span asp-validation-for="Name" class="text-danger"></span>` 
here `Name` is model class member and if we don't want to throw model property in the error message then we can add
```
[DisplayName("Display Order")]
public int DisplayOrder {get; set;}

-> now asp-validation-for="DisplayOrder" will not display DisplayOrder instead it display Display Order
```
-> Also we have Range annotations where it checks values range like->
```
[Range(1,100,ErrorMessage="Display Order must be between 1 and 100 only!!"]
```


-> Suppose if user enter first name and second name same then we can do validation by ->
```
if(obj.FirstName == obj.SecondName)
{
 ModelState.AddModelError("CustomError","The first Name and Second Name cannot be same");
}
```
