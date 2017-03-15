---
title: "Compilerwarnung (Stufe 1) C4436 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# Compilerwarnung (Stufe 1) C4436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Operator dynamic\_cast von der virtuellen Basisklasse "Klasse1" zu "Klasse2" im Konstruktor oder Destruktor kann mit teilweis\-erstelltem Objekt fehlgeschlagenen kompilieren mit \/vd2 oder definieren "Klasse2" mit \#pragma vtordisp wirksam \(2\)  
  
 Der Compiler hat einen Vorgang `dynamic_cast` mit den folgenden Eigenschaften gefunden.  
  
-   Die Umwandlung wird über einen Basisklassenzeiger einem Zeiger der abgeleiteten Klasse.  
  
-   Die abgeleitete Klasse erbt virtuell die Basisklasse.  
  
-   Die abgeleitete Klasse hat kein `vtordisp` \- Feld für die virtuelle Basisklasse.  
  
-   Die Umwandlung wird in einem Konstruktor oder einem Destruktor der abgeleiteten Klasse oder in irgendeiner Klasse gefunden, die weiter von der abgeleiteten Klasse erbt.  
  
 Die Warnung angibt `dynamic_cast` führt möglicherweise nicht ordnungsgemäß ausgewertet, auf einem teilweis\-erstellten Objekt funktioniert.  Das geschieht, wenn der abgeleitete Konstruktor\/der Destruktor auf ein Unterobjekt einige nachfolgend abgeleiteten Objekts.  Wenn die abgeleitete Klasse, die in der Warnung ", nie eine weitere abgeleitete ist, kann die Warnung ignoriert werden.  
  
## Beispiel  
 Das folgende Beispiel generiert C4436 und zeigt das Codegenerierungsproblem, das aus dem fehlenden `vtordisp` Feld entsteht.  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## Siehe auch  
 [dynamic\_cast\-Operator](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [Compilerwarnung \(Stufe 4\) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)