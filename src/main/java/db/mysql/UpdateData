import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class UpdateData {

	public static void main(String[] args) {

		Connection conn = null;
		PreparedStatement pstmt = null;

		try {

			Class.forName("com.mysql.jdbc.Driver");

			String url = "jdbc:mysql://localhost:3306/kes_table?useSSL=false";
			conn = DriverManager.getConnection(url, "id", "pw");  //id 와 pw 입력

			 String sql = "update table_test set Name=?,Age=?,Job=?,Hobby=? where id=3";
			//String sql = "INSERT INTO table_test VALUES (?,?,?,?,?)";

			pstmt = conn.prepareStatement(sql);

			//pstmt.setInt(1, 3);
			pstmt.setString(1, "oppa");
			pstmt.setString(2, "33");
			pstmt.setString(3, "toy");
			pstmt.setString(4, "work");

			int count = pstmt.executeUpdate();
			if (count == 0) {
				System.out.println("데이터 입력 실패");
			} else {
				System.out.println("데이터 입력 성공");
			}

		} catch (ClassNotFoundException e) {
			System.out.println("드라이버 로딩 실패");
		} catch (SQLException e1) {
			System.out.println("에러 " + e1);
		} finally {
			try {
				if (conn != null && !conn.isClosed()) {
					conn.close();
				}
				if (pstmt != null && !pstmt.isClosed()) {
					pstmt.close();
				}
			} catch (SQLException e) {
				e.printStackTrace();
			}
		}
	}
}
