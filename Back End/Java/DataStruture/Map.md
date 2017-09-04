# Map相关用法

java获得map的key：

方式1

```java
  Iterator iterator = hashMap.keySet().iterator();
  while (iterator.hasNext()) {
    String key = (String)iterator.next();
    System.out.println(key+":"+hashMap.get(key));
  }

```

方式2：

```java
for(Iterator ite = map.entrySet().iterator(); ite.hasNext();){
  Map.Entry entry = (Map.Entry) ite.next();
  entry.getKey();
  entry.getValue();
}
```