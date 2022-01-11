---
layout: post 
title: Advanced C++
categories: cs2150
image: https://www.modernescpp.com/images/blog/ModernCpp/timeline.png
---

# Sizeof

Don't forget byte alignment!

```cpp
bool a, b, c
long d
int i
```

That would be a `sizeof` of 24! Use the `sizeof.cpp` file to test more of this.

## Tests - Don't Scroll past the Code Block

`sizeof(gplistnode)`

```cpp

class gplistnode {
public:
    gplistnode* prev, *next;
    int id;
    gplistnode() : prev (nullptr), next (nullptr) {
        cout << "In gplistnode::constructor()" << endl;
        id = 1;
    }
    virtual ~gplistnode() { }
    virtual int getID() {
        return id;
    }
};
```

**Answer** - 32, because we have 3 8 byte pointers (`prev, next, virtual`) and a byte-aligned int

# Virtual

Virtual is **shared** inheritance, and uses up a byte of space for the vtable.
