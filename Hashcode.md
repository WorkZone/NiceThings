Default equals method 
  returns true if references are same [Object]
  
But generally we override to compare based on contents

hashCode produces integer in order to store object in data structures(HashMap, HashSet).

While working with data structure when we store object in buckets. If we use built-in hash technique, 
it generates two different hashcode. So we are storing the same identical object in two different places.
To avoid this kind of issues we should override the hashCode method also based on the following principles. 

    un-equal instances may have same hashcode.
    equal instances should return same hashcode.


First of all,HashMap checks if the hashCode of second is the same as first. Only if the values are the same,it will 
proceed to check the equality in the same bucket.

But here the hashCode is different for these 2 objects (because they have different memory address-from default 
implementation). Hence it will not even care to check for equality.

If you have a breakpoint inside your overridden equals() method,it wouldn't step in if they have different hashCodes. 
contains() checks hashCode() and only if they are the same it would call your equals() method.

stunning article
http://www.thejavageek.com/2013/06/28/significance-of-equals-and-hashcode/
