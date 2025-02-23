Task: bring back relationships in life and their formal characteristics.  

List of them, and their formal properties. Eg 

  - Part of 
  - Believes 
  - desires 

Prior to next meeting please send me at least 2 relations you've identified and answers to the following questions:
  - Is this relation reflexive, i.e. for every x is xRx
  - Is this relation irreflexive, i.e. no x is such that xRx
  - Is this relation symmetric, i.e. for every x and y, if xRy then yRx
  - Is this relation antisymmetric, i.e. for every x and y, if xRy and yRx then x=y
  - Is this relation asymmetric, i.e. for every x and y, if xRy then it is not the case that yRx
  - Is this relation functional, i.e. for every x, y and z, if xRy and xRz then y=z
  - Is this relation inverse functional, i.e. for every x, y, z, if xRy and zRy then x=z
  - Is this relation transitive, i.e. for every x, y, and z, if xRy and yRz then xRz

assumptions: 
 - "in life" and lower-case variables imply instances/particulars, not classes/universals
 - "in life" and upper-case variable R implies 

Relationship 0, *john-d-4 flies fa3000aaa*: 
  - Is this relation reflexive
    - i.e. for every x is xRx
    - for every john-d-4 is john-d-4 flies john-d-4
    - no
  - Is this relation irreflexive
    - i.e. no x is such that xRx
    - no john-d-4 is such that john-d-4 flies john-d-4
    - yes
  - Is this relation symmetric
    - i.e. for every x and y, if xRy then yRx
    - for every john-d-4 and y, if john-d-4 flies fa3000aaa then fa3000aaa flies john-d-4
    - no
  - Is this relation antisymmetric
    - i.e. for every x and y, if xRy and yRx then x=y
    - for every john-d-4 and fa3000aaa, if john-d-4 flies fa3000aaa, and fa3000aaa flies john-d-4, then john-d-4 = fa3000aaa
    - no
  - Is this relation asymmetric
    - i.e. for every x and y, if xRy then it is not the case that yRx
    - for every john-d-4 and fa3000aaa, if john-d-4Rfa3000aaa then it is not the case that fa3000aaa flies john-d-4
    - yes
  - Is this relation functional
    -   i.e. for every x, y and z, if xRy and xRz then y=z
    -   for every john-d-4, fa3000aaa and fa3111bbb, if john-d-4 flies fa3000aaa and john-d-4 flies fa3111bbb then fa3000aaa=fa3111bbb
    -   no
  - Is this relation inverse functional
    - i.e. for every x, y, z, if xRy and zRy then x=z
    - for every john-d-4, fa3000aaa, fa3111bbb, if john-d-4 flies fa3000aaa and fa3111bbb flies fa3000aaa then john-d-4=fa3111bbb
    - no
  - Is this relation transitive
    - i.e. for every x, y, and z, if xRy and yRz then xRz
    - for every john-d-4, fa3000aaa, and fa3111bbb, if john-d-4 flies fa3000aaa and fa3000aaa flies fa3111bbb then john-d-4 flies fa3111bbb
    - no
  
Relationship 1 *john-d-4 has_role pilot*: 
  - Is this relation reflexive
    - i.e. for every x is xRx
    - for every john-d-4 is john-d-4 has_role john-d-4
    - no
  - Is this relation irreflexive
    - i.e. no x is such that xRx
    - no john-d-4 is such that john-d-4 has_role john-d-4
    - yes
  - Is this relation symmetric
    - i.e. for every x and y, if xRy then yRx
    - for every john-d-4 and y, if john-d-4 has_role pilot then pilot has_role john-d-4
    - no
  - Is this relation antisymmetric
    - i.e. for every x and y, if xRy and yRx then x=y
    - for every john-d-4 and pilot, if john-d-4 has_role pilot and pilot has_role john-d-4 then john-d-4=pilot
    - no
  - Is this relation asymmetric
    - i.e. for every x and y, if xRy then it is not the case that yRx
    - for every john-d-4 and pilot, if john-d-4 has_role pilot then it is not the case that pilot has_role John
    - no
  - Is this relation functional
    -   i.e. for every x, y and z, if xRy and xRz then y=z
    -   for every john-d-4, pilot and crewmember, if john-d-4 has_role pilot and john-d-4 has_role crewmember then pilot=crewmember
    -   yes
  - Is this relation inverse functional
    - i.e. for every x, y, z, if xRy and zRy then x=z
    - for every john-d-4, pilot, crewmember, if john-d-4 has_role pilot and crewmember has_role pilot then john-d-4=crewmember
    - yes
  - Is this relation transitive
    - i.e. for every x, y, and z, if xRy and yRz then xRz
    - for every john-d-4, pilot, and crewmember, if john-d-4 has_role pilot and pilot has_role crewmember then john-d-4 has_role crewmember
  	- yes
