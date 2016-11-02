When I started awk I always wanted something like the below to just show me the power and usage of the tool. Awk is a lot more powerful than the below articulates, but this much will carry you a long ways

This can be copy and pasted into a terminal
```
printf 'i am 0\ni am 1\ni am 2\ni am 3\ni am 4\ni am 5\ni am 6\ni am 7\ni am 8\ni am 9' | 

awk 'BEGIN {print "pattern { } to match rows with regex. rows == lines. BEGIN/END are special"}            
           {print "empty matches all rows, use $0 for line: \""$0"\" and $n>1 to select columns like $3: "$3""} 
           /i am 3/ {print "I hate being 3 (matched only the \"i am 3\" line"} 
           END { print "Now you know everything you need to crush it with awk"}'
```

For reference see:
http://www.grymoire.com/Unix/Awk.html
