# Bubble Sort
```
function bubble_sort($arr) {  
    $max = $arr[0];
    $min = $arr[0];
 
    do {
        for($i=0; $i<count($arr); $i++) {  
            if(!isset($arr[$i+1]))
                break;
 
            if($arr[$i] > $max)
                $max = $arr[$i];

            if($min > $arr[$i])
                $min = $arr[$i];

            if($arr[$i] > $arr[$i+1]) { 
                $temp_number = $arr[$i];
                $arr[$i] = $arr[$i+1];
                $arr[$i+1] = $temp_number;
            }
    

        }
    }
    while($arr[0] !== $min && $arr[array_key_last($arr)]);
    
    return $arr;
}
```