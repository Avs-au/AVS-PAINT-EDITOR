@echo off
color 0A
setlocal enabledelayedexpansion

:: Tamaño del lienzo
set filas=10
set columnas=20

:: Inicializar lienzo con espacios
for /L %%i in (1,1,%filas%) do (
    set "linea="
    for /L %%j in (1,1,%columnas%) do (
        set "linea=!linea! "
    )
    set "lienzo%%i=!linea!"
)

:menu
cls
echo ==============================
echo         AVS PAINT BATCH
echo ==============================
echo 1. Mostrar lienzo
echo 2. Pintar celda
echo 3. Salir
set /p opcion="Elige una opcion: "

if "%opcion%"=="1" goto mostrar
if "%opcion%"=="2" goto pintar
if "%opcion%"=="3" exit

goto menu

:mostrar
cls
for /L %%i in (1,1,%filas%) do (
    echo !lienzo%%i!
)
pause
goto menu

:pintar
set /p fila="Fila (1-%filas%): "
set /p columna="Columna (1-%columnas%): "
set /p simbolo="Simbolo: "

:: Reemplazar caracter en la fila
set "linea=!lienzo%fila%!"
set "parte1=!linea:~0,%columna%-1!"
set "parte2=!linea:~%columna%!"
set "lienzo%fila%=%parte1%%simbolo%%parte2%"

goto menu
