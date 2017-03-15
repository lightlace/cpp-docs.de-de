---
title: "Tempor&#228;re Objekte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Objekte [C++], Temporär"
  - "Temporäre Objekte"
ms.assetid: 4c8cec02-391e-4225-9bc6-06d150201412
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Tempor&#228;re Objekte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einigen Fällen muss der Compiler temporäre Objekte erstellen.  Diese temporären Objekte können aus folgenden Gründen erstellt werden:  
  
-   Um einen `const`\-Verweis mit dem Initialisierer eines anderen Typs als dem zugrunde liegenden des initialisierten Verweises zu initialisieren.  
  
-   Um den Rückgabewert einer Funktion zu speichern, die einen benutzerdefinierten Typ zurückgibt.  Diese temporären Objekte werden nur erstellt, wenn das Programm den Rückgabewert nicht in ein Objekt kopiert.  Beispiel:  
  
    ```  
    UDT Func1();    //  Declare a function that returns a user-defined  
                    //   type.  
  
    ...  
  
    Func1();        //  Call Func1, but discard return value.  
                    //  A temporary object is created to store the return  
                    //   value.  
    ```  
  
     Da der Rückgabewert nicht in ein anderes Objekt kopiert wird, wird ein temporäres Objekt erstellt.  Ein allgemeinerer Fall, in dem temporäre Dateien erstellt werden, ist während der Auswertung eines Ausdrucks, wobei überladene Operator\-Funktionen aufgerufen werden müssen.  Diese überladenen Operatorfunktionen geben einen benutzerdefinierten Typ zurück, der häufig nicht in ein anderes Objekt kopiert wird.  
  
     Betrachten Sie den Ausdruck `ComplexResult = Complex1 + Complex2 + Complex3`.  Der Ausdruck `Complex1 + Complex2` wird ausgewertet und das Ergebnis wird in einem temporären Objekt gespeichert.  Anschließend wird der Ausdruck *temporary* `+ Complex3` ausgewertet, und das Ergebnis nach `ComplexResult` kopiert \(wobei angenommen wird, dass der Zuweisungsoperator nicht überladen ist\).  
  
-   Um das Ergebnis einer Typumwandlung in einem benutzerdefinierten Typ zu speichern.  Wenn ein Objekt eines angegebenen Typs explizit in einen benutzerdefinierten Typ konvertiert wird, wird das neue Objekt als temporäres Objekt erstellt.  
  
 Temporäre Objekte haben eine Lebensdauer, die sich nach dem Zeitpunkt der Erstellung und Zerstörung richtet.  Jeder Ausdruck, der mehr als einer temporäres Objekt erstellt, zerstört sie letztendlich in umgekehrter Reihenfolge, in der sie erstellt wurden.  In der folgenden Tabelle sind die Punkte dargestellt, an denen Zerstörung auftritt.  
  
### Zerstörungspunkte für temporäre Objekte  
  
|Grund "temporär" erstellt|Zerstörungspunkt|  
|-------------------------------|----------------------|  
|Ergebnis der Ausdrucksauswertung|Alle temporären Dateien, die als Ergebnis der Ausdrucksauswertung erstellt werden, werden am Ende der Ausdrucksanweisung \(d. h. das Semikolon\) oder am Ende der steuernden Ausdrücke für die Anweisungen `for`, `if`, `while`, `do` und `switch` zerstört.|  
|Initialisieren von `const`\-Verweisen|Wenn ein Initialisierer kein l\-Wert desselben Typs wie der initialisierte Verweis ist, wird ein temporäres Objekt des zugrunde liegenden Objekttyps erstellt und mit dem Initialisierungsausdruck initialisiert.  Dieses temporäre Objekt wird zerstört, sobald das Verweisobjekt, an das es gebunden ist, zerstört wurde.|  
  
## Siehe auch  
 [Spezielle Memberfunktionen](../misc/special-member-functions-cpp.md)