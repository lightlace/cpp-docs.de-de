---
title: "Typkonvertierungen (C)"
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
  - "C"
helpviewer_keywords: 
  - "Konvertierungen, Typ"
  - "Konvertieren von Typen"
  - "Ganzzahlige Erweiterungen"
  - "Typumwandlungen, Bei der Ausführung"
  - "Typkonvertierung"
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Typkonvertierungen (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typkonvertierungen hängen vom angegebenen Operator und dem Typ des Operanden bzw. der Operatoren ab.  Typkonvertierungen werden in folgenden Fällen ausgeführt:  
  
-   Wenn ein Wert eines Typs einer Variablen eines anderen Typs zugewiesen wird oder wenn ein Operator den Typ des bzw. der Operanden vor der Durchführung des Vorgangs konvertiert.  
  
-   Wenn ein Wert eines Typs explizit in einen anderen Typ umgewandelt wird.  
  
-   Wenn ein Wert als Argument an eine Funktion übergeben wird oder wenn ein Typ von einer Funktion zurückgegeben wird.  
  
 Ein Zeichen, eine kurze ganze Zahl oder ein ganzzahliges Bitfeld \(alle entweder signiert oder unsigniert\) oder ein Objekt des Enumerationstyps können immer dann in einem Ausdruck verwendet werden, wenn die Verwendung einer Ganzzahl möglich ist.  Wenn ein `int`\-Wert alle Werte des ursprünglichen Typs darstellen kann, wird der Wert in `int` konvertiert. Andernfalls wird er in `unsigned int` konvertiert.  Dieser Vorgang wird als "ganzzahlige Erweiterung" bezeichnet. Ganzzahlige Erweiterungen behalten den Wert bei.  Das heißt, es ist gewährleistet, dass der Wert nach der Erweiterung derselbe ist wie vor der Erweiterung.  Weitere Informationen finden Sie unter [Übliche arithmetische Konvertierungen](../c-language/usual-arithmetic-conversions.md).  
  
## Siehe auch  
 [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md)