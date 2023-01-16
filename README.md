# CS_DepuracionInteractivaDeApp.NET-E3
Comprobación de condiciones con Assert

En algunas situaciones, puede que quiera detener toda la aplicación en ejecución cuando no se cumpla una determinada condición. Mediante el uso de `Debug.Assert`
, puede comprobar una condición y generar información adicional sobre el estado de la aplicación. Vamos a agregar una comprobación justo antes de la instrucción "return" para tener la seguridad de que n2 es 5.

```csharp
// If n2 is 5 continue, else break.
Debug.Assert(n2 == 5, "The return value is not 5 and it should be.");
return n == 0 ? n1 : n2;
```

La lógica de la aplicación ya es correcta, así que vamos a actualizar `Fibonacci(5);` a `Fibonacci(6);`, lo que tendrá un resultado diferente.

Depure la aplicación. Cuando se ejecuta `Debug.Assert` en el código, el depurador detiene la aplicación para que pueda inspeccionar las variables, la ventana de inspección, la pila de llamadas, etc. También envía el mensaje a la consola de depuración.

Resultado

```
---- DEBUG ASSERTION FAILED ----
---- Assert Short Message ----
The return value is not 5 and it should be.
---- Assert Long Message ----

   at Program.<<Main>$>g__Fibonacci|0_0(Int32 n) in C:\Users\Jon\Desktop\DotNetDebugging\Program.cs:line 23
   at Program.<Main>$(String[] args) in C:\Users\Jon\Desktop\DotNetDebugging\Program.cs:line 3
```

Detenga la depuración y, luego, ejecute la aplicación sin depurar escribiendo el siguiente comando en el terminal:

```bash
dotnet run
```

La aplicación finaliza después de producirse un error en la aserción y registrarse la información en la salida de la aplicación.

Resultado

```
Process terminated. Assertion failed.
The return value is not 5 and it should be.
   at Program.<<Main>$>g__Fibonacci|0_0(Int32 n) in C:\Users\Jon\Desktop\DotNetDebugging\Program.cs:line 23
   at Program.<Main>$(String[] args) in C:\Users\Jon\Desktop\DotNetDebugging\Program.cs:line 3
```

Ahora, vamos a ejecutar la aplicación en la configuración `Release`
 con el siguiente comando en el terminal:

```bash
dotnet run --configuration Release
```

La aplicación se ejecuta correctamente hasta su finalización, porque ya no estamos en la configuración `Debug`.

Enhorabuena, ha depurado de forma correcta y eficaz el código mediante las características de .NET, como `Debug.WriteLine` y `Debug.Assert`. Buen trabajo.

[![Assert1.png](https://i.postimg.cc/zfPPQ4r3/Assert1.png)](https://postimg.cc/zLKjbt31)

[![Assert2.png](https://i.postimg.cc/MTC36RXS/Assert2.png)](https://postimg.cc/zbkFpynt)

[![Assert3.png](https://i.postimg.cc/26bXNTkG/Assert3.png)](https://postimg.cc/JD8QbNBH)
