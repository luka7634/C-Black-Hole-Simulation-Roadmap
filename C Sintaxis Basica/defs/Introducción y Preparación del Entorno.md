### ¿Qué es C y para qué sirve?

C es un lenguaje de programación procedimental creado en los años setenta por Dennis Ritchie en Bell Labs.  
Ofrece un control directo sobre memoria y hardware, lo que lo hace ideal para sistemas operativos, compiladores y desarrollo embebido.  
Su sintaxis minimalista y eficiencia lo convirtieron en la base de muchos lenguajes modernos y en un estándar en informática de alto rendimiento.  
Aprender C te brinda los fundamentos del funcionamiento interno de la máquina y las técnicas para escribir código portable y optimizado.

---

### Instalar un compilador (GCC, Clang, MinGW)

Para transformar tu código C en binarios necesitas un compilador:

- Linux (Ubuntu/Debian):
    
    ```bash
    sudo apt update
    sudo apt install build-essential
    ```
    
- macOS (Homebrew o Xcode):
    
    ```bash
    xcode-select --install
    # o
    brew install gcc
    ```
    
- Windows (MinGW-w64):
    1. Descarga el instalador de MSYS2 y ejecuta la terminal MSYS2.
    2. En la terminal, corre:
        
        ```bash
        pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
        ```
        
    3. Añade `C:\msys64\ucrt64\bin` al PATH de Windows.

---

### Elegir y configurar un editor (VS Code, Sublime, Vim)

Selecciona un editor con soporte para C y configuración de compilación:

- VS Code: instala la extensión “C/C++” de Microsoft. Configura un `tasks.json` para compilar y un `launch.json` para depurar.
- Sublime Text: añade paquetes como “SublimeClang” o “EasyClangComplete” y define build systems con comandos `gcc`.
- Vim/Neovim: integra plugins como “YouCompleteMe” o “coc.nvim”, configura `makeprg=gcc\ %\ -o\ %<` y complementos de lint.

Estos ajustes te ofrecen resaltado de sintaxis, autocompletado, saltos a definición y atajos para compilar y ejecutar sin salir del editor.

---

### Escribir y ejecutar tu primer "Hola Mundo"

1. Crea el archivo `hola_mundo.c` con este contenido:
    
    ```c
    #include <stdio.h>
    
    int main(void) {
        printf("Hola Mundo\n");
        return 0;
    }
    ```
    
2. Compila y ejecuta:
    
    - En Linux/macOS:
        
        ```bash
        gcc hola_mundo.c -o hola_mundo
        ./hola_mundo
        ```
        
    - En Windows (MinGW-w64):
        
        ```bash
        gcc hola_mundo.c -o hola_mundo.exe
        hola_mundo.exe
        ```
        

Si ves en pantalla `Hola Mundo`, ¡felicidades! Acabas de compilar y ejecutar tu primer programa en C.

---

Con esto tienes el entorno listo para avanzar. ¿Quieres que preparemos un Makefile o un script Bash que automatice estos pasos y valide tu instalación?