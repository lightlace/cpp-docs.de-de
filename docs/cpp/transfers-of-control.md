---
title: "&#220;bertragung der Steuerung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ablaufsteuerung, Verzweigen"
  - "Ablaufsteuerung, Übertragen der Steuerung"
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bertragung der Steuerung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die `goto`\-Anweisung oder eine **case**\-Bezeichnung in einer `switch`\-Anweisung verwenden, um ein Programm anzugeben, das sich hinter einem Initialisierer verzweigt.  Solcher Code ist nicht zulässig, es sei denn, die Deklaration, die den Initialisierer enthält, befindet sich in einem Block, der von dem Block eingeschlossen wird, in dem die Sprunganweisung auftritt.  
  
 Das folgende Beispiel zeigt eine Schleife, welche die Objekte `total`, `ch` und `i` deklariert und initialisiert.  Es gibt auch eine fehlerhafte `goto`\-Anweisung, die die Steuerung jenseits eines Initialisierers überträgt.  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 Im vorherigen Beispiel versucht die `goto`\-Anweisung, die Steuerung an der Initialisierung von `i` vorbei zu übergeben.  Wenn jedoch `i` zwar deklariert, aber nicht initialisiert ist, wäre die Übertragung gültig.  
  
 Die Objekte `total` und `ch`, die im Block deklariert wurden, der als *Anweisung* der `while`\-Anweisung verwendet wird, werden gelöscht, wenn dieser Block mit der `break`\-Anweisung beendet wird.  
  
## Siehe auch  
 [\(NOTINBUILD\) Declaration of Automatic Objects](assetId:///81f941e9-c1b1-4d1c-a28d-70b6ee9765db)