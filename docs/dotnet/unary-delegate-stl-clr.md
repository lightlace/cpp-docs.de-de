---
title: "unary_delegate (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::unary_delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_delegate-Funktion [STL/CLR]"
ms.assetid: b3ee253c-98e8-466e-a272-505e47aed061
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# unary_delegate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die genereic Klasse beschreibt einen EinArgumentdelegaten.  Sie verwenden sie angeben einem Delegaten in BNF Argument und Rückgabetypen.  
  
## Syntax  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### Parameter  
 Arg  
 Der Typ des Arguments.  
  
 Ergebnis  
 Der Rückgabetyp.  
  
## Hinweise  
 Der genereic Delegat beschreibt eine EinArgumentfunktion.  
  
 Beachten Sie das für:  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 die Typen `Fun1` und `Fun2` sind Synonyme, während für:  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 sie sind nicht der gleiche Typ.  
  
## Beispiel  
  
```  
// cliext_unary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
int hash_val(wchar_t val)   
    {   
    return ((val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate<wchar_t, int> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
  **Hash \(L'a\) \= 5**  
**Hash \(L'b\) \= 22**   
## Anforderungen  
 **Header:** \<cliext\/funktionsfähig\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [binary\_delegate](../dotnet/binary-delegate-stl-clr.md)   
 [binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)