What is an OS?
-> An operating system is a piece of software that manages all the resources of a computer system, both hardware and software, and provides an environment in which user can executes his/her programs in a convenient and efficient manner by hiding underlying complexity of the hardware and acting as a resource manager.

Functions of OS
1) Resource management -> Os manages memory(ram), hard disk , processor etc.
2) If there is no os then application have to write it own memory management and resource management code which makes application bulky and complex.
3) Isolation and Protection -> Isolation -> user programs cannot interface with one-another. Protection ->User programs cannot access e.g memory that is not allocates to them, kernel privilege functions etc.
4) Interface between the user(software) and the computer hardware.
5) Abstraction -> Hides the underlying complexity of the hardware.
6) Access to the hardware.

Types of OS
Goals
1) Maximum CPU utilization -> meaning suppose there are two process P1 and P2 . First P1 process some task and go for I/O for copy and paste task. Here we dont want CPU to stay idel . So, while P1 doing I/O task we want P2 to some task for CPU utilization.
2) We don't need Process starvation -> meaning suppose there are two processes P1 and P2.  When Os is executing P1 process but P1 is very large like it have while loop, meaning the process will be running for infinite time. So we don't want due to Process P1 , P2 and other processes will derived from using CPU. 
3) High priority Job(processes) execution -> Suppose, there are three P1, P2, P3 processes running. Suddenly a high priority like anti-virus scanning  job/processes P4 comming, then priority should be given to P4 processes.

Types of OS
1) Single Process Os -> here only one job is executed at one time. So after finishing that job, another job can be executed. Its doesn't support the above Goals. Ex:- Ms DOS
2) Batch Processing OS -> here processes is divided into batches and send into CPU for computatation. It doesn't support the above Goals. ex: ATLAS
3)  Multi Programming OS ->  (SIngle CPU) -> here in this Os there is jobs(J1, J2,J3) which are in ready queue , which are ready to execute. When One process goes into I/o state then CPU pick another processes and execute it. Here, suppose CPU execute some task on P1 processes then P1 goes for I/o. Now CPU execute on P2 processes. The state of P1 is saved in Process Control Block(PCB). Then again CPU execute on P1 which process is called Context Switching. It also doesnt follow all Goals. ex:  THE
4) Multi Tasking OS -> (SIngle CPU) -> Context Switching . Same as Multi Programming OS but here -> TIme sharing is added means in Multi-Programming OS , when one processes is going for I/O, only at that time Context Switching happens. but what if process is not going for I/O then it can cause Process Starvation. but in Multi Tasking Os , there is time quantam = 100ms meaning CPU compute one proccess one process P1 for 100ms and other for 100ms. This makes application responsive or run smoothely. It follow all  above Goals. ex: CTSS
5) Multi Processing Os ->  here it have -> Context switching -> Time Sharing -> CPU >= 1 . Nowadays, a CPU have 8 core means we can say 8 CPU. ex: Linux
6) DIstributed OS -> Here , it have only one operating system and have many cpus with its own memory and all cpu are connected to the operating system through network. ex: Micros
7) RTOS(Real Time OS) -> This Os is used in place where there should be less error chance. like in aeroplane , nulcear plan.



Program -> A Program is an executable file which contains certain set of instructions written to complete the specific job or operation on your computer. -> Its a complied code. Ready to be executed. -> Stored in Disk.

PROCESS -> Program under execution. or -> exe -> double click -> Process. Resides in RAM.

Thread -> Light weight Process -> Independently executable. Multi-thread doesn't happen in one CPU. There is no isolation and protection between threads. If one process uses x amount of memory. Then all threads in a process also takes x amount of memory. Used to achieve parallelism by dividing's process's tasks which are independent path of execution. ex:- multiple tabs in a browser, text editor (When you are typing in an editor, spell-checking, and saving the text are done concurrently by multiple threads)

Thread Scheduling -> Threads are scheduled for execution based on their priority.

Differences between Thread Context Switching and Process Context Switching.

Thread Context Switching -> 1) Os saves current state of thread and switches to another thread of same process. 2) Doesn't includes switching of memory address space(But program counter, registers and stack are included). 3) Fast switching 4) CPU's cache state is preserved.

Process Context Switching -> 1) Os saves current state of process and switches to another process by restoring its state. 2) Includes switching of memory address space. 3) Slow switch 4) CPU's cache state is flushed.


Components of OS (OS -> User Space + Kernel)
1) User Space -> application are run here. No Hardware access. Have GUI and CLI. User Space interacts with kernel.
2) Kernel  -> access to underlying Hardware. Heart of OS. Interacts with Hardware. first part of OS to load on start up.

Functions of Kernel
1) Process Management -> Process Creation -> Process termination -> Process and Thread schedule. ->Process synchorization -> Process Communication.
2) Memory Management -> Allocate/deallocate memory -> Free space management. Keeping track of which part of memory are currently being used and by which process.
3) File Management -> create/delete files -> directory management  
4) I/O Management -> management and controlling of all I/O devices. 4.1) Spooling 4.2) Buffering  4.3) Caching

User Mode and Kernel Mode -> When we write command `mkdir A ` in CLI , it is in User Mode and to create a directory,  User Mode changes into Kernel Mode (kernel have the implementation for commands in c language)  and make directory which is done through SOftware Interrupt.

How does two processes P1 and P2 communicate in User Mode  and Kernel Mode?
-> Through IPC(InterProcessCommunication)
We can achieve IPC through 2 ways:-
1) Shared Memory 
2) Message Passing


Types of Kernel 
1) Monolithic Kernel -> Here all four functions of Kernel are stored in Kernel.  Advantages a) Fast Communication between different component of  kernel.  Disadvanatges a) Kernel Bulky b) Less reliable(if process management component is damaged then all components also damaged ). ex:- Linux , Unix
2) Micro Kernel -> Here main function Memory management and Process management are stored in Kernel Space and FIle and I/O management are stored in User Space. Adv a) Less Bulky b) More Reliable c) Stable. Disadv a) Less Performance  due to switching between User Mode and Kernel Mode like Kernel Mode do some memory management and go for I/O in User Mode and again come in Kernel Space for Process Management. Ex:- L4 Linux, Symbian OS
3) Hybrid Kernel -> Here FIle mngment is in User space and Process,Memory, I/O management is in Kernel Space. ex:- MacOS , Windows.
4) Nano Kernel
5) Exo Kernel 


System Calls
-> A system call is a mechanism using which a user program can request a service from the kernel for which it does not have the permission to perform. User programs typically do not have permission to perform operations like accessing I/O devices and communicating other programs.
-> all system calls are implemented in c programming language.
-> System call lies between user mode and kernel mode. 
-> Ex-> when we run `hellworld.exe` program, it search for system call  which provides by system call interface then it switch into kernel mode.
in kernel there is process-management which creates process. at last it returns into user mode.
-> System call interface look for implementation code in kernel for particular task and then kernel executes that code.

How to switch from User mode to Kernel Mode?
-> through software interrupt -> software interrupt is nothing but while cpu is doing something , telling cpu to stop certain task and do this emergency task.


Types of system Calls
1) Process management
2) File Management
3) Device Management
4) Information Management 
5) Communication


How Operating System boots up?
Step 1) Power On
Step 2) CPU loads BIOS or UEFI(UEFI is upgraded version of BIOS) -In BIOS, how system components are intialized ,programs are written.
a) First CPU initialized.
Step 3) BIOS or UEFI run test and initialize hardware.
a) loads some settings from a memory area which is backend by CMOS battery. b) POST(Power on Self Test) means here it test whether the RAM is working fine or not.
Step 4) BIOS or UEFI hand off to Boot device -> here BIOS have done its job, now its need a program that boot a OS called boot loader.
-> Boot loader -> a program when executes -> it on the actual OS
-> Boot devices -> disk , CD , usb device.

Boot loader can be found in a) MBR(Master Boot Record  ) -> It lies in 0th index of disk. Used in old device . Mainly used by BIOS.
b) EFI -> Used by UEFI -> Partation on disk
Step 5) Boot loader loads the full OS


32 bit vs 64 bit operating system?
-> In 32 bit Os , it have 32 bit register and in 64 bit OS, it have 64 bit register.

 