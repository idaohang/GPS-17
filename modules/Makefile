include ../Makefile.inc

SRC=mmc/mmc.c  \
	mmc/pff.c  \
	uart/uart.c \
	mmc/usci_spi.c 
	#mmc/usci_serial.c  \
	
ROOT_DIR =..

OBJS = ${SRCS:.c=.o}

#Primeiro alvo
all: $(OBJ)
	mv *.o ../obj
	
#Gerando objetos
.c.o:
	$(CC) -Wall -c $(SRC) $(CC_FLAGS)

#Gerando arquivo assembly (não passa por este alvo)
assembly: $(SRC)
	$(CC) $(SRC) -Wl,-Map=_$(TARGET).map -o $(TARGET).s $(FLAGS) -S
		
#Limpando os objetos
clean:
	clear
	rm -rf *.o *.elf *.hex *.map *.s *.list

