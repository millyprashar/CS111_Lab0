## UID: 205836697

# A Kernel Seedling

Kernel module that creates a file /proc/count which shows the current number of running processes.

## Building

The Makefile contains instructions on how to build the kernel module. It specifies the source files, target name, and any necessary flags or dependencies.

## Running

First run the `make` command to compile the kernel module. We expect to see:

`make[1]: Entering directory '/usr/lib/modules/5.14.8-arch1-1/build'`
  `CC [M]  /home/cs111/CS111_Lab0/proc_count.o`
  `MODPOST /home/cs111/CS111_Lab0/Module.symvers`
  `CC [M]  /home/cs111/CS111_Lab0/proc_count.mod.o`
  `LD [M]  /home/cs111/CS111_Lab0/proc_count.ko`
  `BTF [M] /home/cs111/CS111_Lab0/proc_count.ko`
`make[1]: Leaving directory '/usr/lib/modules/5.14.8-arch1-1/build'`

Then we load the module by using the command `sudo insmod proc_count.ko`. This command evokes the start initialize function proc_count_init(), shouldn't expect to see anything here.

We can get details of the running processes in /proc. To see the number of processes running at a time we will use the command `cat /proc/count`, count is specified as the proc_dir_entry. Should expect to see the number of running processes.

## Cleaning Up

Explain how to remove your kernel module and clean up the code
To remove the kernel module we use the command `sudo rmmod proc_count`. This command evokes the end cleanup function proc_count_exit(), shouldn't expect to see anything here. To clean up the code we run `make clean`, shouldn't expect to see anything here.

## Testing

Tested using kernel release 5.14.8-arch1-1 and kernel version #1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000