# Red-Black Trees

Created: November 23, 2022 8:16 PM

### Name: Bhushan Wanjari

### Roll no: A-37 (5th Sem)

### DAA TA-2

## Introduction :

A red-black tree is a kind of self-balancing binary search tree where each node has an extra bit, and that bit is often interpreted as the color (red or black). These colors are used to ensure that the tree remains balanced during insertions and deletions. Although the balance of the tree is not perfect, it is good enough to reduce the searching time and maintain it around O(log n) time, where n is the total number of elements in the tree.
Most of the BST operations (e.g., search, max, min, insert, delete.. etc) take O(h) time where h is the height of the BST. The cost of these operations may become O(n) for a skewed Binary tree. If we make sure that the height of the tree remains O(log n) after every insertion and deletion, then we can guarantee an upper bound of O(log n) for all these operations. The height of a Red-Black tree is always O(log n) where n is the number of nodes in the tree.

### Rules for Red-Black Trees :

1. Every node has a color either red or black.
2. The root of the tree is always black.
3. There are no two adjacent red nodes (A red node cannot have a red parent or red child).
4. Every path from a node (including root) to any of its descendants NULL nodes has the same number of black nodes.
5. All leaf nodes are black nodes.

![photo_2022-11-24_18-20-54.jpg](Red-Black%20Trees%20d4676bde969e4d71b9e80299971ed9a1/photo_2022-11-24_18-20-54.jpg)

### Inserting an element into a Red-Black Tree :

While inserting a new node, the new node is always inserted as a RED node. After insertion of a new node, if the tree is violating the properties of the red-black tree then, we do the following operations.

1. Recolor
2. Rotation

### Rotations in Red Black Trees :

In rotation operation, the positions of the nodes of a subtree are interchanged.
Rotation operation is used for maintaining the properties of a red-black tree when they are violated by other operations such as insertion and deletion.

### There are two types of rotations :

### 1) Left Rotation -

In left-rotation, the arrangement of the nodes on the right is transformed into the arrangements on the left node.

             **Algorithm(T,x):**

```
1) y <-- right[x]
2) right[x]<-- left[y] // Turn y's left subtree into x's right subtree.
3) p[left[y]] <-- x
4) p[y] <-- p[x] // Link x's parent to y.
5) if p[x] = nil[T] then
6)    root[T] <-- y
7) else if x = left[p[x]] then
8)                    left[p[x]] <--y
9)           else right[p[x]] <-- y
10) left[y] <--x //put x on y's left.
11) p[x] <--y
```

![photo_2022-11-24_18-22-26.jpg](Red-Black%20Trees%20d4676bde969e4d71b9e80299971ed9a1/photo_2022-11-24_18-22-26.jpg)

### 2) Right Rotation -

In right-rotation, the arrangement of the nodes on the left is transformed into the arrangements on the right node.

              **Algorithm(T,x):**

```
1) y <-- left[x]
2) left[x]<-- right[y] // Turn y's right subtree into x's left subtree.
3) p[right[y]] <-- x
4) p[y] <-- p[x] // Link x's parent to y.
5) if p[x] = nil[T] then
6)    root[T] <-- y
7) else if x = left[p[x]] then
8)                    left[p[x]] <--y
9)           else right[p[x]] <-- y
10) right[y] <--x //put x on y's right.
11) p[x] <--y
```

![photo_2022-11-24_18-23-07.jpg](Red-Black%20Trees%20d4676bde969e4d71b9e80299971ed9a1/photo_2022-11-24_18-23-07.jpg)

### 3) Left-Right Rotation -

In left-right rotation, the arrangements are first shifted to the left and then to the right.

![photo_2022-11-24_18-23-59.jpg](Red-Black%20Trees%20d4676bde969e4d71b9e80299971ed9a1/photo_2022-11-24_18-23-59.jpg)

### 4) Right-Left Rotation -

In left-right rotation, the arrangements are first shifted to the left and then to the right.

![photo_2022-11-24_18-24-50.jpg](Red-Black%20Trees%20d4676bde969e4d71b9e80299971ed9a1/photo_2022-11-24_18-24-50.jpg)

### Insertion Algorithm :

              **Algorithm(root , key):**

```
//The color of the inserted new node is Red
color[key] <- Red
while(key≠root and color (p[key]=Red))
do if p[key]= left(p[p[key]])
   Then y←right[p[p[key]]
// If the parent of the new node is Red(if there is Grandparent instead
root Node) Flip the color.
   if color[y]← Red
   then color(p[key])← Black
      color(p[p[key]])← Red
      key← p[p[key]]
   else if key← right[p[key]]
      then key← p[key]
      //When parent of new node has the red color and its sibling is NULL
   LeftRotate(root,key)
   color(p[key]) ← Black
   color(p[p[key]]) ← Red
RotateRight(root,p[p[key]])
else exchange then left and right elements to make it balance.
color(root)← Black
```

![photo_2022-11-24_18-24-55.jpg](Red-Black%20Trees%20d4676bde969e4d71b9e80299971ed9a1/photo_2022-11-24_18-24-55.jpg)

### Applications of Red-Black Trees :

1)  To implement finite maps.

2)  To implement Java packages: TreeMap and TreeSet.

3)  To implement Standard Template Libraries (STL) in C++: multiset, map, multimap.

4)  In Linux Kernel.

5) Machine Learning K-mean clustering algorithm for reducing Time Complexity.

6) MySQL also uses Red-Black Tree indexing to reduce the searching and insertion time.