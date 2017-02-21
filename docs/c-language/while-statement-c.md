---
title: "while-Anweisung (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "while-Schlüsselwort [C]"
  - "while-Schlüsselwort [C], Syntax"
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# while-Anweisung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der `while`\-Anweisung können Sie eine Anweisung solange wiederholen, bis ein angegebener Ausdruck den Wert "false" aufweist.  
  
## Syntax  
 *iteration\-statement*:  
 **while \(**  *expression*  **\)** *\-Anweisung*  
  
 Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen.  Die Ausführung erfolgt folgendermaßen:  
  
1.  Der *Ausdruck* wird ausgewertet.  
  
2.  Wenn der *Ausdruck* zu Beginn den Wert "false" hat, wird der Text der `while`\-Anweisung nicht ausgeführt, und das Steuerelement wird von der `while`\-Anweisung an die nächste Anweisung im Programm übergeben.  
  
     Wenn der *Ausdruck* den Wert "true" hat \(ungleich 0 ist\), wird der Text der Anweisung ausgeführt und der Prozess ab Schritt 1 wiederholt.  
  
 Die `while`\-Anweisung kann auch beendet werden, wenn eine **break**\-, `goto`\- oder `return`\-Anweisung im Anweisungstext ausgeführt wird.  Verwenden Sie die **continue**\-Anweisung, um eine Iteration zu beenden, ohne die `while`\-Schleife zu beenden.  Die **continue**\-Anweisung übergibt das Steuerelement an die nächste Iteration der `while`\-Anweisung.  
  
 In diesem Beispiel wird die `while`\-Anweisung veranschaulicht:  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 In diesem Beispiel werden Zeichen aus `string2` nach `string1` kopiert.  Wenn `i` größer als oder gleich 0 ist, wird `string1[i]` an `string2[i]` zugewiesen und `i` dekrementiert.  Wenn `i` 0 erreicht oder niedriger ist, wird die Ausführung der `while`\-Anweisung beendet.  
  
## Siehe auch  
 [while\-Anweisung \(C\+\+\)](../cpp/while-statement-cpp.md)