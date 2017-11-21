---
title: Spezielle Memberfunktionen | Microsoft Docs
ms.custom: 
ms.date: 12/06/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a254b89d7d3007f639c961371b9f1560b4c5f406
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="special-member-functions"></a>Spezielle Memberfunktionen  
  
Die *spezielle Memberfunktionen* -Klasse (oder Struktur) Memberfunktionen, die in bestimmten Fällen generiert der Compiler automatisch für Sie sind. Diese Funktionen befinden sich die [Standardkonstruktor](constructors-cpp.md#default_constructors), die [Destruktor](destructors-cpp.md), [Kopierkonstruktor und der Kopierzuweisungsoperator](copy-constructors-and-copy-assignment-operators-cpp.md), und die [bewegungskonstruktor und bewegungszuweisungsoperator](move-constructors-and-move-assignment-operators-cpp.md). Wenn eine oder mehrere der speziellen Memberfunktionen nicht in die Klasse definieren, klicken Sie dann der Compiler möglicherweise implizit deklarieren und definieren die Funktionen, die verwendet werden. Die vom Compiler generierte Implementierungen heißen die *Standard* spezielle Memberfunktionen. Der Compiler löst keine Funktionen, wenn sie nicht benötigt werden.  
  
Sie können eine Standard-spezielle Memberfunktion explizit deklarieren, indem die `= default` Schlüsselwort. Dies bewirkt, dass den Compiler zum Definieren der Funktion nur im Bedarfsfall, auf die gleiche Weise wie wenn die Funktion nicht deklariert wurde. 

In einigen Fällen kann der Compiler generieren *gelöscht* spezielle Memberfunktionen, die nicht definiert ist und daher nicht aufgerufen werden kann. Dies kann in Fällen vorkommen, in dem ein Aufruf an eine bestimmte spezielle Memberfunktion für eine Klasse, andere Eigenschaften der Klasse sinnvoll nicht. Um die automatische Generierung von eine spezielle Memberfunktion explizit zu verhindern, deklarieren Sie es als gelöscht mithilfe der `= delete` Schlüsselwort.  
  
Der Compiler generiert eine *Standardkonstruktor*, einen Konstruktor, der keine Argumente akzeptiert nur, wenn Sie einem anderen Konstruktor nicht deklariert haben. Wenn Sie nur einen Konstruktor, der Parameter annimmt deklariert haben, Compiler Code, der versucht, einen Standardkonstruktor Aufrufen der eine Fehlermeldung zu erzeugen. Der vom Compiler generierter Standardkonstruktor führt einfache member-wise [standardinitialisierung](initializers.md#default_initialization) des Objekts. Standardinitialisierung bewirkt, dass alle Membervariablen in einem unbestimmten Zustand.  
  
Der Standarddestruktor führt elementweise Zerstörung des Objekts. Es ist virtuell, nur dann, wenn ein Basisklassendestruktor virtuell ist.  
  
Die Standard-Kopie und verschiebungskonstruktion und Zuweisungsvorgängen ausführen elementweise Bitmuster kopiert oder verschiebt nicht statischen Datenmember. Verschieben Sie, dass Vorgänge nur generiert werden, wenn keine Destruktor oder Verschiebe-oder Kopiervorgänge deklariert werden. Ein Standardkopierkonstruktor wird nur generiert, wenn kein Kopierkonstruktor deklariert wird. Er wird implizit gelöscht, wenn ein Verschiebevorgang deklariert wird. Ein Standard-Kopierzuweisungsoperator wird nur generiert, wenn kein Kopierzuweisungsoperator explizit deklariert wird. Er wird implizit gelöscht, wenn ein Verschiebevorgang deklariert wird.  
  
## <a name="see-also"></a>Siehe auch  
[C++-Programmiersprachenreferenz](cpp-language-reference.md)  



 
