  ```
  static int[] reversed(int[] arr) {    
    int[] newArray = new int[arr.length];    
    for(int i = 0; i < arr.length; i += 1) {    
      arr[i] = newArray[arr.length - i - 1];    
    }    
    return arr;    
  }  
```
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
