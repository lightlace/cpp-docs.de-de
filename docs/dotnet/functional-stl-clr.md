---
title: funktionale (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 38bfbe025c92aa54956a165367b367cecc6160b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="functional-stlclr"></a>functional (STL/CLR)
Fügen Sie den STL/CLR-Header `<cliext/functional>` zu definieren, die eine Reihe von Vorlagenklassen und zugehörige Vorlage Delegaten und Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <functional>  
```  
  
## <a name="declarations"></a>Deklarationen  
  
|delegate|Beschreibung|  
|--------------|-----------------|  
|[binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)|Delegaten mit zwei Argumenten.|  
|[binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)|Zurückgeben von Delegaten mit zwei Argumenten `void`.|  
|[unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)|Delegaten mit einem Argument.|  
|[unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)|Zurückgeben von Delegaten mit einem Argument `void`.|  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)|Funktionselement ein Funktionselement ist zwei Argumenten zu negieren.|  
|[binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)|Funktionselement erstes Argument an ein Funktionselement ist zwei Argumenten gebunden.|  
|[binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)|Funktionselement zweites Argument an ein Funktionselement ist zwei Argumenten gebunden.|  
|[divides (STL/CLR)](../dotnet/divides-stl-clr.md)|Teilen Sie Funktionselement.|  
|[equal_to (STL/CLR)](../dotnet/equal-to-stl-clr.md)|Entspricht dem Vergleich Funktionselement.|  
|[greater (STL/CLR)](../dotnet/greater-stl-clr.md)|Größer Vergleich Funktionselement.|  
|[greater_equal (STL/CLR)](../dotnet/greater-equal-stl-clr.md)|Größer oder gleich-Vergleich Funktionselement.|  
|[less (STL/CLR)](../dotnet/less-stl-clr.md)|Weniger Funktionselement Vergleich.|  
|[less_equal (STL/CLR)](../dotnet/less-equal-stl-clr.md)|Kleiner oder gleich dem Vergleich Funktionselement.|  
|[logical_and (STL/CLR)](../dotnet/logical-and-stl-clr.md)|Logisches AND Funktionselement.|  
|[logical_not (STL/CLR)](../dotnet/logical-not-stl-clr.md)|Logisches nicht Funktionselement.|  
|[logical_or (STL/CLR)](../dotnet/logical-or-stl-clr.md)|Logisches OR Funktionselement.|  
|[minus (STL/CLR)](../dotnet/minus-stl-clr.md)|Subtrahieren Sie Funktionselement.|  
|[modulus (STL/CLR)](../dotnet/modulus-stl-clr.md)|Modulus-Funktionselement.|  
|[multiplies (STL/CLR)](../dotnet/multiplies-stl-clr.md)|Multiplizieren Sie Funktionselement.|  
|[negate (STL/CLR)](../dotnet/negate-stl-clr.md)|Funktionselement zurückzugebenden Argument negiert.|  
|[not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)|Ist ungleich Vergleich Funktionselement.|  
|[plus (STL/CLR)](../dotnet/plus-stl-clr.md)|Fügen Sie Funktionselement hinzu.|  
|[unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)|Funktionselement zu negierende ein Funktionselement ist nur einem Argument.|  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[bind1st (STL/CLR)](../dotnet/bind1st-stl-clr.md)|Generiert eine binder1st für ein Argument und ein Funktionselement ist.|  
|[bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)|Generiert eine binder2nd für ein Argument und ein Funktionselement ist.|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|Generiert eine Unary_negate für ein Funktionselement ist.|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|Generiert eine Binary_negate für ein Funktionselement ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/funktionale >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)