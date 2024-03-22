### Create Component:
> [!NOTE]
> It use for reuse the code
> This command will automaticlly create a folder in view. We can also mention with the name menullay
> View in resouce and Vew in App Both create a conponent folder
#
```powershell
php artisan make:component Card
```
We Edit the resourse view folder component view file.

```powershell
<div>
   <h1>This is card Title</h1>
   <h4>This is Sub title</h4>
   <p>This is discription box</p>
   <hr>
</div>

```

Then we Render it in our main blade file; <x-nameOfComponent>

```powershell
<x-card/>
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