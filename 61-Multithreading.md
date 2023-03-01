
```java
public class MyThread extends Thread{

	@Override  
	public void run() {  //When we start an instance of this thread, the code inside run() function executes. run() is a function of Thread class.
		
		for(int i =10;i>0;i--) {
			System.out.println("Thread #1 : "+i);  // 10-1
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
			System.out.println("Thread #2 : "+i);  // 0-9
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

# Syncronized Method Demo:

```java
public class MessagePrinter {

    // public synchronized void display(String message){
    public void display(String message) {
        // When multiple threads are trying to access the same method (display()) at the
        // same time - adding the 'syncronized' keyword to the function definition makes
        // the whole operation syncronized - that means the function will attend to only
        // one thread at a time. After the function completes/delivers the request of
        // 1st Thread, then it moves on to attend to the next Thread.

        System.out.print("<" + message);
        try {
            Thread.sleep(3000);
        } catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        System.out.println(">");
    }
}


public class MessageThread extends Thread {
    String message;
    MessagePrinter messagePrinter;

    MessageThread(String message, MessagePrinter messagePrinter) {
        this.message = message;
        this.messagePrinter = messagePrinter;
    }

    @Override
    public void run() {
        messagePrinter.display(message);
    }
}

public class Main {
	public static void main(String[] args) {
		MessagePrinter messagePrinter = new MessagePrinter();

		MessageThread messageThread1 = new MessageThread("Hello World !", messagePrinter);
		MessageThread messageThread2 = new MessageThread("Sigma", messagePrinter);
		MessageThread messageThread3 = new MessageThread("Delta", messagePrinter);

		messageThread1.start(); // Accessing display() method of MessagePrinter class.
		messageThread2.start(); // Accessing display() method of MessagePrinter class.
		messageThread3.start(); // Accessing display() method of MessagePrinter class.

		// <Hello World !>
		// <Delta>
		// <Sigma>

		// Here the display() function of MessagePrinter class attends the request of
		// only one thread at a time and moves to the next Thread only after completing
		// the delivery to the 1st Thread --- due to the use of `synchronized` keyword -
		// in the display() function definition - of MessagePrinter class.

		// Output without the use of `synchronized` keyword in the display() method
		// ************************************************************************* */
		// <Sigma<Hello World !<Delta>
		// >
		// >
	}
}
```

# Synchronized Block Demo:

```java
public class MessagePrinter {

    public void display(String message) {
        System.out.print("<" + message);
        try {
            Thread.sleep(3000);
        } catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        System.out.println(">");
    }
}

public class MessageThread extends Thread {
    String message;
    MessagePrinter messagePrinter;

    MessageThread(String message, MessagePrinter messagePrinter) {
        this.message = message;
        this.messagePrinter = messagePrinter;
    }

    @Override
    public void run() {
        // syncronized block - execution of all other threads is stopped until the
        // complete execution of the code inside this block.
        synchronized (messagePrinter) {
            messagePrinter.display(message);
        }
    }
}

public class Main {
	public static void main(String[] args) {
		MessagePrinter messagePrinter = new MessagePrinter();

		MessageThread messageThread1 = new MessageThread("Hello World !", messagePrinter);
		MessageThread messageThread2 = new MessageThread("Sigma", messagePrinter);
		MessageThread messageThread3 = new MessageThread("Delta", messagePrinter);

		messageThread1.start(); // run() Method has a synchronized block
								// No other thread or code will execute until the complete execution of the synchronized block within run() 
		messageThread2.start(); // run() Method has a synchronized block
								// No other thread or code will execute until the complete execution of the synchronized block within run() 
		messageThread3.start(); // run() Method has a synchronized block
								// This thread will start only after complete execution of above thread.

		// <Hello World !>
		// <Delta>
		// <Sigma>

		// Same output as in the case of `syncronized method demo`
	}
}
```