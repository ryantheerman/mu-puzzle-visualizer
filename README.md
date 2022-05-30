# mu-puzzle-visualizer
app to interactively visualize hofstadter's mu puzzle. good luck lol


Instructions:
Given the string "MI", the object is to produce the string "MU" by application of certain rules. The only characters allowed in this system are "M", "I", and "U".

Rule 0: The character sequence of any given string is fixed.
  ex: "MIUIU" cannot become "IMUUI", "UIUIM", or any other sequence except by valid mutations through the rules, which will produce a new string.
  
Rule 1: If you possess a string whose last letter is "I", you may add a "U" to the end.
  ex: From "MI" you may get "MIU"
  ex: From "MUUI" you may get "MUUIU"
  
Rule 2: Suppose you have Mx (x standing in for any sequence of characters following the "M" and running to the end of the string), you may add Mxx to your collection.
  ex: From "MIU" you may get "MIUIU"
  ex: From "MUM" you may get "MUMUM"
  ex: From "MU" you may get "MUU"
  note: x is not a valid character in the MIU system. It is nothing more than a variable to hold the string values to demonstrate the rule. No rule can produce x.
  
Rule 3: If "III" occurs in the string, you may make a new string with "U" in place of "III"
  ex: From "UMIIIMU" you could make "UMUMU"
  ex: From "MIIII" you could make "MUI" or "MIU"
  ex: From "MIIUIIU" you cannot apply this rule. The 3 Is must be consecutive.
  ex: From "MIII" you could make "MU"
  note: this rule works only in one direction. You cannot convert "U" to "III"
  
Rule 4: If "UU" occurs inside one of your strings, you can drop it.
  ex: From "UUU" you could get "U"
  ex: From "MUUUII" you could get "MUI"
