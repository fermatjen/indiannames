The ner_ind_names.ser file is a Java-serialized List containing ~2.8 million indian names collected from various Indian news portals and social media channels. Note the the serialized list contains only the names and no other demographic details. Please feel free to use this for your Java-based NER/NLP projects.

Usage:

In Java

```java
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream("ner_ind_inames.ser"));
        ArrayList indNamesList = (ArrayList) ois.readObject();
        
        //indNamesList is already a sorted collection. Do a binary search.
        if((Collections.binarySearch(indNamesList, "Kunal".toLowerCase())) > 1){
            System.out.println("Indian Name!");
        }
``` 

In Scala

```scala
        val ois = new ObjectInputStream(new FileInputStream("ner_ind_inames.ser"))
        val indNamesList = ois.readObject().asInstanceOf[List[_]].asScala.toList

        if (indNamesList contains("kunal")) println("Indian Name!")
```

Remember, Indian population is ~1.3 billion and we have only ~2.8 million in our list. This list is by no way exhaustive but is a good start for your NER experiments.
