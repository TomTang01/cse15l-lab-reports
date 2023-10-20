Code for `StringServer.java` :
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a counter and a string that will be 
    // manipulated by various requests.
    
    String str = "";
    int num = 1;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("%s", str);
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    str += num + ". " + parameters[1] + "\n";
                    return "String extended!";
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```
Screenshots of using `/add-message` :
![Screenshot](https://github.com/TomTang01/cse15l-lab-reports/blob/main/sceenshot1.png)

