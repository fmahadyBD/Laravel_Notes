### Work of Route:
    - Every application are start from here. 
    - User enter or clicked a url then it go to route;
    - Suppose user enter in
    ``` https//::127.1.2.1/about ```

### Basic Syntex of route
>[!NOTE]
> this Route returning string 
    ```Route::get('URL',closure/callBack)```

> ```Route::get('/about',function(){
        return "Hello World"
    });```

### Route with parameter:
 ***Systex***
> ```Route::get('url/{p_para}',finction($p_para){
    return $p_para;
 });```

### Route Multiple Parameter:
***syntex***
```Route::get('post/{post_id}/comment/{comment_id}',function($post_id,$commect_id{ return $post_id.$comment_id}));```

### Optional Routes Paramenter:
- In the previous example we must assign the id but in here if have id then run one function else it will not.
```Route::get('post/{name?}',function($name=null){ })```

### Routes Parameter and Regular Expression:
- It means the parametter is numaric or alphabating,, we will fixed it.

```powershell 
    Route::get('url/{p_para}',function($para){
    return $para;
})->where('p_para','A-Za-z);```

- For Example:
