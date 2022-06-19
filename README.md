# mergesort

mergesort([],[]).    /* covers special case */
mergesort([A],[A]).
mergesort([A,B|R],S) :-  
   split([A,B|R],L1,L2), %one input and two output. weird version..split(L,L1,L2).
   mergesort(L1,S1),
   mergesort(L2,S2),
   merge(S1,S2,S).

split([],[],[]).
split([A],[A],[]). 
split([A,B|R],[A|Ra],[B|Rb]) :-  split(R,Ra,Rb). %what is the truth about the results___split(R,Ra,Rb)?
% conditional in the rule must be true
merge(A,[],A). %it is a fact
merge([],B,B). %it is a fact
merge([A|Ra],[B|Rb],[A|M]) :-  A =< B, merge(Ra,[B|Rb],M). % head must be true so body must be true
merge([A|Ra],[B|Rb],[B|M]) :-  A > B,  merge([A|Ra],Rb,M).
% 三段論分析
