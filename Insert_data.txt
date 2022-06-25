Insertion of data into table :


import java.sql.*; 
import  java.util.*;
public class insert_data
{
public static void main(String args[]) {
	try 
{
Class.forName("com.mysql.jdbc.Driver");
Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/MOVIES","root","");
Statement st=con.createStatement();
Scanner sc = new Scanner(System.in);
System.out.println("Enter the movie details\n");
String name1= sc.nextLine();
String actor2= sc.nextLine();
String actress3= sc.nextLine();
String director4= sc.nextLine(); 
int year_of_release5=sc.nextInt();
String qry = "INSERT INTO MOVIES_data(name,actor,actress,director,year_of_release) VALUES('"+name1+"','"+actor2+"','"+actress3+"','"+director4+"','"+year_of_release5+"')";
st.executeUpdate(qry);
con.close();
sc.close();
}
catch(Exception e)
{
System.out.println(e);
}
System.out.println("Row Inserted");
}
}