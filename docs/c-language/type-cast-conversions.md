---
title: "Typumwandlungskonvertierungen"
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
  - "Konvertierungen [C++], Typumwandlung"
  - "Datentypkonvertierung [C++], Typumwandlungskonvertierungen"
  - "Explizite Typkonvertierungen"
  - "Typumwandlungen"
  - "Typumwandlungen [C++], Informationen über die Typumwandlungskonvertierung"
  - "Typumwandlungskonvertierungen [C++]"
ms.assetid: 57ab5902-f12f-4326-a2f6-6282f1d4025a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Typumwandlungskonvertierungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Typumwandlungen verwenden, um Typen explizit zu konvertieren.  
  
 **Syntax**  
  
 *Umwandlungsausdruck*:  
 *unärer Ausdruck*  
  
 **\(**  *type\-name*  **\)**  *cast\-expression*  
  
 *type\-name*:  
 *specifier\-qualifier\-list abstract\-declarator*  opt  
  
 *type\-name* ist ein Typ, und *cast\-expression* ist ein Wert, der in diesen Typ konvertiert wird.  Ein Ausdruck mit einer Typumwandlung ist kein l\-Wert.  *cast\-expression* wird wie bei einer Zuweisung zu einer Variablen des Typs *type\-name* konvertiert.  Die Konvertierungsregeln für Zuweisungen \(unter [Zuweisungskonvertierungen](../c-language/assignment-conversions.md) beschrieben\) gelten auch für Typumwandlungen.  Die folgende Tabelle zeigt die Typen, die in jeden Typ umgewandelt werden können.  
  
### Gültige Typumwandlungen  
  
|Zieltypen|Mögliche Quellen|  
|---------------|----------------------|  
|Ganzzahlige Typen|Ein beliebiger ganzzahliger Typ oder Gleitkommatyp oder Zeiger auf ein Objekt|  
|Gleitkomma|Beliebiger arithmetischer Typ|  
|Ein Zeiger auf ein Objekt oder \(**void\***\)|Ein beliebiger ganzzahliger Typ \(**void \***\), ein Zeiger auf ein Objekt oder einen Funktionszeiger|  
|Funktionszeiger|Ein beliebiger ganzzahliger Typ, ein Zeiger auf ein Objekt oder einen Funktionszeiger|  
|Eine Struktur, Union oder ein Array|Keine|  
|void\-Typ|Beliebiger Typ|  
  
 Jeder Bezeichner kann in den `void`\-Typ umgewandelt werden.  Wenn jedoch der Typ, der in einem Typumwandlungsausdruck angegeben ist, nicht `void` ist, kann der Bezeichner, der in diesen Typ umgewandelt wird, kein `void`\-Ausdruck sein.  Jeder Ausdruck kann in `void` umgewandelt werden, aber ein Ausdruck vom Typ `void` kann nicht in einen anderen Typ umgewandelt werden.  Beispielsweise kann die Rückgabe einer Funktion mit dem Rückgabetyp `void` nicht in einen anderen Typ umgewandelt werden.  
  
 Beachten Sie, dass ein **void \***\-Ausdruck einen Typzeiger auf `void`, nicht den Typ `void` aufweist.  Wenn ein Objekt in einen `void`\-Typ umgewandelt wird, kann der resultierende Ausdruck keinem Element zugewiesen werden.  Ebenso ist ein Typumwandlungsobjekt kein zulässiger l\-Wert, sodass keine Zuweisung zu einem Typumwandlungsobjekt durchgeführt werden kann.  
  
 **Microsoft\-spezifisch**  
  
 Eine Typumwandlung kann ein l\-Wert\-Ausdruck sein, solange die Größe des Bezeichners sich nicht ändert.  Weitere Informationen zu l\-Wert\-Ausdrücken finden Sie unter [L\-Wert\-und R\-Wert\-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).  
  
 **END Microsoft\-spezifisch**  
  
 Sie können einen Ausdruck durch eine Umwandlung in den Typ `void` konvertieren, der resultierende Ausdruck kann jedoch nur verwendet werden, wenn kein Wert erforderlich ist.  Ein Objektzeiger, der in **void \*** und zurück in den ursprünglichen Typ konvertiert wird, kehrt zum ursprünglichen Wert zurück.  
  
## Siehe auch  
 [Typkonvertierungen](../c-language/type-conversions-c.md)