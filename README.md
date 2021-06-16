# WINE console app creation
Пара слов о компиляции, развертывании и запуске win-приложений на C++ с помощью WINE под Linux.
## 1. Пакеты
Установка WINE:
```
sudo apt install wine-stable
```
Установка компилятора:
```
sudo apt install mingw-w64
```
## 2. Visual Studio
```
sudo apt install snap
sudo snap install --classic code
```
## 3. Ключи компиляции
```
/usr/local/bin/x86_64-w64-mingw32-gcc -o app.exe main.c -mwindows
```
## 4. Запуск
```
wine app.exe
```
### Источники
https://husl.ru/questions/941756  
https://www.securitylab.ru/analytics/521188.php  
https://www.winehq.org/
