# Hashtable

# Hashtable����
1. ����
   1. ��ֵ��
      1. ������key-value pairs(items)��ht_item
      2. ��ɣ�char* key��char* value
   2. ��ϣ��
      1. ������hash_table��ht_hash_table
      2. ��ɣ�int size��int count��ht_item** items
   3. ���캯��
      1. �ص㣺ʹ��strdup()���������ַ���
   4. ��������
      1. �ص㣺ʹ��free()��������
2. ��ϣ����
   1. ���ܣ����ַ���ӳ��Ϊ0-size��һ������
      1. Ҫ�󣺾���ƽ���ķ��䵽��ϣ����
   2. collision
      1. ����������ɢ��
3. API
   1. insert
      1. ���ܣ��ҵ�����Ͱ����item
      2. �ص㣺����ѱ�ɾ������HT_DELETED_ITEM���Բ���
   2. search
      1. ���ܣ��ҵ�key����Ԥ��ֵ��item
      2. �ص㣺����ѱ�ɾ������HT_DELETED_ITEM��Ҫ����
   3. delete
      1. �ص㣺��ɾ��item������ĳ����ͻ����һ�ɾ���ᵼ�³�ͻ���޷��ҵ�
      2. ������ʹɾ�����λ��ָ��һ��ȫ���ڱ�(������ɾ��)
   4. update
      1. ���ܣ��ٴβ�����ͬkeyʱ�������һ�ε�value
      2. �ص㣺���ɵ�insert������(��Ѱ�ҿ���λ�õĳ�ͻ���бȽ��Ƿ����key)
4. resiezing
   1. ���ܣ���load<0.1ʱdown����load>0.7ʱup
   2. 