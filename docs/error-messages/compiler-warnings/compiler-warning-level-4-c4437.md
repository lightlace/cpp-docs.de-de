---
title: Compilerwarnung (Stufe 4) C4437 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a50534ca7e25b18d32d37a9120e478f78ea56daf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4437"></a>Compilerwarnung (Stufe 4) C4437
Dynamic_cast von virtueller Basis 'class1' zu 'class2' konnte in bestimmten Kontexten Kompilieren mit/vd2 fehl oder definieren wirksam "Klasse2" mit der #pragma-vtordisp(2)  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Der Compiler hat eine `dynamic_cast` Operation mit den folgenden Merkmalen.  
  
-   Die Umwandlung ist von einem Zeiger Basisklasse in einer abgeleiteten Klasse Zeiger.  
  
-   Die abgeleitete Klasse erbt praktisch die Basisklasse.  
  
-   Die abgeleitete Klasse verfügt nicht über eine `vtordisp` Feld für die virtuelle Basisklasse.  
  
-   Die Umwandlung in einen Konstruktor oder Destruktor der abgeleiteten Klasse nicht gefunden wird, oder einige Klasse was erbt von der abgeleiteten Klasse (hingegen compilerwarnung, die C4436 ausgegeben werden).  
  
 Die Warnung gibt an, dass die `dynamic_cast` möglicherweise nicht ordnungsgemäß ausgeführt werden, wenn sie für eine teilweise konstruiert Objekt ausgeführt wird.  Diese Situation tritt auf, wenn die einschließende Funktion aufgerufen wird, von einem Konstruktor oder Destruktor einer Klasse, die die abgeleitete Klasse erbt, mit dem Namen in der Warnung.  Wenn die abgeleitete Klasse mit dem Namen in der Warnung nie weiteren wird abgeleitet werden, oder die einschließende Funktion wird nicht bei der objekterstellung oder Zerstörung aufgerufen, die Warnung kann ignoriert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4437 generiert und veranschaulicht, das Code-Generation-Problem, das aus den fehlenden `vtordisp` Feld.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Dynamic_cast-Operator](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [Compilerwarnung (Ebene 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)