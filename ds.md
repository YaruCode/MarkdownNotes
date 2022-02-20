# 数据结构算法题汇总
二叉树的递归遍历代码

```C++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
typedef struct BiTNode{
    char data;
    struct BiTNode *lchild,*rchild;//定义左右孩子指针
}BiTNode, *BiTree;

void visit(BiTNode *node)
{
    cout<<(*node).data<<"\t";
}
void PreOrder(BiTree tree)
{
    if(tree!=NULL)
    {
        visit(tree);
        PreOrder(tree->lchild);
        PreOrder(tree->rchild);
    }
}

void InOrder(BiTree tree)
{
    if(tree!=NULL)
    {
        InOrder(tree->lchild);
        visit(tree);
        InOrder(tree->rchild);
    }

}

void PostOrder(BiTree tree)
{
    if(tree!=NULL)
    {
        PostOrder(tree->lchild);
        PostOrder(tree->rchild);
        visit(tree);
    }

}
int main()
{
    BiTNode a,b,c,d,e;
    a.data='a';
    b.data='b';
    c.data='c';
    d.data='d';
    e.data='e';
    c.lchild=NULL;
    c.rchild=NULL;

    a.lchild=&b;
    a.rchild=&c;

    b.lchild=&d;
    b.rchild=&e;

    e.lchild=NULL;
    e.rchild=NULL;

    d.rchild=NULL;
    d.lchild=NULL;

    //PreOrder(&a);
    //InOrder(&a);
    PostOrder(&a);
    return 0;
}

```

二叉树的非递归遍历代码
```C++


```