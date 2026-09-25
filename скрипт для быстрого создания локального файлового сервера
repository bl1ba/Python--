import http.server
import socketserver
import socket

PORT = 8000

def get_ip():
    s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
    try:
        s.connect(("8.8.8.8", 80))
        ip = s.getsockname()[0]
    except:
        ip = "127.0.0.1"
    finally:
        s.close()
    return ip

Handler = http.server.SimpleHTTPRequestHandler
with socketserver.TCPServer(("", PORT), Handler) as httpd:
    print(f"Сервер запущен: http://{get_ip()}:{PORT}")
    print("Файлы в текущей папке доступны для скачивания.")
    httpd.serve_forever()
