OPERATING SYSTEMS ASSIGNMENTS - SOURCE CODE

Files:
1_address_book.sh          Assignment 1: Shell address book
2_process_management.c     Assignment 2: fork, wait, zombie, orphan
3_producer_consumer.c      Assignment 3: producer-consumer
4_dining_philosophers.c    Assignment 4: dining philosophers
5_bankers_algorithm.c      Assignment 5: Banker's algorithm
6_fifo_process1.c          Assignment 6: FIFO process 1
6_fifo_process2.c          Assignment 6: FIFO process 2
7_parent_child_pipes.c     Assignment 7: two pipes with parent and child
8_disk_scheduling.c        Assignment 8: SSTF, SCAN, C-LOOK

COMPILE AND RUN (Linux / Ubuntu / WSL)

Assignment 1:
  chmod +x 1_address_book.sh
  ./1_address_book.sh

Assignment 2:
  gcc -Wall -Wextra 2_process_management.c -o assi2
  ./assi2

Assignments 3 and 4 (pthread + POSIX semaphores):
  gcc -Wall -Wextra 3_producer_consumer.c -o assi3 -pthread
  ./assi3
  gcc -Wall -Wextra 4_dining_philosophers.c -o assi4 -pthread
  ./assi4

Assignment 5:
  gcc -Wall -Wextra 5_bankers_algorithm.c -o assi5
  ./assi5

Assignment 6:
  Open two terminals in the same directory.
  Terminal 1: ./assi6_p1
  Terminal 2: ./assi6_p2
  Start Process 2 first, then Process 1. Enter sentences in Process 1,
  and type END on a separate line when finished.
  Compile:
    gcc -Wall -Wextra 6_fifo_process1.c -o assi6_p1
    gcc -Wall -Wextra 6_fifo_process2.c -o assi6_p2
  Both processes must run in the same working directory.

Assignment 7:
  gcc -Wall -Wextra 7_parent_child_pipes.c -o assi7
  ./assi7

Assignment 8:
  gcc -Wall -Wextra 8_disk_scheduling.c -o assi8
  ./assi8

NOTES:
- Assignment 2 uses _exit() in child processes to avoid duplicated buffered
  output after fork. The orphan child may continue briefly after its parent
  exits; observe it using process tools if required by your lab instructor.
- Assignment 6 creates fifo1 and fifo2 in the current directory. Remove stale
  FIFOs with: rm -f fifo1 fifo2
- Assignment 8 assumes cylinder 0 is at the spindle. Therefore moving away
  from the spindle means moving toward larger cylinder numbers. If your lab
  manual uses the opposite cylinder convention, reverse the initial direction.
