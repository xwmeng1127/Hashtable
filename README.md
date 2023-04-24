# Hashtable

# Hashtable介绍
1. 构造
   1. 键值对
      1. 别名：key-value pairs(items)、ht_item
      2. 组成：char* key、char* value
   2. 哈希表
      1. 别名：hash_table、ht_hash_table
      2. 组成：int size、int count、ht_item** items
   3. 构造函数
      1. 特点：使用strdup()函数复制字符串
   4. 析构函数
      1. 特点：使用free()函数回收
2. 哈希函数
   1. 功能：将字符串映射为0-size的一个数字
      1. 要求：尽量平均的分配到哈希表中
   2. collision
      1. 方法：二次散列
3. API
   1. insert
      1. 功能：找到空闲桶放置item
      2. 特点：针对已被删除的项HT_DELETED_ITEM可以插入
   2. search
      1. 功能：找到key等于预期值的item
      2. 特点：针对已被删除的项HT_DELETED_ITEM需要跳过
   3. delete
      1. 特点：待删除item可能是某个冲突链的一项、删除会导致冲突项无法找到
      2. 方法：使删除项的位置指向一个全局哨兵(代表已删除)
   4. update
      1. 功能：再次插入相同key时会更新上一次的value
      2. 特点：集成到insert函数中(在寻找空闲位置的冲突链中比较是否存在key)
4. resiezing
   1. 