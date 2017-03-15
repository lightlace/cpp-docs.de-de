---
title: "Typqualifizierer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const-Schlüsselwort [C]"
  - "Speicher, Zugriff mithilfe von volatile"
  - "Qualifizierer für Typen"
  - "Typqualifizierer"
  - "volatile-Schlüsselwort [C]"
  - "volatile-Schlüsselwort [C], Typqualifizierer"
  - "volatile-Schlüsselwort [C], Typspezifizierer"
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Typqualifizierer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typqualifizierer verleihen einem Bezeichner eine von zwei Eigenschaften.  Der Typqualifizierer **const** deklariert ein Objekt als nicht änderbar.  Der Typqualifizierer `volatile` deklariert ein Element, bei dem eine Wertänderung von außerhalb des Programms, in dem es vorhanden ist, zulässig ist \(z. B. durch einen gleichzeitig ausgeführten Thread\).  
  
 Die beiden Typqualifizierer **const** und `volatile` können in einer Deklaration nur einmal verwendet werden.  Typqualifizierer lassen sich mit einem beliebigen Typspezifizierer verwenden, jedoch können sie in einer Deklaration mit mehreren Elementen nicht hinter dem ersten Komma stehen.  Beispielsweise sind die folgenden Deklarationen zulässig:  
  
```  
typedef volatile int VI;  
const int ci;  
```  
  
 Diese Deklarationen sind unzulässig:  
  
```  
typedef int *i, volatile *vi;  
float f, const cf;     
```  
  
 Typqualifizierer sind nur wichtig, wenn auf Bezeichner als L\-Werte in Ausdrücken zugegriffen wird.  Weitere Informationen über L\-Werte und Ausdrücke finden Sie unter [L\-Wert\- und R\-Wert\-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).  
  
## Syntax  
 *type\-qualifier*:  
 **constvolatile**  
  
 Folgende sind zulässige **const**\- und `volatile`\-Deklarationen:  
  
```  
int const *p_ci;       /* Pointer to constant int */  
int const (*p_ci);     /* Pointer to constant int */  
int *const cp_i;       /* Constant pointer to int */  
int (*const cp_i);     /* Constant pointer to int */  
int volatile vint;     /* Volatile integer        */  
```  
  
 Wenn die Spezifikation eines Arraytyps Typqualifizierer enthält, wird das Element qualifiziert, nicht der Arraytyp.  Enthält die Spezifikation des Funktionstyps Qualifizierer, ist das Verhalten undefiniert.  Weder `volatile` noch **const** wirken sich auf den Wertebereich oder arithmetische Eigenschaften des Objekts aus.  
  
 Diese Liste beschreibt die Verwendung von **const** und `volatile`.  
  
-   Das **const**\-Schlüsselwort kann verwendet werden, um jeden grundlegenden oder aggregierten Typ, einen Zeiger auf ein Objekt beliebigen Typs oder ein `typedef` zu ändern.  Wenn ein Element nur mit dem **const**\-Typqualifizierer deklariert ist, lautet der Typ **const int**.  Eine **const**\-Variable kann initialisiert oder in einem schreibgeschützten Speicherbereich platziert werden.  Das **const**\-Schlüsselwort ist gut geeignet, um Zeiger auf **const** zu deklarieren, da die Funktion den Zeiger keinesfalls ändern darf.  
  
-   Der Compiler nimmt an, dass im Programm zu jedem Zeitpunkt der Zugriff auf eine `volatile`\-Variable erfolgen kann, und zwar durch einen unbekannten Prozess, der den Wert verwendet oder ändert.  Daher muss – unabhängig von den in der Befehlszeile angegebenen Optimierungen – der Code für jede Zuordnung oder für jeden Verweis auf eine `volatile`\-Variable generiert werden, auch wenn er keine Auswirkung hat.  
  
     Bei alleiniger Verwendung von `volatile` wird `int` angenommen.  Der Typspezifizierer `volatile` kann verwendet werden, um zuverlässigen Zugriff auf spezielle Speicheradressen zu ermöglichen.  Verwenden Sie `volatile` mit Datenobjekten, bei denen der Zugriff oder eine Änderung durch Signalhandler, durch gleichzeitig ausgeführte Programme oder durch spezielle Hardware \(wie z. B. im Speicher abgebildete E\/A\-Steuerungsregister\) erfolgen kann.  Sie können eine Variable für ihre Verwendungszeit als `volatile` deklarieren oder einen einzelnen Verweis in `volatile` umwandeln.  
  
-   Ein Element kann sowohl **const** als auch `volatile` sein. Dann ist eine Änderung des Elements durch das eigene Programm nicht zulässig, eine Änderung durch einen asynchronen Prozess ist jedoch möglich.  
  
## Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)