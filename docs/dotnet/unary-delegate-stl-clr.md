---
title: Unary_delegate (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unary_delegate
dev_langs:
- C++
helpviewer_keywords:
- unary_delegate function [STL/CLR]
ms.assetid: b3ee253c-98e8-466e-a272-505e47aed061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 689fc3afba26d4b20816f3513262b6c1fc269e2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="unarydelegate-stlclr"></a>unary_delegate (STL/CLR)
Die Genereic Klasse beschreibt einen Delegaten mit nur einem Argument. Sie verwenden, geben Sie einen Delegaten im Hinblick auf die Argument- und Rückgabetypen Typen.  
  
## <a name="syntax"></a>Syntax  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### <a name="parameters"></a>Parameter  
 arg  
 Der Typ des Arguments.  
  
 Ergebnis  
 Der Rückgabetyp.  
  
## <a name="remarks"></a>Hinweise  
 Der Delegat Genereic beschreibt eine Funktion nur einem Argument.  
  
 Beachten Sie, dass für:  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 die Typen `Fun1` und `Fun2` sind Synonyme, während er sich für:  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 sind sie nicht den gleichen Typ.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
hash(L'a') = 5  
hash(L'b') = 22  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [Binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)