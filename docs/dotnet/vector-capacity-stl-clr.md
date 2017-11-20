---
title: 'Vector:: Capacity (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::capacity
dev_langs: C++
helpviewer_keywords: capacity member [STL/CLR]
ms.assetid: f82d8da9-8b4d-4288-8d18-8e9ca5911d87
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 97693360d03f0c861f1c2f1b956fcbd136d7c6f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="vectorcapacity-stlclr"></a>vector::capacity (STL/CLR)
Gibt die Größe des belegten Speichers für den Container.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_type capacity();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt den Speicherplatz, um die kontrollierte Sequenz, ein Wert, der mindestens so groß wie derzeit zugewiesen [Vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`. Sie verwenden es, um zu bestimmen, wie viel der Container vergrößert werden kann, bevor sie Speicher für die gesteuerte Sequenz neu zugeordnet werden muss.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_vector_capacity.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  
  
## <a name="description"></a>Beschreibung  
 Beachten Sie, dass die tatsächliche Kapazität von der hier gezeigten Werte, so lange, bis alle abweichen `ok` Tests melden "true".  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)