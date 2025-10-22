import java.io.*;
import java.net.*;

public class ChatClient {
    public static void main(String[] args) {
        String hostname = "localhost"; // Server IP or hostname
        int port = 1234;

        try (Socket socket = new Socket(hostname, port)) {
            System.out.println("Connected to the chat server");

            new Thread(new ReadMessage(socket)).start();
            new Thread(new WriteMessage(socket)).start();

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

// Thread to read messages from server
class ReadMessage implements Runnable {
    private BufferedReader reader;

    public ReadMessage(Socket socket) throws IOException {
        reader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
    }

    @Override
    public void run() {
        String message;
        try {
            while ((message = reader.readLine()) != null) {
                System.out.println(message);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

// Thread to send messages to server
class WriteMessage implements Runnable {
    private PrintWriter writer;
    private BufferedReader consoleReader;

    public WriteMessage(Socket socket) throws IOException {
        writer = new PrintWriter(socket.getOutputStream(), true);
        consoleReader = new BufferedReader(new InputStreamReader(System.in));
    }

    @Override
    public void run() {
        String message;
        try {
            while ((message = consoleReader.readLine()) != null) {
                writer.println(message);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
