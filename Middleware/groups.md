### Group route Middleware Wth 503 exception Under construction

> [!WARNING]
> It will be apply groups route .

- Create Middleware using this command
```powershell
php artisan make:middleware NameofMiddleware
```
Then use it in the middleware file

```powershell
use Symfony\Component\HttpKernel\Exception\HttpException;
```
the remodify the function:

```powershell
    public function handle(Request $request, Closure $next): Response
    {
        throw new HttpException(503);

    }
```
> Now this is the time to register the middleware 
> It will be in the kernel.php file



```powershell
  protected $middlewareGroups = [
        'const'=>[
            \App\Http\Middleware\UnderConst::class,
        ],





```

> Now call it in the route using varibael  name:

```powersell


Route::middleware(['const'])->group(function () {
    Route::get('/', function () {
        return view('welcome');
    })->name('home');
    Route::get('about', [
        ReportController::class, 'show'
    ])->name('about');
});

```

