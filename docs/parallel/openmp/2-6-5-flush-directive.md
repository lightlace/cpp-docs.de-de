---
title: "2.6.5 flush Directive"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.5 flush Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **leer**\-Direktive, ob explizit oder implizit, geben einen „threadübergreifenden“ Sequenzpunkt an, in dem die Implementierung erforderlich ist, um sicherzustellen, dass alle Threads in einem Team eine konsistente Ansicht von bestimmten Objekten \(unten angegeben\) im Arbeitsspeicher verfügen.  Dies bedeutet, dass vorherige Auswertungen von Ausdrücken, die diese Objekte verweisen, vollständige und nachfolgende Auswertungen sind noch nicht gestartet wurden.  Beispielsweise müssen Compiler die Werte der Objekte aus Register Arbeitsspeicher und Hardware wiederherstellen, muss möglicherweise Pufferspeicher zum Arbeitsspeicher löscht und die Werte der Objekte aus dem Arbeitsspeicher.  
  
 Die Syntax der **leer**\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp flush [(variable-list)]  new-line  
```  
  
 Wenn die Objekte, die eine Synchronisierung erfordern, durch alle Variablen festgelegt werden können, können diese Variablen in der *Liste Variablen*optionalen angegeben werden.  Ist ein Zeiger auf die *Variable Liste*enthalten ist, wird der Zeiger auf das Objekt selbst, nicht entleert, die der Zeiger verweist.  
  
 **leer**\-Direktive ohne eine *Variable Liste* synchronisieren alle freigegebenen Objekte außer nicht zugänglich Objekte mit automatischer Speicherung dauer.  \(Dies kann mehr als **leer** Mehraufwand mit einer *Variablen Liste*zu haben.\) **leer**\-Direktive ohne eine *Variable Liste* werden für die folgenden Direktiven Folgendes bedeutet:  
  
-   `barrier`  
  
-   Am Eintrag und Beenden von **Kritisch**  
  
-   Am Eintrag und Beenden von `ordered`  
  
-   Am Eintrag und Beenden von **Ähnlichkeit**  
  
-   Verlassen Sie an der **nach**  
  
-   Verlassen Sie an der **Abschnitte**  
  
-   Verlassen Sie an der **Einfach**  
  
-   Am Eintrag und Beenden von **für Ähnlichkeit**  
  
-   Am Eintrag und Beenden von **parallele Abschnitte**  
  
 Die Direktive wird nicht, wenn eine `nowait`\-Klausel vorhanden ist.  Es sollte beachtet werden, dass die **leer**\-Direktive nicht für alle der folgenden Elemente gedacht sind:  
  
-   Am Eintrag **nach**  
  
-   Am Eintrag oder Verlassen **Master**  
  
-   Am Eintrag **Abschnitte**  
  
-   Am Eintrag **Einfach**  
  
 Ein Verweis, der den Wert eines Objekts mit einem flüchtig\-qualifizierten Typ zugegriffen wird, verhält sich, als ob es **leer** gab, das dieses Objekt am vorherigen Sequenzpunkt angibt richtungweisend ist.  Ein Verweis, der den Wert eines Objekts mit einem flüchtig\-qualifizierten Typ ändert, verhält sich, als ob es **leer** gab, das dieses Objekt am nächsten Sequenzpunkt angibt richtungweisend ist.  
  
 Da die **leer**\-Direktive Wechselstrom\-Sprachanweisung nicht als Teil der Syntax haben, jedoch einige Einschränkungen bezüglich ihrer Platzierung innerhalb eines Programms vorhanden ist.  Weitere Informationen finden Sie unter [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) für die formale Grammatik.  Das folgende Beispiel verdeutlicht diese Einschränkungen.  
  
```  
/* ERROR - The flush directive cannot be the immediate  
*          substatement of an if statement.  
*/  
if (x!=0)  
   #pragma omp flush (x)  
...  
  
/* OK - The flush directive is enclosed in a  
*      compound statement  
*/  
if (x!=0) {  
   #pragma omp flush (x)  
}  
```  
  
 Einschränkungen für **leer**\-Direktive lauten wie folgt:  
  
-   Eine Variable, die in **leer**\-Direktive angegeben ist, darf einen Verweistyp enthalten.