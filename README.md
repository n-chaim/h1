import java.io.FileNotFoundException;
import java.util.Scanner;
import java.io.File;
import java.io.PrintWriter;
import java.util.ArrayList;

public class H1_43 {
  public static void main(String[] pArgs) {
    new H1_43().run(); 
  }
  public H1_43(){ 
  }
  private void run(){
  }
  
  private String getInput(){
    Scanner userInput = new Scanner(System.in);
    System.out.print("Enter file name");
    String fName = userInput.nextLine();
    return fName;
    userInput.close();    
  }
  
  private ArrayList<String> readFile(String pFileName,ArrayList<String> pList)throws FileNotFoundException{
    Scanner in = new Scanner(new File(pFileName));
    while (in.hasNext() == true){  
      pList.add(in.nextLine());
    }
    in.close();
    return pList; 
  }
  
  private void writeFile(String pFileName, ArrayList<String> pList) throws FileNotFoundException{
    PrintWriter out = new PrintWriter(new File(pFileName));
    int lineNum = 1;
    for (int i = 0; i <= pList.size()-1; i++){
      out.printf("[%-03d] %s",lineNum, pList.get(i));
    }
    out.close();
  }
  
  
  
}
