---
title: Initialisieren von Zeichenfolgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c01dbea3cbcfaf89280f5fd61a31646b88ac491a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="initializing-strings"></a>Initialisieren von Zeichenfolgen
Sie können ein Zeichenarray (oder Breitzeichen) mit einem Zeichenfolgenliteral (oder Breitzeichenfolgenliteral) initialisieren. Zum Beispiel:  
  
```  
char code[ ] = "abc";  
```  
  
 initialisiert `code` als Zeichenarray mit vier Elementen. Das vierte Element ist das Nullzeichen, welches alle Zeichenfolgenliterale beendet.  
  
 Eine Bezeichnerliste kann nur so lang sein, wie die Anzahl von zu initialisierenden Bezeichnern. Beim Erstellen einer Arraygröße, die kürzer als die Zeichenfolge ist, werden die zusätzlichen Zeichen ignoriert. Zum Beispiel initialisiert die folgende Deklaration `code` als ein Drei-Elemente-Zeichenarray:  
  
```  
char code[3] = "abcd";  
```  
  
 Nur die ersten drei Zeichen des Initialisierers werden `code` zugewiesen. Das Zeichen `d` und das eine Zeichenfolge beendete NULL-Zeichen werden verworfen. Beachten Sie, dass dies eine nicht terminierte Zeichenfolge (d. h. eine Zeichenfolge ohne einen 0-Wert, um ihr Ende zu markieren) erstellt und eine Diagnosemeldung generiert, die diese Bedingung angibt.  
  
 Die Deklaration  
  
```  
char s[] = "abc", t[3] = "abc";  
```  
  
 ist identisch mit  
  
```  
char s[]  = {'a', 'b', 'c', '\0'},   
     t[3] = {'a', 'b', 'c' };  
```  
  
 Wenn die Zeichenfolge kürzer ist als die angegebene Arraygröße, werden die verbleibenden Elemente des Arrays mit 0 initialisiert.  
  
 **Microsoft-spezifisch**  
  
 In Microsoft C können Zeichenfolgenliterale bis 2048 Byte lang sein.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Initialisierung](../c-language/initialization.md)