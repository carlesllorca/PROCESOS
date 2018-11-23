# Desarrollar una barra de tareas

## Swing

En este ejerciocio mediante ProcessBuilder y Swing vamos a crear una barra de tareas que ejecuten mis 4 aplicaciones preferidas. En este caso he elegido eclipse, gimp, android studio y visual studio.

Para este ejercicio he tenido que instalar el WindowsBuilder para java, esta herramienta nos ayuda gráficamente a poner botones. Jo a los botones les he puesto unas imagen en las que estan modificadas para que se adapten al tamaño del botón.

```java
ImageIcon icon = new ImageIcon("imagen\\eclipse.png");
		Image img = icon.getImage(); //convertimos icon en una imagen
		Image otraimg = img.getScaledInstance(57,57,java.awt.Image.SCALE_SMOOTH); //creamos una imagen nueva dándole las dimensiones que queramos a la antigua
		ImageIcon otroicon = new ImageIcon(otraimg);
		
		JButton btnEclipse = new JButton(otroicon);
```


#### Cuando inicias cada boton cuando le das iniciará el programa predeterminado de ese ordenador. Para canviar el link tienes que canviar el link por el link donde este la aplicación.

```java
btnEclipse.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				try {
					ProcessBuilder pb=new ProcessBuilder("C:\\Users\\vesprada\\eclipse\\java-photon\\eclipse\\eclipse.exe");
					pb.start();
				} catch (IOException e1) {
					// TODO Auto-generated catch block
					e1.printStackTrace();
				}
			}
		});
```
#### El código comleto:
```java
import java.awt.BorderLayout;
import java.awt.EventQueue;
import java.awt.Image;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JButton;
import javax.swing.ImageIcon;
import java.awt.event.ActionListener;
import java.io.IOException;
import java.awt.event.ActionEvent;

public class BarraTareas extends JFrame {

	private JPanel contentPane;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					BarraTareas frame = new BarraTareas();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public BarraTareas() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 279, 95);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		ImageIcon icn= new ImageIcon("imagen\\eclipse.png");
		
		ImageIcon icon = new ImageIcon("imagen\\eclipse.png");
		Image img = icon.getImage(); //convertimos icon en una imagen
		Image otraimg = img.getScaledInstance(57,57,java.awt.Image.SCALE_SMOOTH); //creamos una imagen nueva dándole las dimensiones que queramos a la antigua
		ImageIcon otroicon = new ImageIcon(otraimg);
		
		JButton btnEclipse = new JButton(otroicon);
		btnEclipse.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				try {
					ProcessBuilder pb=new ProcessBuilder("C:\\Users\\vesprada\\eclipse\\java-photon\\eclipse\\eclipse.exe");
					pb.start();
				} catch (IOException e1) {
					// TODO Auto-generated catch block
					e1.printStackTrace();
				}
			}
		});
		btnEclipse.setBounds(0, 0, 57, 57);
		contentPane.add(btnEclipse);
		
		
		ImageIcon icon2 = new ImageIcon("imagen\\gimp.png");
		Image img2 = icon2.getImage(); //convertimos icon en una imagen
		Image otraimg2 = img2.getScaledInstance(57,57,java.awt.Image.SCALE_SMOOTH); //creamos una imagen nueva dándole las dimensiones que queramos a la antigua
		ImageIcon otroicon2 = new ImageIcon(otraimg2);
		
		JButton btnEdge = new JButton(otroicon2);
		btnEdge.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				ProcessBuilder pb=new ProcessBuilder("C:\\Program Files\\GIMP 2\\bin\\gimp-2.10.exe");
				try {
					pb.start();
				} catch (IOException e1) {
					// TODO Auto-generated catch block
					e1.printStackTrace();
				}
			}
		});
		btnEdge.setBounds(70, 0, 57, 57);
		contentPane.add(btnEdge);
		
		ImageIcon icon3 = new ImageIcon("imagen\\android.png");
		Image img3 = icon3.getImage(); //convertimos icon en una imagen
		Image otraimg3 = img3.getScaledInstance(57,57,java.awt.Image.SCALE_SMOOTH); //creamos una imagen nueva dándole las dimensiones que queramos a la antigua
		ImageIcon otroicon3 = new ImageIcon(otraimg3);
		
		JButton btnAndroid = new JButton(otroicon3);
		btnAndroid.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				ProcessBuilder pb=new ProcessBuilder("C:\\Program Files\\Android\\Android Studio\\bin\\studio64.exe");
				try {
					pb.start();
				} catch (IOException e1) {
					// TODO Auto-generated catch block
					e1.printStackTrace();
				}
			}
		});
		btnAndroid.setBounds(137, 0, 57, 57);
		contentPane.add(btnAndroid);
		
		ImageIcon icon4 = new ImageIcon("imagen\\visual.png");
		Image img4 = icon4.getImage(); //convertimos icon en una imagen
		Image otraimg4 = img4.getScaledInstance(57,57,java.awt.Image.SCALE_SMOOTH); //creamos una imagen nueva dándole las dimensiones que queramos a la antigua
		ImageIcon otroicon4 = new ImageIcon(otraimg4);
		
		JButton btnVisualBasic = new JButton(otroicon4);
		btnVisualBasic.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				ProcessBuilder pb=new ProcessBuilder("C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Enterprise\\Common7\\IDE\\devenv.exe");
				try {
					pb.start();
				} catch (IOException e1) {
					// TODO Auto-generated catch block
					e1.printStackTrace();
				}
			}
		});
		btnVisualBasic.setBounds(207, 0, 57, 57);
		contentPane.add(btnVisualBasic);
		
		
		
	}
}


```
