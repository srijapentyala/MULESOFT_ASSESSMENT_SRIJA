Select a single row based on actor's name:


import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement; 
public class select_actor_movie
{
public static void main(String args[]) {
	try 
{
Class.forName("com.mysql.jdbc.Driver");
Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/MOVIES","root","");
Statement st=con.createStatement();
ResultSet rs = st.executeQuery("select * from MOVIES_data WHERE actor='Yash'");
System.out.println("The Movie Details are \n");
while(rs.next())
{
System.out.println(rs.getString(1)+"\t"+rs.getString(2)+"\t"+ rs.getString(3)+"\t"+rs.getString(4) +"\t" +rs.getInt(5));
}
con.close();
}
catch(Exception e)
{
System.out.println(e);
}
}
}