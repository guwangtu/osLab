# .PHONY: gdb qemu qemu-gdb

## execute bomb
bomb: bomb-builder
	./bomb-builder < ./student-number.txt
	chmod +x ./bomb

qemu: bomb
	qemu-aarch64 ./bomb

qemu-gdb: bomb
	qemu-aarch64 -g 1234 ./bomb

gdb:
	gdb-multiarch -ex "set architecture aarch64" -ex "target remote localhost:1234" -ex "add-symbol-file bomb"