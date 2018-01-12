---
title: 'Vector:: Vector (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::vector
dev_langs: C++
helpviewer_keywords: vector member [STL/CLR]
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a321e18c9fc921e1d88961b4f282c29917fa7962
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vectorvector-stlclr"></a>vector::vector (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Die Anzahl einzufügender Elemente.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Einzufügendes Objekt bzw. einzufügender Bereich.  
  
 Val  
 Der Wert des einzufügenden Elements.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `vector();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente. Sie können damit Geben Sie eine leere gesteuerte Sequenz.  
  
 Der Konstruktor:  
  
 `vector(vector<Value>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`). Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Vektorobjekt gesteuert wird `right`.  
  
 Der Konstruktor:  
  
 `vector(vector<Value>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`). Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die von der Vector-Objekt, dessen Handle, gesteuert wird `right`.  
  
 Der Konstruktor:  
  
 `explicit vector(size_type count);`  
  
 Initialisiert die gesteuerte Sequenz mit `count` jedes Elemente mit dem Wert `value_type()`. Sie verwenden es den Container mit Elementen gefüllt alle mit dem Standardwert.  
  
 Der Konstruktor:  
  
 `vector(size_type count, value_type val);`  
  
 Initialisiert die gesteuerte Sequenz mit `count` jedes Elemente mit dem Wert `val`. Sie verwenden sie den Container mit Elementen gefüllt alle mit dem gleichen Wert.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`). Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz erstellen.  
  
 Der Konstruktor:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`. Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz beschrieben durch einen Enumerator erstellen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector:: Assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)   
 [Vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)