### Work of Route:

> [!NOTE]
> Every application are start from here.
> User enter or clicked a url then it go to route;
> Suppose user enter in
> **_ https//::127.1.2.1/about _**

### Basic Syntex of route

> [!NOTE]
> this Route returning string

```powershell
    Route::get('URL',closure/callBack);
```

```powershell
   Route::get('/about',function(){
       return "Hello World"
   });
```

### Route with parameter:

**_Systex_**

```powershell
    Route::get('url/{p_para}',finction($p_para){
        return $p_para;
    });
```

### Route Multiple Parameter:

**_syntex_**

```powershell
    Route::get('post/{post_id}/comment/{comment_id}',function($post_id,$commect_id{
            return $post_id.$comment_id;
    }));
```

### Optional Routes Paramenter:

- In the previous example we must assign the id but in here if have id then run one function else it will not.

```powershell
    Route::get('post/{name?}',function($name=null){ })
```

### Routes Parameter and Regular Expression:

- It means the parametter is numaric or alphabating,, we will fixed it.

```powershell
    Route::get('url/{p_para}',function($para){
        return $para;
    })->where('p_para','Regular_Expression');
```

##### For Example:

```powershell
    Route::get('url/{p_para}',function($para){
        return $para;
    })->where('p_para','A-Za-z);
```

> For Multiple Parameter:

```powershell
    Route::get('url/{id}/{name}',function($id,$name){
        return $para;
    })->where(['id'=>'0-9+'],['name'=>'a-z+']);
```

##### For Regular expression with Helper Methods:

```powershell
    Route::get('url/{id}/{name}',function($id,$name){
        return $para;
    })->whereNumber('id')->whereAlpha('name');
```

    - Uuid have one option

### Routes Redirect:

> [!NOTE]
> By defult it redirect to 302 error status code

```powershell
    route::redirect('/here','/there');

```

### FallBack Route

> [!NOTE]
> When user give wrong url then it will work
> you must define it in the last

### Route Method:

- route::get('url',callback);
- route::post('url',callback);
- route::put('url',callback);
- route::patch('url',callback);
- route::delete('url',callback);
- route::option('url',callback);

### Route Multipule Method:

- route::match(['get','post'],'/','funtion(){});
- route::any('url',function(){});

## Real Code Example:

### When user give `/about` then it will show in webpage

```powershell
    Route::get('about',function(){
    return "This is about page";
});

```

#### With using comment id:

```powershell
    http://127.0.0.1:8000/user/1234
```

```powershell
    Route::get('user/{p_id}',function($id){
    return  $id;
});

```

It will retrun 1234, if http://127.0.0.1:8000/user/fahim <br>
It will return fahim. cause we not given regular expression.

#### Multiple parameter:

```powershell
Route::get('comment/{id}/comment/{comment_id}',function($id,$comment_id){
    return  $id . $comment_id;
});

```

```powershell
http://127.0.0.1:8000/comment/111/comment/99
```

### Optional Parameter:

```powershell
Route::get('name/{name?}',function($name=null){
    return  $name;
});

```

```powershell
http://127.0.0.1:8000/name/fahim
```

```powershell
http://127.0.0.1:8000/name
```

#### Use the Reqular expression:

you can create reqular expression;

```powershell
Route::get('product/{P_name}',function($product_name){
    return  $product_name;
})->where('P_name','[A-Za-z]+');
```

```powersell
    http://127.0.0.1:8000/product/fahim
```

This is not valid:

```powershell
    http://127.0.0.1:8000/product
```

#### Route Redirect:

```powershell
http://127.0.0.1:8000/redir
```

```powershell
http://127.0.0.1:8000/fahim
```

```powershell
Route::redirect('rdir', 'fahim', 301);
```

### Route Fallback:

```powershell
Route::fallback(function(){
    return "Not page exist";
});

```
