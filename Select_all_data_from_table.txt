Select all rows from the table MOVIES_data:


import java.sql.*; 
public class select_movies
{
public static void main(String args[]) {
	try 
{
Class.forName("com.mysql.jdbc.Driver");
Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/MOVIES","root","");
Statement st=con.createStatement();
ResultSet rs = st.executeQuery("select * from MOVIES_data");
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