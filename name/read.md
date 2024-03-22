> [!NOTE]
> Remeber the Flow
> url -> route -> function -> model? -> view

#### USE With 
Set the url
```powershell
<a href="{{route('home')}}">Home</a>

```
set the route:
```powershell
Route::get('/', function () {
    return view('welcome');
})->name('home');

```
> You can Now use the name;

### Use with parameter:
1.URL set:

```powershell
<a href="{{route('post',['category'=>'Mobile'])}}">post</a>

```
2. Route define:
> [!NOTE]
> the key of the url will be must same route url paramter name.
> return view key must same the calling view key

```powershell
Route::get('post/{category}', function ($cat) {
    return view('mypost', ['cat' => $cat]);
})->name('post');

```
```powershell
<body>
    This is my POST
    and category:{{ $cat }};
</body>

```
