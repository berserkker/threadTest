# threadTest
线程
package threadTest;

import java.security.Principal;

public class FirstThread extends Thread{
private int i;
public void run(){
	for(;i<100;i++){
		System.out.println(getName()+" "+i);
	}
}
public static void main(String args[]){
	FirstThread fr=new FirstThread();
	for(int i=0;i<100;i++){
		System.out.println(Thread.currentThread().getName()+" "+i);
		if(i==20){
			fr.start();
			System.out.println(fr.isAlive());
		}
		if(i>20&&!fr.isAlive()){
			fr.start();
		}
	}
}
}
