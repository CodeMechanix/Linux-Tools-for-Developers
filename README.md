# Linux Tools for Developers

| Title  | Command | Description |
| ------------- | ------------- | ------------- |
| cp -p (preserves timestamp)  | $ cp - p $file  | cp - p command will preserve the timestamp when you copy a file. |
| mkdir -p (create directory structure) | $ mkdir - p | when you copy a file /app/config/app.properties then it will create those directories automatically if they don't exist. | 
| scp -i (file copy without password using identity file) | $ scp -i /home/appuser/.ssh/id_rsa_app datauser@host:/app/data/outbound/stocks.xml | The SCP command is used to securely copy files and directories from one host to another host. When you copy files using SCP, it asks for your username and password but if you are doing using script, you better want to do a password-less SCP and that's where scp -i helps. Here the identity file: id_rsa_app contains the private/public key for "datauser". The beauty of this option is that it won't ask for a password if you run this command.
| grep -c  (count number of matches) | $ grep -c "keyword" app.log | Many times we are interested in knowing whether the file contains a matching word or not and the grep command just tells you that, but sometimes you also want to know how many times that particular keyword appears in files? I mean, could of the matching keyword. That's where grep -c helps. It will tell you the count of the matching keyword. It's very useful to find details like how many times a user has logged in or how many files he has downloaded, or how many instruments you have received from upstream, and so on. Given command will print how many times "keyword" has appeared in the app.log file.
| find -mtime (search files by modified time) | $ find -mtime -3 | One of them is -mtime which is a shortcut for modified time and can be used to search files that have been modified recently like in hours or days. This is very useful while troubleshooting to check if anyone touched any important files.
| cd - (takes you to the previous directory) | $ cd /home/test1/ $ cd /opt/bin/ $ cd - /home/test1/ | We all have used cd but do you know how to go to the previous directory quickly? Well, that's what "cd -" do. It takes you to the previous directory. |
| pwd -P (shows the actual path for soft linked directory)| $ pwd /com/unicorn/app/current $ pwd -P /com/unicorn/app/1.0.23 | pwd will tell you the current folder with the path you followed. |
| tail -f (seeing live updates on a file) | $ tail -f app.log | tail, it is used to see the content of the file from the bottom, and the tail -f lets you see the live updates. | 
| netstat -p (print process id  of the process for connections) | $ netstat -nap | grep LISTEN | Linux networking commands generally used to find the process which is listening on a particular port, but do you know how to print the process id which is listening on a port.It prints the process id and name of the program to which each socket belongs. This is useful because you now also kill the process if you don't want to.