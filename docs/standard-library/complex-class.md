---
title: "complex-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "complex"
  - "std::complex"
  - "std.complex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex-Klasse"
  - "Komplexe Zahlen"
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# complex-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das zwei Objekte Typ **Typ** speichert, eines, das den reellen eine komplexe Zahl darstellt und einen, der den imaginären Teil darstellt.  
  
## Syntax  
  
```  
  
   template<class   
   Type  
   >  
class complex  
```  
  
## Hinweise  
 Ein Objekt der Klasse **Typ**:  
  
-   Hat einen öffentlichen Standardkonstruktor, einen Destruktor, einen Kopierkonstruktor und einen Zuweisungsoperator mit konventionellem Verhalten.  
  
-   Die ganze oder Gleitkommawerte oder wandeln zu solchen Werten mit konventionellem Verhalten zugewiesen werden.  
  
-   Definiert die arithmetischen Operatoren sowie mathematische Funktionen nach Bedarf für die mit Gleitkommatypen konventionellem Verhalten definiert werden.  
  
 Insbesondere keine vorhanden sind kleine Unterschiede Kleinschreibung zwischen der Kopienkonstruktion und Standardkonstruktion, die von der Zuweisung folgen.  Keine der Operationen auf Objekte der Klasse **Typ** lösen möglicherweise Ausnahmen aus.  
  
 Explizite Spezialisierungen des Vorlagenklassenkomplexes sind für die drei Gleitkommatypen.  In dieser Implementierung ist ein Wert eines anderen Typs **Typ**\-Typ von **double** für tatsächliche Berechnungen, wenn das **double** Ergebnis zurück zum gespeicherten Objekt zugewiesen ist, der Typ **Typ**`.`  
  
### Konstruktoren  
  
|||  
|-|-|  
|[Komplexe](../Topic/complex::complex.md)|Erstellt eine komplexe Zahl mit angegebenem Videolernprogrammen und imaginären Teile oder als Kopie einer anderen komplexer Zahl.|  
  
### Typedefs  
  
|||  
|-|-|  
|[value\_type](../Topic/complex::value_type.md)|Ein Typ, der dem Datentyp darstellt, der verwendet wird, um das die tatsächliche und imaginären Teile einer zu komplexen Zahl darstellen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[imag](../Topic/complex::imag.md)|Extrahiert die imaginäre Komponente einer komplexen Zahl.|  
|[real](../Topic/complex::real.md)|Extrahiert die echte Komponente einer komplexen Zahl.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\*\=](../Topic/complex::operator*=.md)|Multipliziert eine Zielkomplexe Zahl mit einem Faktor, der oder möglicherweise ist der gleiche Typ komplex ist, wie die echten imaginären und die Teile der komplexen Zahl sind.|  
|[Operator\+\=](../Topic/complex::operator+=.md)|Fügt einer Zeilennummer einer Zielkomplexen Ganzzahl\- hinzu, in der die Zahl, die hinzugefügt wird, oder möglicherweise denselben Typ komplex ist, wie die echten imaginären und die Teile der komplexen Zahl sind, an den er hinzugefügt wird.|  
|[Operator\-\=](../Topic/complex::operator-=1.md)|Subtrahiert eine Zahl von einer Zielkomplexen Zahl, in der die Zahl, die subtrahiert wird, z oder von demselben Typ komplex ist, wie die echten imaginären und die Teile der komplexen Zahl sind, an den er hinzugefügt wird.|  
|[operator\/\=](../Topic/complex::operator-=2.md)|Dividiert eine Zielkomplexe Zahl durch einen Divisor, der oder möglicherweise ist der gleiche Typ komplex ist, wie die echten imaginären und die Teile der komplexen Zahl sind.|  
|[operator\=](../Topic/complex::operator=.md)|Weist eine Zahl in eine Zielkomplexen Zahl zu, in der die Zahl, die zugewiesen wird, z oder von demselben Typ komplex ist, wie die echten imaginären und die Teile der komplexen Zahl sind, zu der sie zugewiesen wird.|  
  
## Anforderungen  
 **Header**: \<komplex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [complex Members](assetId:///d5c4466c-43a0-4817-aca1-9a5d492dae28)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)