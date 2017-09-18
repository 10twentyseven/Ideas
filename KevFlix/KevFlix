package KevFlix;

import java.awt.Desktop;
import java.io.File;
import java.io.IOException;
import java.util.Scanner;

public class KevFlix {
	
	public static String checkDirectory(){
		if (new File("D:\\Movies").exists()) {
			return "D:\\Movies";
		} else if (new File("E:\\Movies").exists()){
			return "E:\\Movies";
		} else if (new File("F:\\Movies").exists()){
			return "F:\\Movies";
		} else if (new File("G:\\Movies").exists()){
			return "G:\\Movies";
		} else {
			return "No Dice";
		}
	}
	
	public static String[] movieList(){
		File movieDirectory = new File(checkDirectory());
		File[] movies = movieDirectory.listFiles();
		String[] titleList = new String[movies.length]; 
		for (int i = 0; i < movies.length; i++){
			String title = movies[i].toString();
			String shortTitle = title.substring(10, title.length()-4);
			titleList[i] = shortTitle;
			
		}
		return titleList;
	}
	
	public static String[] session(){
		Scanner s = new Scanner(System.in);
		String[] movieList = movieList();
		int n = (int)(Math.random() * movieList.length);
		String movie = movieList[n];
		String[] choice = new String[2];
		
		System.out.println("Hello! Let's find you something to watch!");
		System.out.println(movie);
		System.out.println("Is this ok?");
		if (s.next().toLowerCase().equals("yes")){
			choice[0] = "yes";
			choice[1] = movie;
		} else {
			choice[0] = "no";
			choice[1] = "";
		}
		return choice;
		
	}
	
	public static void main(String[] args) throws IOException{
		String[] session = session();
		String yesNo = session[0];
		String movie = session[1];
		Desktop d = Desktop.getDesktop();
		while(!yesNo.equals("yes")){
			System.out.println("well gosh");
			session = session();
			yesNo = session[0];
			movie = session[1];
		}
		System.out.println("Looks like you're watching " + movie);
		File finalChoice = new File(checkDirectory() + "\\" + movie + ".m4v");
		d.open(finalChoice);
	}
}
