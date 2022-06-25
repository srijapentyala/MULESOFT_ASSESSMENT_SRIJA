Creation of database MOVIES:


import java.sql.*;
public class create_table
{
public static void main(String args[])
{
try
{
Class.forName("com.mysql.cj.jdbc.Driver");
Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/","root","");
Statement st=con.createStatement();
String sql="CREATE DATABASE MOVIES";
st.executeUpdate(sql);
System.out.println("Database created.");
con.close();
}
catch(Exception e)
{
System.out.println(e);
}
}
}