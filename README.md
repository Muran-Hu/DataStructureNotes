# DataStructureNotes
数据结构笔记
## 一、 数组 (Array) - 是一种线性表数据结构
#### 1. 数组支持随机访问, 根据下标随机访问的时间复杂度为 O(1).

#### 2. 数组：为什么很多编程语言中数组都从0开始编号？
######从数组存储的内存模型上来看, "下标"最确切的定义应该是"偏移(offset)". 如果用 a 来表示数组的首地址, a[0] 就是偏移为 0 的位置, 也就是首地址, a[k] 就表示偏移 k 个 type_size 的位置, 所以计算 a[k] 的内存地址只需要用这个公式：

    a[k]_address = base_address + k * type_size

######但是, 如果数组从 1 开始计数, 那我们计算数组元素 a[k] 的内存地址就会变为：

    a[k]_address = base_address + (k-1) * type_size
  
######对比两个公式, 不难发现，从 1 开始编号, 每次随机访问数组元素就多了一次减法运算, 对于 CPU 来说, 就是多了一次减法指令.

#### 3. 二维数组内存寻址公式：对于 m * n 的数组, a[i][j](i < m, j < n) 的地址为：
        
        a[i][j]_address = base_address + (i * n + j) * type_size

#### 4. ArrayList: 每次存储空间不够，他都会将空间自动扩容 1.5 倍大小. 扩容涉及内存申请和数据搬移，是比较耗时的，所以，如果事先能确定需要存储的数据大小，最好在创建 ArrayList 的时候事先指定数据大小.
        ArrayList<User> users = new ArrayList(1000);
        for(int i=0; i<1000; i++) {
            users.add(xxx);
        }

## 二、 链表 (Linked list)
#### 1. 常见策略：
        1. 先进先出 FIFO - Fist In, First Out
        2. 最少使用 LFU - Least Frequently Used
        3. 最近最少使用 LRU - Least Recently Used

#### 2. 常见链表结构
        1. 单链表
        2. 双向链表 - LinkedHashMap
        3. 循环链表
