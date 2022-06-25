import java.sql.*;
Create table MOVIES_data:


public class create_movies_table
{
public static void main(String args[])
{
try
{
//com.mysql.cj.jdbc.Driver
Class.forName("com.mysql.cj.jdbc.Driver");
Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/MOVIES","root","");
Statement st=con.createStatement();
st.executeUpdate("CREATE TABLE MOVIES_data (NAME VARCHAR(30),ACTOR VARCHAR(20),ACTRESS VARCHAR(20),DIRECTOR VARCHAR(20),YEAR_OF_RELEASE int)");
System.out.println("Table created");
con.close();
}
catch(Exception e)
{
System.out.println(e);
}
}
}