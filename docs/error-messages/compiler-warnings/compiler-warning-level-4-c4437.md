---
title: "Compilerwarnung (Stufe 4) C4437"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4437
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Operator dynamic\_cast von der virtuellen Basisklasse "Klasse1" zu "Klasse2" kann in mehreren Kontexten fehlgeschlagenen kompilieren mit \/vd2 oder definieren "Klasse2" mit \#pragma vtordisp wirksam \(2\)  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Der Compiler hat einen Vorgang `dynamic_cast` mit den folgenden Eigenschaften gefunden.  
  
-   Die Umwandlung wird über einen Basisklassenzeiger einem Zeiger der abgeleiteten Klasse.  
  
-   Die abgeleitete Klasse erbt virtuell die Basisklasse.  
  
-   Die abgeleitete Klasse hat kein `vtordisp` \- Feld für die virtuelle Basisklasse.  
  
-   Die Umwandlung wird nicht in einem Konstruktor oder einem Destruktor der abgeleiteten Klasse oder in irgendeiner Klasse gefunden, die weiter von der abgeleiteten Klasse erbt \(; andernfalls wird C4436 Compilerwarnung ausgegeben\).  
  
 Die Warnung gibt an, dass `dynamic_cast` ggf. nicht ordnungsgemäß ausgeführt, wenn es auf einem teilweis\-erstellten Objekt funktioniert.  Diese Situation tritt auf, wenn die einschließende Funktion von einem Konstruktor oder einem Destruktor einer Klasse aufgerufen wird, die die abgeleitete Klasse erbt, die in der Warnung ".  Wenn die abgeleitete Klasse, die in der Warnung ", nie eine weitere abgeleitete oder die einschließende Funktion wird aufgerufen nicht während der Objekterstellung oder der Zerstörung ist, kann die Warnung ignoriert werden.  
  
## Beispiel  
 Das folgende Beispiel generiert C4437 und zeigt das Codegenerierungsproblem, das aus dem fehlenden `vtordisp` Feld entsteht.  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
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
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
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
 [Compilerwarnung \(Stufe 1\) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)