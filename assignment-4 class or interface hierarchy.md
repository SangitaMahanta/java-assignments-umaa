# ASSIGNMENT-4 #

  ## **1.**  **LinkedList (C):** ##
   
   ### ***Extends :*** ###
      AbstractSequentialList (ac)
   ### ***Implements :*** ###
     List<E> (I), Deque<E> (I), Cloneable (I), java.io.Serializable (I)
     
 *   **AbstractSequentialList (ac) :**

      ***Extends :***     AbstrcatList: (ac)    
     
         
 *   **AbstractList (ac) :**
   
     ***Extends :***   AbstractCollection (ac)
   
     ***Implemnets :***   List (I)
   

  * **AbstractCollection (ac) :** 
     
       ***Implemnets :***   Collection (I)
     
     
  * **Collection(I) :** 
           
       ***Extends :***  Iterable(I)

* ###  **Abstract Methods of above abstract classes :** ###
   #### **1.**  **AbstractSequentialList (ac) :** ####    
             a)listIterator(int index);
   #### **2.**  **AbstractList (ac) :** ####    
             a)get(int index);
   #### **3.**  **AbstractCollection (ac) :** ####    
             a)iterator();
             b)size();
             
             
## **2.**  **ArrayList (C):** ##
   ### ***Extends :*** ###
      AbstractList (ac)
   ### ***Implements :*** ###
    List<E>, RandomAccess, Cloneable, java.io.Serializable
    
  *   **AbstractList (ac) :**   
    ***Extends :***    AbstractCollection: (ac)  
    ***Implemnets :***  List<E>
   
  *   **AbstractCollection (ac) :**    
      ***Implemnets :***   Collection<E>
   
  * ###  **Abstract Methods of above abstract classes :** ###
  
     #### **1.**  **AbstractList (ac) :** ####    
             a)get(int index);
             
     #### **2.**  **AbstractCollection (ac)  :** ####    
             a)iterator();
             b)size();      
             
 ## **3.**  **Stack (C):** ##
   ### ***Extends :*** ###
      Vector<E>
 *   **Vector (c) :**   
 
     ***Extends :***    AbstractList: (ac)  
     ***Implemnets :***  List<E>, RandomAccess, Cloneable, java.io.Serializable
    
   *   **AbstractList (ac) :**
   
       ***Extends :***   AbstractCollection (ac)
       ***Implemnets :***   List (I)
       
   *   **AbstractCollection (ac) :**    
       ***Implemnets :***   Collection(I)
       
   * ###  **Abstract Methods of above abstract classes :** ###
   
     #### **1.**  **AbstractList (ac) :** ####   
              a)get(int index);
     #### **2.**  **AbstractCollection (ac)  :** ####    
             a)iterator();
             b)size();  
             
             
## **4.**  **ArrayBlockingQueue (C):** ##
   ### ***Extends :*** ###
     AbstractQueue (ac)
   ### ***Implements :*** ###
    BlockingQueue<E>, java.io.Serializable 
    
 *   **AbstractQueue (ac) :**
 
        ***Extends :***    AbstractCollection (ac)   
        ***Implemnets :***    Queue<E>
   
*   **AbstractCollection (ac) :** 

      ***Implemnets :***   Collection(I)
    
* ###  **Abstract Methods of above abstract classes :** ###
     #### **1.**  **AbstractQueue (ac) :** ####   
              None
     #### **2.**  **AbstractCollection (ac)  :** ####    
             a)iterator();
             b)size();  
     
     
## **5.**  **LinkedBlockingQueue (C):** ##
  ### ***Extends :*** ###
     AbstractQueue (ac)
   ### ***Implements :*** ###
     BlockingQueue<E>, java.io.Serializable
     
  *   **AbstractQueue (ac) :**
 
        ***Extends :***    AbstractCollection (ac)   
        ***Implemnets :***    Queue<E>
  
  *   **AbstractCollection (ac) :** 

      ***Implemnets :***   Collection(I)
  
  * ###  **Abstract Methods of above abstract classes :** ###
     #### **1.**  **AbstractQueue (ac) :** ####   
              None
     #### **2.**  **AbstractCollection (ac)  :** ####    
             a)iterator();
             b)size();
