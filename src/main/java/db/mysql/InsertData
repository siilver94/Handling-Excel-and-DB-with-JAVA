import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class InsertData {

	public static void main(String[] args) {
		// test case로 kes_table 테이블에는 ID/타이틀/내용/만들시일 칼럼이 있습니다.
		insert( 5,"AllenSQL", "Allen SQL is...", "2019-09-10 01:36:33",3);
	}

	public static void insert(int id, String title, String description, String created,int author_id) {
		Connection conn = null;
		PreparedStatement pstmt = null;

		try {
			// 1. 드라이버 로딩
			Class.forName("com.mysql.jdbc.Driver");

			// 2. 연결하기
		//	String url = "jdbc:mysql://localhost/kes_table";
			String url = "jdbc:mysql://localhost:3306/kes_table?useSSL=false";
			conn = DriverManager.getConnection(url, "root", "sd203505");

			// 3. SQL 쿼리 준비
			// 추가하려는 데이터의 값은 전달된 인자를 통해 동적으로 할당되는 값이다.
			// 즉 어떤 값이 전달될지 모르므로 Select 할 때와 달리
			// stmt = conn.createStatement(); 를 작성하지 않고
			// pstmt = conn.prepareStatement(sql); 로 작성하여 데이터를 추가할 것임을 알립니다.
			// 물론 sql 쿼리 내에서 + 연산자로 한 줄로 작성할 수 있지만 가독성이 너무 떨어지게 되므로
			// 이 방법을 권합니다.
			String sql = "INSERT INTO kes_table VALUES (?,?,?,?,?)";
			pstmt = conn.prepareStatement(sql);

			// 4. 데이터 binding
			pstmt.setInt(1, id);
			pstmt.setString(2, title);
			pstmt.setString(3, description);
			pstmt.setString(4, created);
			pstmt.setInt(5, author_id);
			//pstmt.setString(6, death);

			// 5. 쿼리 실행 및 결과 처리
			// SELECT와 달리 INSERT는 반환되는 데이터들이 없으므로
			// ResultSet 객체가 필요 없고, 바로 pstmt.executeUpdate()메서드를 호출하면 됩니다.
			// INSERT, UPDATE, DELETE 쿼리는 이와 같이 메서드를 호출하며
			// SELECT에서는 stmt.executeQuery(sql); 메서드를 사용했었습니다.
			// @return int - 몇 개의 row가 영향을 미쳤는지를 반환
			int count = pstmt.executeUpdate();
			if (count == 0) {
				System.out.println("데이터 입력 실패");
			} else {
				System.out.println("데이터 입력 성공");
			}
		} catch (ClassNotFoundException e) {
			System.out.println("드라이버 로딩 실패");
		} catch (SQLException e) {
			System.out.println("에러 " + e);
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
