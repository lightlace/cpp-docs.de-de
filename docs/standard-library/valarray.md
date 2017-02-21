---
title: "&lt;valarray&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<valarray>"
  - "valarray/std::<valarray>"
  - "std::<valarray>"
  - "<valarray>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray-Header"
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;valarray&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die valarray\-Vorlagenklasse sowie zahlreiche unterstützende Vorlagenklassen und Funktionen.  
  
## Syntax  
  
```  
  
#include <valarray>  
  
```  
  
## Hinweise  
 Diese Vorlagenklassen und Funktionen haben im Interesse einer verbesserten Leistung ungewöhnliche Freiheiten.  Insbesondere kann jede Funktion, die den Typ **valarray\<**T1**\>** zurückgibt, ein Objekt eines anderen Typs T2 zurückgeben.  In diesem Fall muss jede Funktion, die mindestens ein Argument des Typs **valarray\<**T2**\>** akzeptiert, Überladungen haben, die beliebige Kombinationen dieser Argumente akzeptieren, wobei jedes durch ein Argument des Typs T2 ersetzt ist.  
  
### Funktionen  
  
|||  
|-|-|  
|[abs](../Topic/abs%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem absoluten Wert der Elemente des valarray\-Eingabeobjekts sind.|  
|[acos](../Topic/acos%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Arkuskosinus der Elemente des valarray\-Eingabeobjekts sind.|  
|[asin](../Topic/asin%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Arkussinus der Elemente des valarray\-Eingabeobjekts sind.|  
|[atan](../Topic/atan%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Hauptwert des Arkustangens der Elemente des valarray\-Eingabeobjekts sind.|  
|[atan2](../Topic/atan2%20\(%3Cvalarray%3E\).md)|Gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Arkustangens der kartesischen Komponenten sind, die durch eine Kombination aus Konstanten und Elementen von valarray\-Objekten angegeben sind.|  
|[cos](../Topic/cos%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Kosinus der Elemente des valarray\-Eingabeobjekts sind.|  
|[cosh](../Topic/cosh%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Kosinus Hyperbolicus der Elemente des valarray\-Eingabeobjekts sind.|  
|[exp](../Topic/exp%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich der natürlichen Exponentialfunktion der Elemente des valarray\-Eingabeobjekts sind.|  
|[log](../Topic/log%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem natürlichen Logarithmus der Elemente des valarray\-Eingabeobjekts sind.|  
|[log10](../Topic/log10%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Logarithmus zur Basis 10 \(dekadischer Logarithmus\) der Elemente des valarray\-Eingabeobjekts sind.|  
|[pow](../Topic/pow%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente von valarray\-Eingabeobjekten und Konstanten und gibt ein valarray\-Objekt zurück, dessen Elemente gleich einer mit einem Exponenten potenzierten Basis sind, wobei Basis und Exponent jeweils durch die Elemente eines valarray\-Eingabeobjekts oder eine Konstante angegeben sind.|  
|[sin](../Topic/sin%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Sinus der Elemente des valarray\-Eingabeobjekts sind.|  
|[sinh](../Topic/sinh%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Sinus Hyperbolicus der Elemente des valarray\-Eingabeobjekts sind.|  
|[sqrt](../Topic/sqrt%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich der Quadratwurzel der Elemente des valarray\-Eingabeobjekts sind.|  
|[swap](../Topic/swap%20\(%3Cvalarray%3E\).md)||  
|[tan](../Topic/tan%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Tangens der Elemente des valarray\-Eingabeobjekts sind.|  
|[tanh](../Topic/tanh%20\(%3Cvalarray%3E\).md)|Verarbeitet die Elemente eines valarray\-Eingabeobjekts und gibt ein valarray\-Objekt zurück, dessen Elemente gleich dem Tangens Hyperbolicus der Elemente des valarray\-Eingabeobjekts sind.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/operator!=%20\(%3Cvalarray%3E\).md)|Überprüft, ob die entsprechenden Elemente von zwei gleich großen valarray\-Objekten ungleich sind oder ob alle Elemente eines valarray\-Objekts entsprechend einem angegebenen Wert des Elementtyps des valarray\-Objekts ungleich sind.|  
|[operator%](../Topic/operator%25.md)|Ruft den Rest der Division der entsprechenden Elemente von zwei gleich großen valarray\-Objekten oder der Division eines valarray\-Objekts durch einen angegebenen Wert des valarray Elementtyps oder der Division eines angegebenen Werts durch ein valarray\-Objekt ab.|  
|[Operator&](../Topic/operator&.md)|Ruft das bitweise **AND** zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps ab.|  
|[operator&&](../Topic/operator&&.md)|Ruft das logische **AND** zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps des valarray\-Objekts ab.|  
|[Operator \>](../Topic/operator%3E%20\(%3Cvalarray%3E\).md)|Überprüft, ob die Elemente eines valarray\-Objekts größer sind als die Elemente eines gleich großen valarray\-Objekts oder ob alle Elemente eines valarray\-Objekts größer oder kleiner sind als ein angegebener Wert des Elementtyps des valarray\-Objekts.|  
|[Operator \>\=](../Topic/operator%3E=%20\(%3Cvalarray%3E\).md)|Überprüft, ob die Elemente eines valarray\-Objekts größer gleich den Elementen eines gleich großen valarray\-Objekts oder ob alle Elemente eines valarray\-Objekts größer gleich oder kleiner gleich einem angegebenen Wert sind.|  
|[Operator \>\>](../Topic/operator%3E%3E%20\(%3Cvalarray%3E\).md)|Verschiebt die Bits für jedes Element eines valarray\-Objekts um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites valarray\-Objekt angegeben ist, nach rechts.|  
|[Operator \<](../Topic/operator%3C%20\(%3Cvalarray%3E\).md)|Überprüft, ob die Elemente eines valarray\-Objekts kleiner sind als die Elemente eines gleich großen valarray\-Objekts oder ob alle Elemente eines valarray\-Objekts größer oder kleiner sind als ein angegebener Wert.|  
|[Operator \<\=](../Topic/operator%3C=%20\(%3Cvalarray%3E\).md)|Überprüft, ob die Elemente eines valarray\-Objekts kleiner gleich den Elementen eines gleich großen valarray\-Objekts oder ob alle Elemente eines valarray\-Objekts größer gleich oder kleiner gleich einem angegebenen Wert sind.|  
|[Operator \<\<](../Topic/operator%3C%3C%20\(%3Cvalarray%3E\).md)|Verschiebt die Bits für jedes Element eines valarray\-Objekts um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites valarray\-Objekt angegeben ist, nach links.|  
|[operator\*](../Topic/operator*%20\(%3Cvalarray%3E\).md)|Ruft das elementweise Produkt zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps des valarray\-Objekts ab.|  
|[operator\+](../Topic/operator+%20\(%3Cvalarray%3E\).md)|Ruft die elementweise Summe zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps des valarray\-Objekts ab.|  
|[operator\-](../Topic/operator-%20\(%3Cvalarray%3E\)2.md)|Ruft die elementweise Differenz zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps des valarray\-Objekts ab.|  
|[operator\/](../Topic/operator-%20\(%3Cvalarray%3E\)1.md)|Ruft den elementweise Quotienten zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps des valarray\-Objekts ab.|  
|[operator\=\=](../Topic/operator==%20\(%3Cvalarray%3E\).md)|Überprüft, ob die entsprechenden Elemente von zwei gleich großen valarray\-Objekten gleich sind oder ob alle Elemente eines valarray\-Objekts entsprechend einem angegebenen Wert des Elementtyps des valarray\-Objekts gleich sind.|  
|[operator^](../Topic/operator%5E.md)|Ruft das bitweise exklusive `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps ab.|  
|[operator&#124;](../Topic/operator%7C.md)|Ruft das bitweise `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps ab.|  
|[operator&#124;&#124;](../Topic/operator%7C%7C.md)|Ruft das logische `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray\-Objekten oder zwischen einem valarray\-Objekt und einem angegebenen Wert des Elementtyps des valarray\-Objekts ab.|  
  
### Klassen  
  
|||  
|-|-|  
|[gslice\-Klasse](../standard-library/gslice-class.md)|Eine Hilfsklasse der valarray\-Klasse, die zum Definieren von mehrdimensionalen Segmenten eines valarray\-Objekts verwendet wird.|  
|[gslice\_array\-Klasse](../standard-library/gslice-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die allgemeine slice\-Objekte \(Segmente\) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das allgemeine Segment eines valarray\-Objekts definiert sind.|  
|[indirect\_array\-Klasse](../standard-library/indirect-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die allgemeine Objekte, die Teilmengen von valarray\-Objekten sind, unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch Angeben einer Teilmenge von Indizes eines übergeordneten valarray\-Objekts definiert sind.|  
|[mask\_array\-Klasse](../standard-library/mask-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die Objekte, die Teilmengen von übergeordneten valarray\-Objekten und mit einem booleschen Ausdruck angegeben sind, dadurch unterstützt, dass sie Vorgänge zwischen den Teilmengenarrays bereitstellt.|  
|[slice\-Klasse](../standard-library/slice-class.md)|Eine Hilfsklasse für die valarray\-Klasse, die dazu verwendet wird, eindimensionale vektorähnliche Teilmengen eines valarray\-Objekts zu definieren.|  
|[slice\_array\-Klasse](../standard-library/slice-array-class.md)|Eine interne zusätzliche Vorlagenklasse, die slice\-Objekte \(Segmente\) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das Segment eines valarray\-Objekts definiert sind.|  
|[valarray\-Klasse](../standard-library/valarray-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das eine Sequenz von Elementen des Typs **Type** steuert, die als Array gespeichert sind. Diese Klasse ist für das Ausführen von schnellen mathematischen Operationen vorgesehen und für rechenbetonte Leistung optimiert.|  
  
### Spezialisierungen  
  
|||  
|-|-|  
|[valarray\<bool\>\-Klasse](../standard-library/valarray-bool-class.md)|Eine spezielle Version der Vorlagenklasse valarray\<**Type**\> für Elemente des Typs `bool`.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)