CC	= gcc
CFLAGS	= -Wall
LDFLAGS	= -lcrypto -lb64 /usr/local/lib64/libcbor.a

CLIENT_OBJFILES	= crypto_functions.o edhoc_client.o edhoc_messages.o \
			  io_functions.o other_functions.o
SERVER_OBJFILES	= crypto_functions.o edhoc_server.o edhoc_messages.o \
			  io_functions.o other_functions.o
ALL_OBJFILES	= crypto_functions.o edhoc_client.o edhoc_server.o edhoc_messages.o \
			  io_functions.o other_functions.o
EDHOC_MSGS		= ./edhoc_client_INBOX/edhoc_sym_msg2_RAW.txt ./edhoc_server_INBOX/edhoc_sym_msg1_RAW.txt ./edhoc_server_INBOX/edhoc_sym_msg3_RAW.txt
EDHOC_KEYS		= ./edhoc_client_INBOX/server_PUBKEY.txt ./edhoc_server_INBOX/client_PUBKEY.txt
EDHOC_INP_PARAM	= ./input_parameters/client_PrivateKey.txt ./input_parameters/client_PUBKEY.txt ./input_parameters/server_PrivateKey.txt ./input_parameters/server_PUBKEY.txt

CLIENT_TARGET	=	edhoc-client
SERVER_TARGET	=	edhoc-server

all: $(CLIENT_TARGET) $(SERVER_TARGET)

$(CLIENT_TARGET) : $(CLIENT_OBJFILES)
	$(CC) $(CFLAGS) -o $(CLIENT_TARGET) $(CLIENT_OBJFILES) $(LDFLAGS)

$(SERVER_TARGET) : $(SERVER_OBJFILES)
	$(CC) $(CFLAGS) -o $(SERVER_TARGET) $(SERVER_OBJFILES) $(LDFLAGS)

clean:
	rm $(ALL_OBJFILES) $(CLIENT_TARGET) $(SERVER_TARGET) $(EDHOC_MSGS) $(EDHOC_KEYS) $(EDHOC_INP_PARAM)
