#Shaker Sort
```
function shaker_sort($arr) {  
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

        $max2 = $arr[0];
        $min2 = $arr[0];
        
        for($i=array_key_last($arr); $i>=0; $i--) { 
            if(!isset($arr[$i-1]))
                break;
        
            if($min2 > $arr[$i])
                $min2 = $arr[$i];
        
            if($max2 < $arr[$i])
                $max2 = $arr[$i];
        
            if($arr[$i-1] > $arr[$i]) {
                $temp_number = $arr[$i];
                $arr[$i] = $arr[$i-1];
                $arr[$i-1] = $temp_number;
            }   
        }
    }
    while($arr[0] !== $min && $arr[array_key_last($arr)]);

    return $arr;
}
```