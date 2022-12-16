```java
public class MyThread extends Thread{

	@Override  
	public void run() {  //When we start an instance of this thread, the code inside run() function executes. run() is a function of Thread class.
		
		for(int i =10;i>0;i--) {
			System.out.println("Thread #1 : "+i);
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				e.printStackTrace();
			}
		}
		System.out.println("Thread #1 is finished :)");
	}
}


public class MyRunnable implements Runnable{

	@Override
	public void run() {
		
		for(int i =0;i<10;i++) {
			System.out.println("Thread #2 : "+i);
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				e.printStackTrace();
			}
		}
		System.out.println("Thread #2 is finished :)");
	}
}


public class Main{
	  
    public static void main(String[] args) throws InterruptedException{  

    	//1st Way of creating a Thread :: Create a subclass of Thread class
    	MyThread thread1 = new MyThread();
    	  
    	//or 
    	
    	//2nd Way of creating a Thread :: Implement Runnable interface and pass instance as an argument to Thread() 
    	MyRunnable runnable1 = new MyRunnable();
    	Thread thread2 = new Thread(runnable1);
    	
    	
//    	thread1.setDaemon(true);
//    	thread2.setDaemon(true);
    	
    	//Normally, when thread1 & thread2 are not daemon threads -- in that case, even if an exception occurs in the 'main' thread, the other two threads will continue to run (& complete) without any interruption. But, if we make the threads - thread1 & thread2 - into daemon threads - then in that case there remains only one primary/user thread i.e 'main' thread. An then, if any exception occurs in our one and only user/primary thread i.e main thread, then the compiler does not care to complete the execution of daemon threads (threads1 & thread2) and the whole program immediately stops. 
    	
    	thread1.start();
    	thread1.join(); //this line of code makes the 'main' thread wait/pause untill the thread1 completes its excecution. And once thread1 completes its execution, the main thread continues again -- i.e starts threads2.
//    	thread1.join(3000); //this line of code makes the 'main' thread wait/pause for 3000 milliseconds (after starting of thread1) before continuing its execution -- i.e starting threads2. 
    	thread2.start();
    	
    	//An important point to note here is that even if there occurs an exception during execution of one of the threads, the other thread/threads continue to run without any problem.
    	
//    	System.out.println(1/0);  //This will cause an exception in 'main' thread but the threads 'thread1' and 'thread2' will continue to run without any interruption. But, if threads - thread1 & thread2 - are made into daemon threads,  then in that case there remains only one primary/user thread i.e 'main' thread. Then, as soon as the exception occurs in the main thread (1/0), the compiler does not care to complete the execution of daemon threads (threads1 & thread2) and the whole program immediately stops. 
    } 
}
```