---
title: Eigenschaft (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- property_cpp
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a791615f7fd91a7ccfcda45b23fc524ebd9b6400
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="property-c"></a>property (C++)
**Microsoft-spezifisch**  
  
 Dieses Attribut kann auf nicht statische "virtuelle Datenmember" in einer Klassen- oder Strukturdefinition angewendet werden. Der Compiler behandelt diese "virtuellen Datenmember" als Datenmember, indem er ihre Verweise in Funktionsaufrufe ändert.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   __declspec( property( get=get_func_name ) ) declarator  
   __declspec( property( put=put_func_name ) ) declarator  
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Compiler erkennt einen Datenmember mit diesem Attribut deklariert wird, auf der rechten Seite eines Operators Memberauswahl ("**.**"oder"**->**"), konvertiert Sie den Vorgang, um eine **Abrufen** oder **put** -Funktion, je nachdem, ob ein solcher Ausdruck ein l-Wert oder ein r-Wert. In den schwierigeren Kontexten, z. B. "`+=`", eine neue Version wird ausgeführt, indem Sie beide **abrufen** und **put**.  
  
 Dieses Attribut kann in der Deklaration eines leeren Arrays in einer Klassen- oder Strukturdefinition ebenfalls verwendet werden. Zum Beispiel:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 Die oben genannte Anweisung gibt an, dass `x[]` mit einem oder mehreren Arrayindizes verwendet werden kann. In diesem Fall wird `i=p->x[a][b]` in `i=p->GetX(a, b)` umgewandelt und `p->x[a][b] = i` in `p->PutX(a, b, i);`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="example"></a>Beispiel  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)