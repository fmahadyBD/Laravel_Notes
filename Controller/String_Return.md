### To create controller comand:
```powershell
        php artisan  make:controller  AboutController
```

#### How to retun:
user clicked the url
```powershell
    http://127.0.0.1:8000/about
```
url goes to Route:
```powershell
    Route::get('about',[AboutController::class,'show']);
```
Then it call the controller:
```powershell
class AboutController extends Controller
{
    function show(){
        return "This is controller";
    }
}

```

#### parameter with controller:
User hit the url with id parameter:
```powershell
http://127.0.0.1:8000/about/1234
```

Url to Route , It will passed the url to controller;

```powershell
Route::get('about/{id}',[AboutController::class,'show']);
```
The Controller class functions show will recived the parameter

```powershell
class AboutController extends Controller
{
    function show($id){
        return "This is about with id : ".$id;
    }
}

```

