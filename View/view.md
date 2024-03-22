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

> We must be use `{{}}` and same key name that we used in route

```powertshell
<body>
    {{$name}}

</body>

```

##### Shortcute Method of previous type:

> [!NOTE]
> url, viewName <br>
> url, viewName, ArrayOfData

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

This is for Muliple data:

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

> [!WARNING]
> New Section is start:

## Take Parameter from the URL:

The Url:

```powershell
http://127.0.0.1:8000/user/123
```

```powershell
Route::get('user/{p_id}',function($id){
    return view('user',['pass_id'=>$id]);
});
```

```powershell
<body>
{{$pass_id}}
</body>
```

#### Muultiple parameter:

```powershell
http://127.0.0.1:8000/mypost/111/99
```

```powershell
Route::get('mypost/{post_id}/{cata_id}',function($pid,$catid){
    return view('mypost',['post_id'=>$pid,'catagory_id'=>$catid]);
});

```

```powershell
<body>
Post id: {{$post_id}}<br>
Catagory ID: {{$catagory_id}}
</body>
```

##### Optional Parameter:

```powershell
http://127.0.0.1:8000/student/
http://127.0.0.1:8000/student/Fahim

```

```powershell
Route::get('student/{name?}',function($name=null){
    return view('student',['name'=>$name]);
});
```

```powershell
<body>

    The Name is: {{$name}}
</body>
```

#### Using Reqular expression:

```powershell
http://127.0.0.1:8000/product/mobile
```

```powershell
Route::get('product/{p_name}',function($product_name){
    return view('myProduct',['name'=>$product_name]);
})->where('p_name','[A-Za-z]+');
```

Or ||

```powershell
Route::get('product/{p_name}',function($product_name){
    return view('myProduct',['name'=>$product_name]);
})->where('p_name','[0-9]+');

```

OR |||

```powershell

Route::get('product/{p_name}/{p_id}',function($product_name,$product_id){
    return view('myProduct',['name'=>$product_name,'id'=>$product_id]);
})->whereAlpha('p_name')->whereNumber('p_id');
```

```powershell
<body>
Product Name: {{$name}}
Product id: {{$id}}
</body>
```

### view Redirect:

```powershell
Route::view('login','register');
```

### The fallback function:

```powershell
Route::fallback(function(){

return view('defult');
});
```


