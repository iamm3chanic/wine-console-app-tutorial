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
## 6. Создание Makefile
Makefile полезен для создания больших проектов и может выглядеть так:
```
CC = /usr/local/bin/x86_64-w64-mingw32-gcc
CFLAGS = -W -Wall -O0 -O1 -O2 -g
LIBS = -mwindows

app.exe: main.o file1.o file2.o Makefile
	$(CC) $(CFLAGS) -o app.exe main.o file1.o file2.o $(LIBS)
main.o: main.cpp include1.h include2.h Makefile
	$(CC) $(CFLAGS) -c main.cpp $(LIBS)
file1.o: file1.cpp include1.h Makefile
	$(CC) $(CFLAGS) -c file1.cpp $(LIBS)
file2.o: file2.cpp include2.h Makefile
	$(CC) $(CFLAGS) -c file2.cpp $(LIBS)
clean:
	rm app.exe *.o 

```
### Источники
https://husl.ru/questions/941756  
https://www.securitylab.ru/analytics/521188.php  
https://www.winehq.org/
