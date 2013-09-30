Simulating the process of hooking up hydrogen
atoms with oxygen atoms to form water molecules. Each atom is represented by a
separate thread, we will need to associate two hydrogen threads with one oxygen
thread to make a water molecule, then all three threads exit together.

We will use two general semaphores, one to count the number of hydrogen threads and
one for the number of oxygen threads. A hydrogen thread will wait to consume one of
the oxygen and then signal to raise the count of hydrogen to communicate to the
oxygen thread. An oxygen thread will wait for two hydrogen to come ready and then
signal the oxygen count twice to let them know oxygen is ready.