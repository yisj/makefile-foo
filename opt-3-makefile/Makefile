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

