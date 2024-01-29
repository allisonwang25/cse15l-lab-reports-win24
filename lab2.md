# Lab Report 2: Servers and SSH Keys
## Part1: Chat Server
Code for Chat Server:
```java
import java.util.ArrayList;
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> allMessages = new ArrayList<>();
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            String result = "";
            for(String line : allMessages){
                result += line + "\n";
            }
            return result;
        }else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("&");
                String messageDetails = parameters[0];
                String userDetails = parameters[1];
                String[] messageSplit = messageDetails.split("=");
                String[] userSplit = userDetails.split("=");
                if (messageSplit[0].equals("s")) {
                    String message = messageSplit[1];
                    if(userSplit[0].equals("user")){
                        String username = userSplit[1];
                        allMessages.add(String.format("%s: %s", username, message));
                        String result = "";
                        for(String line : allMessages){
                            result += line + "\n";
                        }
                        return result;
                    }
                }
            }
            return "404 Not Found!";
        }
    }
}

class ChatServer {
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
![Screenshot of Adding First Message](/addMessage/addMessage1.png)
* The handleRequest method in class Handler is called.
* The argument taken into this method is the url `http://localhost:4000/add-message?s=YAY&user=yao`. The value of `ArrayList<String> allMessages` is null at the method is called.
* This request changes the value of `ArrayList<String> allMessages` from null to `["yao: YAY"]` (one value is added to the array list). 
![Screenshot of Adding Second Message](/addMessage/addMessage2.png)
* The same method, handleRequest method in class Handler, is called.
* The argument taken into this method is the url `http://localhost:4000/add-message?s=WE DID IT&user=allison`. The value of `ArrayList<String> allMessages` has value `["yao: YAY"]`  at the method is called.
* This request changes the value of `ArrayList<String> allMessages` from `["yao: YAY"]` to `["yao: YAY", "allison: WE DID IT]` (one value is added to the array list).

## Part 2: SSH
* ![Absolute Path of Private Key Screenshot](/absolutePath/privateKey.png)
  * The absolute path is `/Users/allisonwang/.ssh/id_rsa`
* ![Absolute Path of Public Key Screenshot](/absolutePath/publicKey.png)
  * The absolute path is `/home/linux/ieng6/oce/9f/alw036/.ssh/authorized_keys`
* ![No Password Login Attempt Screenshot](/absolutePath/noPasswordLogin.png)

## Part 3: What Have I Learned
In week 2 lab, I learned about how URLs are handled in the backend and that once a server is open, it can be opened from another computer as long as the link (with information about the port it's opened on and such) is given. 
