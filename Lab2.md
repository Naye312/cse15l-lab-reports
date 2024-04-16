This is the code block Chat Server
```
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;
import java.net.URI;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.List;

class StringHandler implements URLHandler {
  List<String> lines;
  String path;
  StringHandler(String path) throws IOException {
    this.path = path;
    this.lines = Files.readAllLines(Paths.get(path));
  }
  public String handleRequest(URI url) throws IOException {
    String query = url.getQuery();
    if(url.getPath().equals("/add-message")) {
      if(query.startsWith("s=")) {
        String orig = query.substring(query.indexOf("="), query.length());
        if(orig.indexOf("&user=") != -1) {
          String user = orig.substring(orig.lastIndexOf("=") + 1);
          String message = orig.substring(1, orig.indexOf("&")); 
          orig = user + ": " + message; 
        } 
        else {
          return "/add-message requires a username parameter user\n";
        }
        this.lines.add(orig);
        this.log("/add-message?" + query);
        return String.format("New message from user: \n", orig.substring(orig.lastIndexOf("=") + 1));
      }
      else {
        return "/add-message requires a query parameter s\n";
      }
    }
    else {
      return String.join("\n", lines) + "\n";
    }
  }
  void log(String s) {
    try(FileWriter fw = new FileWriter("session.log", true);
        BufferedWriter bw = new BufferedWriter(fw);
        PrintWriter out = new PrintWriter(bw)) {
        out.println(s);
    } catch (IOException e) {
        //exception handling left as an exercise for the reader
    }
  }
}

class StringServer {
  public static void main(String[] args) throws IOException {
    if(args.length == 0){
      System.out.println("Missing both port number and file path! For the first argument (port number), try any number between 1024 to 49151. For the second argument (file path), give a path to a text file.");
      return;
    }
    if(args.length == 1){
      System.out.println("Missing port number or file path! For the first argument (port number), try any number between 1024 to 49151. For the second argument (file path), give a path to a text file.");
      return;
    }

    int port = Integer.parseInt(args[0]);

    Server.start(port, new StringHandler(args[1]));
  }
}
```
