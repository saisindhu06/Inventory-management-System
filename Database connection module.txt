import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class ConnectionFactory {

    Connection conn = null;
    Statement statement = null;
    ResultSet resultSet = null;

    public ConnectionFactory(){
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/inventory", "root", "root");
            statement = conn.createStatement();
        } catch (Exception e) {
        }
    }

    public Connection getConn() {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/inventory", "root", "root");
            System.out.println("Connected successfully.");
        } catch (Exception e) {
        }
        return conn;
    }

    //Login verification method
    public boolean checkLogin(String username, String password, String userType){
        String query = "SELECT * FROM users WHERE username='"
                + username
                + "' AND password='"
                + password
                + "' AND usertype='"
                + userType
                + "' LIMIT 1";

        try {
            resultSet = statement.executeQuery(query);
            if(resultSet.next()) return true;
        } catch (Exception ex) {
        }
        return false;
    }

}
