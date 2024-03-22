#### How to show view file from route:

This is the route:

```powershell
Route::get('contact',function(){
    return view('contact');
});
```

This is the view file:

```powershell
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    This is contact Page

</body>
</html>

```

### How to pass Data from Route to the view:

> [!NOTE]
> we must use the [] array to pass the data
> Name is the key
> Fahim this key's value

```powertshell

Route::get('contact',function(){
    return view('contact',['name'=>'Fahim']);
});

```

> We must be use {{}} and same key name that we used in route

```powertshell
<body>
    {{$name}}

</body>

```

##### Shortcute Method of previous type:

> [!NOTE]
> url,viewName
> url,viewName,ArrayOfData

```powertshell
Route::view('contacturl','contact');

```

```powertshell
<body>
This is contract page

</body>

```

Passing value:

```powertshell
Route::view('url','contact',['name'=>'Fahim']);

```

```powertshell

<body>
Hi {{$name}}

</body>
```

```powertshell
Route::view('url','contact',['name'=>'Fahim','username'=>'fmahadyBD','active'=>'yes']);

```

```powertshell

<body>
Name: {{$name}} <br>
Username: {{$username}} <br>
Active: {{$active}} <br>

</body>
```
##### How to pass single data using with methods:
```powershell
Route::get('url',function(){

    return view('contact')->with('name','fahim');
});

```

```powershell
<body>
    Name: {{ $name }} <br>
</body>

```



```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```