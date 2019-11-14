# Jogo
Projeto 2Eminfoimport java.awt.Canvas;

import java.awt.Dimension;
import java.awt.Graphics;
import java.awt.image.BufferStrategy;

import javax.swing.JFrame

public class game extends Canvas implements Runnable,tenerkeyLis{

	public Note[] nodeSnake = new Node[10];
	
	public boolean left, right,up,down;
	
	public game() {
		this.setpreferredSize(new Dimension(480,480));
		for(int = 0; i < nodeSnake.length;  i++) {
			nodeSnake[i] = new Node(0,06t);
		}	
		this.addKeyListener(this)
	}
	public void tick() {
	if(rigth) {
		nodeSnake[0].x++;
	}else if (up) {
		nodeSnake[0].y--;
	}else if (down) {
		nodeSnake[0].y++;
	}else if(left) {
		nodeSnake[0].x--;
	}
	}
	
	
	public voide render() {
		BufferStrategy bs = this.getBufferStrategy();
		if(bs == null) {
			this.createBufferStrategy(3);
			return;
			
		}
		Graphics g = bs.getDrawGraphics();
		g.setcolor(color.clack);
		g.fillRect(0,0,480,480);
		for(int = 0; i < nodeSnake.length; i++) {
			g.setColor(color.blue);
			g.fillRect(nodeSnake[i.x], nodeSnake[i].y,10,10);
		}
		
		g.dispose();
		bs.show();
	}
	public static void main(String args[]) {
		Game game= new Game();
		JFrame = new Jframe("Jogo da Cobrinha");
		frame.add(game);
		frame.setResizable(false);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		frame.pack();
		frame.setLocationRelativeTo(null);
		frame.setVisible(true);
		new thread(game). start();
		
	}
	
	@Override
	public voide run() {
		
		while(true) {
			tick()
			render();
			Thread.sleep(1000/60);
			
		}catch (InterruptedException e) {
			
			e.printStackTrace();
		}
		
	}
	
}
@Override
public void keyPressed(keyEvent e) {
if(e.getKeyCode()== keyEvent.VK_RIGHT) {
	right = true;
	left = false;
	up=false;
	down=false;
}else if(e.getKeyCode()== keyEvent.VK_LEFT) {
	left=true;
	up = false;
	down= false;
	right = false;
}else if(e.getKeyCode()== keyEvent.VK_UP) {
	up= true;
	down = false;
	right= false;
	left = false;
}else if(e.getKeyCode()== keyEvent.VK_DOWN) {
	down = true;
	right= false;
	left = false;
	up = false;
}
	
}

@Override
public void keyReleased(keyEvent arg0) {
	//TODO Auto-generated method stup
}

@Override
public voide keyTyped(KeyEvent arg0) {
	//TODO Auto-generated method stup
	
}




