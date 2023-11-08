# Makefile Fooline
Compiling multiple files with makefiles

## How to experiment
```src``` 폴더가 있고, 이 폴더를 복사해서 ```opt-1```, ```opt-2```, ... 를 만들면서 실험한다.

## opt-1 One line
```
cp -r src opt-1
cd src
gcc -Wall main.c foo.c
```
```gcc -Wall foo.c main.c``` 도 된다.

### gcc -Wall option flag
gcc -Wall enables all compiler`s warning messages. This option should always be used, in order to generate better code.

## opt-2 Linking
```
gcc -Wall -c main.c
gcc -Wall -c foo.c
gcc -Wall -o footest foo.o main.o
```
```gcc -Wall -o footest2 main.o foo.o``` 도 된다.

## opt-3 Makefile
```
CC	= gcc
CFLAGS	= -Wall
LDFLAGS	=
OBJFILES = foo.o main.o
TARGET = footest

all: $(TARGET)

$(TARGET): $(OBJFILES)
	$(CC) $(CFLAGS) -o $(TARGET) $(OBJFILES) $(LDFLAGS)

clean:
	rm -f $(OBJFILES) $(TARGET) *~
```

### VS Code Makefile Tools

### *~
rm *~ just removes file with names ending with a tilde (~).