# WINE console app creation
Пара слов о компиляции, развертывании и запуске win-приложений на C++ с помощью WINE под Linux.
## 1. Пакеты
Установка WINE:
```
sudo apt install wine-stable
```
https://www.winehq.org/
Установка компилятора:
```
sudo apt install mingw-w64
```
https://onstartup.ru/razrabotka/mingw-w64/
## 2. Visual Studio [OPTIONAL]
```
sudo apt install snap
sudo snap install --classic code
```
https://code.visualstudio.com/
## 3. Ключи компиляции и библиотеки
```
/usr/local/bin/x86_64-w64-mingw32-gcc -o app.exe main.c -mwindows
```
## 4. Запуск
```
wine app.exe
```
## 5. Кодировка
При запуске могут возникать проблемы с кодировкой и нехваткой шрифтов.  
Качаем конвертер `iconv` и пакет шрифтов  `ttf-mscorefonts-installer`  
```
sudo apt install iconv ttf-mscorefonts-installer
```
https://pro-self.ru/blog/pselfin/smena-kodirovki-faylov-v-ubuntu-tak-zhe-iconv-i-bolshie-fayli
### Источники
https://husl.ru/questions/941756  
https://www.securitylab.ru/analytics/521188.php  
https://www.winehq.org/
