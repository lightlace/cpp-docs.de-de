---
title: Make_collection (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::make_collection
dev_langs:
- C++
helpviewer_keywords:
- make_collection function [STL/CLR]
ms.assetid: c25fb0cb-ebd8-4198-a565-bad28d32ee19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 74d10af361b8ffabca1d31af98cb3170af76f023
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="makecollection-stlclr"></a>make_collection (STL/CLR)
Stellen Sie eine `range_adapter` von ein paar Iterator.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Iter>  
    range_adapter<Iter> make_collection(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Iter`  
 Der Typ des umschlossenen Iteratoren.  
  
 `first`  
 Erste Iterator zu umschließen.  
  
 `last`  
 Zweite Iterator zu umschließen.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt `gcnew range_adapter<Iter>(first, last)` zurück. Sie verwenden sie zum Erstellen einer `range_adapter<Iter>` Objekt aus einem Paar von Iteratoren.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cliext_make_collection.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in d1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Collections::ICollection^ p1 =   
        cliext::make_collection(d1.begin(), d1.end());   
    System::Console::WriteLine("Count = {0}", p1->Count);   
    System::Console::WriteLine("IsSynchronized = {0}",   
        p1->IsSynchronized);   
    System::Console::WriteLine("SyncRoot not nullptr = {0}",   
        p1->SyncRoot != nullptr);   
  
// copy the sequence   
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);   
  
    a1[0] = L'|';   
    p1->CopyTo(a1, 1);   
    a1[4] = L'|';   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
Count = 3  
IsSynchronized = False  
SyncRoot not nullptr = True  
 | a b c |  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Adapter >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)