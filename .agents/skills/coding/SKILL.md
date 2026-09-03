---
name: coding
description: test
---


<temp unrefined>

i have the following coding rule implementation:                                                                                                        
- pursue the most boring but robust solution. when you have multiple alternatives of implementing something, default to the simplest one unless you have a good reason not to. in that case, prompt the user to check first before proceeding                                                                                                            
- as modular as needed, emphasize on needed. dont implement very specific algorithm to support just one edge case, it will break on others              
- your code is not a scratch pad. you may not put many comment blocks. you only add comment when it is absolutely needed. even then 2 line comment  
is maximum
- if you add comment, it does not have to be a complete full sentence. make it brief concise, as long as it conveys the meaning well
- do not split your code lines into 80 col max, i dont like this style. 120-140 col is fine. i dont like wasting lines                                  
- dont add __init__ when not needed. this is prone to circular import if you're careless                                                                
- every parameter must be clearly typed                                                                                                                 
- every func should have docstring following google style. 1-2 lines brief explanation in the beginning, followed by args, returns, exception, etc.     
dont mention the type in explanation, the param type already explain that. no module level docstring, filename and structure should be clear enough
- you can implement as if you're going to test later (TDD) but the tests implementation comes later because implementation will undergo some iterations
