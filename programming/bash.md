Memo on some bash scripts

# Commands

* Find out current working directory of process: `pwdx <pid>`, [reference](http://unix.stackexchange.com/questions/94357/find-out-current-working-directory-of-a-running-process)
* Find out cmdline arguments of process: `cat /proc/<pid>/cmdline`, [reference](http://stackoverflow.com/questions/821837/how-to-get-the-command-line-args-passed-to-a-running-process-on-unix-linux-syste)
* Find out the virtual address space of running process `pmap <pid>`, [reference](http://www.kdgregory.com/?page=java.byteBuffer)
* Read file as hex of binary: `od -tx1 <filepath>`, [reference](http://www.kdgregory.com/?page=java.byteBuffer)
