```HIPL
#import hipl.Standard.*;
#import hipl.BadParamsError;

class BadMemeError -> BadParamsError;

function squareMeme(string memetext) {
  if (memetext.length == 0) return;
  if (memetext[0] != memtext[-1]) throw new BadMemeError();
  
  println(memetext.split().join(" "));
  for (int i : range(1, memetext.length-1)) {
    println(memetext[i] + (' '*(2*memetext.length-3)) + memetext[i]);
  }
  println(memetext.split().join(" "));
}
```

Converts to


```Cpp
#include <hipl.Standard>
#include <hipl.BadParamsError>

class BadMemeError : public BadParamsError {};

void squareMeme(hstring memetext) {
  if (memetext.length == 0) return;
  if (memetext[0] != memetext[((-1 % memetext.length) + memetext.length) % memetext.length])
  
  Standard::println(memetext);
  
}
```
