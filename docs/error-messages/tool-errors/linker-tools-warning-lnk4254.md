---
title: "Linkertoolwarnung LNK4254 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4254"
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Linkertoolwarnung LNK4254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abschnitt 'Abschnitt1' \(Offset\) wurde mit 'Abschnitt2' \(Offset\) mit unterschiedlichen Attributen zusammengeführt  
  
 Der Inhalt eines Abschnitts wurde mit dem eines anderen zusammengeführt, die Attribute der zwei Abschnitte sind jedoch nicht identisch.  Das Programm gibt möglicherweise unerwartete Ergebnisse aus.  Zum Beispiel können sich Daten, die schreibgeschützt sein sollten, nun im schreibbaren Abschnitt befinden.  
  
 Um LNK4254 zu beheben, ändern oder entfernen Sie die Anforderung zum Zusammenführen.  
  
 Bei x86\-Computern und Windows CE\-Plattformen \(ARM, MIPS, SH4 und Thumb\) mit Visual C\+\+ ist der .CRT\-Abschnitt ab jetzt schreibgeschützt.  Wenn der Code auf dem vorherigen Verhalten \(.CRT\-Abschnitte mit Lese\-\/Schreibzugriff\) beruht, kann dies zu unerwartetem Verhalten führen.  
  
 Weitere Informationen finden Sie unter  
  
-   [\/MERGE \(Abschnitte kombinieren\)](../../build/reference/merge-combine-sections.md)  
  
-   [Kommentar](../../preprocessor/comment-c-cpp.md)  
  
## Beispiel  
 Im folgenden Beispiel wird LNK4254 generiert.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```