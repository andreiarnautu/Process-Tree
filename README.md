# Process-Tree
Kernel system function that fetches information about a process and its process subtree.

The kernel functions we have added are at the bottom of `sys_generic.c`.

* `int sys_children_count(struct proc *p, void *v, register_t *retval)` returns the number of children processes of a given process.
* `int sys_store_process(struct proc *p, void *v, register_t *retval)` stores relevant information about a process.

Once we added these functions to the Open BSD kernel, we were able to call them from userland using `pstree.c`. The program makes use of these newly added kernel functions and calls them recursively in order to reconstruct the process subtree of a given process.
