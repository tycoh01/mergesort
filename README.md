# mergesort

mergesort([],[]).    /* covers special case */
mergesort([A],[A]).
% mergesort(S,S). %it's weird since a)its comment is not SortList b)semantics because the difference mergesort and merge. 
mergesort([A,B|R],S) :-  
   split([A,B|R],L1,L2), %one input and two output. weird version..split(L,L1,L2).
   mergesort(L1,S1),
   mergesort(L2,S2),
   merge(S1,S2,S).

