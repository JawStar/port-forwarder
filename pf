import socket
import threading

# Local address and port to listen on
LOCAL_HOST = '0.0.0.0'  # Listen on all available network interfaces
LOCAL_PORT = 8080

# Remote destination address and port to forward to
REMOTE_HOST = 'example.com'  # Remote server address
REMOTE_PORT = 80  # Remote server port

def forward_data(client_socket, remote_socket):
    while True:
        # Receive data from the client
        client_data = client_socket.recv(4096)
        if len(client_data) == 0:
            break  # No more data, close the connection
        remote_socket.send(client_data)  # Forward data to remote server

def handle_client(client_socket):
    try:
        # Create a connection to the remote server
        remote_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        remote_socket.connect((REMOTE_HOST, REMOTE_PORT))

        # Start threads to handle data forwarding in both directions
        threading.Thread(target=forward_data, args=(client_socket, remote_socket)).start()
        threading.Thread(target=forward_data, args=(remote_socket, client_socket)).start()

    except Exception as e:
        print(f"Error handling client: {e}")
        client_socket.close()

def start_server():
    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    server_socket.bind((LOCAL_HOST, LOCAL_PORT))
    server_socket.listen(5)
    print(f"Listening on {LOCAL_HOST}:{LOCAL_PORT}...")

    while True:
        client_socket, client_address = server_socket.accept()
        print(f"Connection received from {client_address}")
        threading.Thread(target=handle_client, args=(client_socket,)).start()

if __name__ == '__main__':
    start_server()
