package DBTable;

import java.awt.Color;
import java.awt.EventQueue;
import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.ArrayList;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.JTextField;
import javax.swing.SwingConstants;
import javax.swing.border.CompoundBorder;
import javax.swing.border.EtchedBorder;
import javax.swing.border.LineBorder;

public class ContactMain {
	private static ContactDAO dao;
	
	private JFrame frame;
	private JTextField textIndex;
	private JTextField textName;
	private JTextField textPhone;
	private JTextField textEmail;
	private JTextArea textArea;
	
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					ContactMain window = new ContactMain();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	
	}
	
	public ContactMain() {
		dao = ContactDAOImple.getInstance();
		initialize();
	}
	
	private void initialize() {
		frame = new JFrame();
		frame.setBounds(100, 100, 510, 639);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //종료 버튼
		frame.getContentPane().setLayout(null);
		
		JLabel lblTitle = new JLabel("연락처 ver 0.5");
		lblTitle.setBorder(new LineBorder(new Color(119, 136, 153), 2, true));
		lblTitle.setFont(new Font("맑은 고딕", Font.BOLD, 21));
		lblTitle.setHorizontalAlignment(SwingConstants.CENTER);
		lblTitle.setBounds(12, 10, 470, 60);
		frame.getContentPane().add(lblTitle);
		
		JLabel lblIndex = new JLabel("인덱스");
		lblIndex.setHorizontalAlignment(SwingConstants.CENTER);
		lblIndex.setBorder(new CompoundBorder(
				new EtchedBorder(EtchedBorder.RAISED, new Color(192, 192, 192), new Color(192, 192, 192)), null));
		lblIndex.setFont(new Font("맑은 고딕", Font.PLAIN, 14));
		lblIndex.setBounds(12, 80, 160, 40);
		frame.getContentPane().add(lblIndex);
		
		JLabel lblName = new JLabel("이름");
		lblName.setHorizontalAlignment(SwingConstants.CENTER);
		lblName.setFont(new Font("맑은 고딕", Font.PLAIN, 14));
		lblName.setBorder(new CompoundBorder(
		new EtchedBorder(EtchedBorder.RAISED, new Color(192, 192, 192), new Color(192, 192, 192)), null));
		lblName.setBounds(12, 132, 160, 40);
		frame.getContentPane().add(lblName);
		
		JLabel lblPhone = new JLabel("전화번호");
		lblPhone.setHorizontalAlignment(SwingConstants.CENTER);
		lblPhone.setFont(new Font("맑은 고딕", Font.PLAIN, 14));
		lblPhone.setBorder(new CompoundBorder(
		new EtchedBorder(EtchedBorder.RAISED, new Color(192, 192, 192), new Color(192, 192, 192)), null));
		lblPhone.setBounds(12, 182, 160, 40);
		frame.getContentPane().add(lblPhone);
		
		JLabel lblEmail = new JLabel("이메일");
		lblEmail.setHorizontalAlignment(SwingConstants.CENTER);
		lblEmail.setFont(new Font("맑은 고딕", Font.PLAIN, 14));
		lblEmail.setBorder(new CompoundBorder(
		new EtchedBorder(EtchedBorder.RAISED, new Color(192, 192, 192), new Color(192, 192, 192)), null));
		lblEmail.setBounds(12, 232, 160, 40);
		frame.getContentPane().add(lblEmail);
		
		textIndex = new JTextField();
		textIndex.setBounds(197, 82, 285, 40);
		frame.getContentPane().add(textIndex);
		textIndex.setColumns(10);
		
		textName = new JTextField();
		textName.setColumns(10);
		textName.setBounds(197, 134, 285, 40);
		frame.getContentPane().add(textName);
		
		textPhone = new JTextField();
		textPhone.setColumns(10);
		textPhone.setBounds(197, 184, 285, 40);
		frame.getContentPane().add(textPhone);
		
		textEmail = new JTextField();
		textEmail.setColumns(10);
		textEmail.setBounds(197, 234, 285, 40);
		frame.getContentPane().add(textEmail);
		
		//등록 버튼
		JButton btnInsert = new JButton("등록");
		btnInsert.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				insert();		
			}
		});
		btnInsert.setFont(new Font("굴림", Font.BOLD, 14));
		btnInsert.setBounds(12, 282, 85, 40);
		frame.getContentPane().add(btnInsert);
		
		//전체검색 버튼
		JButton btnSelect = new JButton("전체검색");
		btnSelect.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				selectAll();
			}
		});
		btnSelect.setFont(new Font("굴림", Font.BOLD, 14));
		btnSelect.setBounds(98, 282, 97, 40);
		frame.getContentPane().add(btnSelect);
		
		//상세검색 버튼
		JButton btnIndexSelect = new JButton("상세검색");
		btnIndexSelect.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				select();
			}
		});
		btnIndexSelect.setFont(new Font("굴림", Font.BOLD, 14));
		btnIndexSelect.setBounds(197, 282, 118, 40);
		frame.getContentPane().add(btnIndexSelect);
		
		//수정 버튼
		JButton btnUpdate = new JButton("수정");
		btnUpdate.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				update();
			}
		});
		btnUpdate.setFont(new Font("굴림", Font.BOLD, 14));
		btnUpdate.setBounds(317, 282, 79, 40);
		frame.getContentPane().add(btnUpdate);
		
		//삭제 버튼
		JButton btnDelete = new JButton("삭제");
		btnDelete.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				delete();
			}
		});
		btnDelete.setFont(new Font("굴림", Font.BOLD, 14));
		btnDelete.setBounds(403, 282, 79, 40);
		frame.getContentPane().add(btnDelete);
		
		JScrollPane scrollPane = new JScrollPane();
		
		scrollPane.setBounds(12, 332, 470, 259);
		frame.getContentPane().add(scrollPane);
		
		textArea = new JTextArea();
		scrollPane.setViewportView(textArea);
	}

	
	private void insert() {
		String name = textName.getText();
		String phone = textPhone.getText();
		String email = textEmail.getText();
		
		ContactVO contact = new ContactVO(0,name,phone,email);
		
		int result = dao.insert(contact);
		
		if(result > 0) {
			System.out.println("연락처 등록 성공");
			clearTextFields();
		}else {
			System.out.println("연락처 등록 실패");
		}
		
		textArea.setText(contact.toString());
	}

	private void selectAll() {
		ArrayList<ContactVO> list = dao.select();
		StringBuffer buffer = new StringBuffer();
		
		for(int i = 0; i < list.size(); i++) {
			buffer.append(list.get(i).toString()).append("\n");
		}
		
		textArea.setText(buffer.toString());
	}
	
	private void select() {
		try {
			int index = Integer.parseInt(textIndex.getText());
			ContactVO list = dao.select(index);
			textName.setText(list.getName());
			textPhone.setText(list.getPhone());
			textEmail.setText(list.getEmail());
		} catch (NumberFormatException e) {
			textArea.setText("숫자를 입력하세요.");
		} catch(NullPointerException e) {
			textArea.setText("해당 인덱스가 없습니다.");
		}
	}
	
	private void update() {
		try {
			int index = Integer.parseInt(textIndex.getText());
			String name = textName.getText();
			String phone = textPhone.getText();
			String email = textEmail.getText();
			ContactVO contact = new ContactVO(index, name, phone, email);
			
			int result = dao.update(contact);
			
			if(result == 1) {
				textArea.setText(index + "연락처 수정 성공");
			} else {
				textArea.setText(index + "연락처 수정 실패");
			}
			
		} catch (NumberFormatException e) {
			textArea.setText("숫자를 입력하세요.");
		}
	}
	
	private void delete() {
		try {
			int index = Integer.parseInt(textIndex.getText());
			int result = dao.delete(index);
			
			if(result > 0) {
				textArea.setText(index + "연락처 삭제 성공");
				clearTextFields();
			} else {
				textArea.setText(index + "연락처 삭제 실패");
			}
		} catch (NumberFormatException e) {
			textArea.setText("숫자를 입력하세요.");
		}
	}
	
	private void clearTextFields() {
		textIndex.setText("");
		textName.setText("");
		textPhone.setText("");
		textEmail.setText("");
	}
}
