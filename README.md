# Worksheet on Logic Programming: Three

In the following questions you may presume the existence of the following knowledge base:
```
invented(edison,lightbulb). 
invented(colmeraurer,prolog). 

iq(einstein,210). 
iq(edison,160). 
iq(waldorf,90). 

genius(Person):-
  iq(Person,IQ),
  IQ > 150. 
genius(Person):-
  invented(Person,_).
```
1. When we pose the query 
    ```
    ?-genius(A).
    ```
    
    
    what is the first answer that prolog will return?
1. When we pose the query
    ```
    ?-genius(A).
    ```
    ensitein
    
    how many answers (if we cycle through all answers by pressing `;` after each answer) will Prolog display and what are they?
    
    4: 
    enstien
    edison
    edison
    colmeraurer
    
1. Define a predicate `smart_invention/1` which returns inventions that were invented by people with an IQ of 160 or more.
1. "Beam me up, Scottie, there is no intelligent life down here” (Star Trek — the original series)  
  To help the Star Trek crew determine if there is intelligent life we add the following predicate to our knowledge base:
    ```
    no_beam:- 
      genius(Person),
      write(’I found intelligent life, sir!’), 
      nl.
    ```
    smart_invention(X) :- invented(Y,X), iq(Y,Z), Z>=160.
    
    When we pose the query
    ```
    ?- no_beam.
    ```
    how many times will Prolog write out the 
    ```
    I found intelligent life, sir!
    ```
    sentence?  
    
    4 times, as explained above that calling genius produces 4 results. 
    
    Justify your answer.
