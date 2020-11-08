# C_Linked_List

newnode()/lnkedlist() return a pointer to the respective type with each value set to null. remember to deallocate

deletelist(struct lnkedlist*) deletes all nodes in the list (includeing the data, so watch out if that's not dynamically allocated), then deletes the list

getat(struct lnkedlist*, unsigned) returns value at index or NULL if index out of range. indexing starts at zero

findlast(struct node*) returns the last value in a chain of nodes (or the node returned if node->next = NULL). returns NULL if node passed is NULL

setnull(struct lnkedlist*) sets all data values to null (useful if you didn't allocate any memory on the heap for the values in the nodes and want to delete the list or its contents).

deleteall(struct lnkedlist*) deletes all nodes in list and their data and sets root and last to NULL

deleteat(struct lnkedlist*, unsigned) returns 1 if index out of range. otherwise, sets next of node before to node at index's next, and node after's previous to node at index's previous. then it deletes the node and its contents and returns 0. updates list->last if last has been deleted.

deletenode(struct node*) deletes node, setting its next and previous nodes to point to eachother, if not NULL, otherwise it does nothing. 

deletelast(struct lnkedlist*) is equivalent to deleteat(struct lnkedlist*, index of last) except it's way faster. if last is set to NULL, it will set last to findlast(list->root). if root is NULL it will do nothing.

insert(struct lnkedlist*, void* data) inserts a node that points to data (NOT A COPY OF DATA) to last. if root is NULL, root will also point to this node

insertat(struct lnkedlist*, void* data, unsigned) if index is out of range returns 1. otherwise, inserts a node that points to data (NOT A COPY OF DATA) to index and returns 0. cannot insert to last, to do that use insert

insertc(struct lnkedlist*, void* data, unsigned size) just like insert except that it inserts a copy, not the real thing.

insertcat(struct lnkedlist*, void* data, unsigned size, unsigned index) just like insertat, but inserts a copy, not the real thing. 
