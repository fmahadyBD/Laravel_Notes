##### SImple view return file:

```powershell
http://127.0.0.1:8000/about
```
Goto the route


```powershell
Route::get('about',[AboutController::class,'show']);
```

Goto the controller:

```powershell
class AboutController extends Controller
{
    function show(){
        return view('about');
    }
}

```

The return the view file

### Give it with parameter:

```powershell
http://127.0.0.1:8000/about/fahim
```
Goto the route and find the 


```powershell
Route::get('about/{para_test_without_matching}',[AboutController::class,'show']);

```

Then goto the the controller, fnction will recived the parameter

```powershell

class AboutController extends Controller
{
    function show($name){
        return view('about',['name'=>$name]);
    }
}

```

Now funtion will pass parameter by array with key name, and the view file will<br>
recived it by ```{{$key}}```

```powershell
<body>
    This is about me view file add name: {{$name}}
</body>

```

## How to pass muultiple value using in controller:


```powershell
http://127.0.0.1:8000/student
```


```powershell
Route::get('student',[AboutController::class,'student']);
```
We create an array for passing data:

```powershell
   function student(){
        $name=['name'=>'Fahim','roll'=>'469','subject'=>'CSE','class'=>'bsc'];
        return view('student',['x'=>$name]);
    }
```

How to recived it in view file:
```powershell
<body>

    Your name:{{$x['name']}}  <br>
    Your Roll:{{$x['roll']}}  <br>
    Your Class:{{$x['class']}}  <br>
    Your Subject:{{$x['subject']}}  <br>

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