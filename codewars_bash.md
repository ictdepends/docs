# codewars_bash.md
## 8 kyu
---
### Returning Strings
#### Instructions
Create a function that accepts a parameter representing a name and returns the message: "Hello, <name> how are you doing today?".

[Make sure you type the exact thing I wrote or the program may not execute properly]

##### Sample Tests
###### run the solution and store its result
 output = run_shell args: ['shell']

 describe "sample test" do
   it "should return \"Hello, <name> how are you doing today?\"" do
     expect(output).to eq('Hello, shell how are you doing today?')
   end
 end


```bash
#!/bin/bash

greeting() {
  local name="$1"
  echo "Hello, $name how are you doing today?"
}

greeting "$1"
```

---
