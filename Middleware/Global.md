### Global Middleware Wth 503 exception Under construction

> [!WARNING]
> It will be apply ervey route in because it is in global

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
 protected $middleware = [

        \App\Http\Middleware\UnderConst::class,


```
> [!WARNING]
> For registationn in global: ```middleware``` in there will be added the name of the controller of us


> [!NOTE]
> How to modify the building 503 or others view file?
 ***step 01: ***
            create a folder name ```errors``` in the resourse view
 ***setp 02: ***
            Create 503 file then can modify all of them


```powershell

```