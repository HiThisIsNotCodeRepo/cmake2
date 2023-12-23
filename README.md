# cmake2

```
# Build hello_world
cmake ..
# Build hello_world + feature set 0
cmake .. -DBUILD_CALC=ON
# Build hello_world + feature set 0/1
cmake .. -DBUILD_CALC=ON -DBUILD_CALC_F1=ON
# Build binary
g++ -o main test.cpp -lmyapp -L.
```
