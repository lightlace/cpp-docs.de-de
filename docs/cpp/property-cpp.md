---
title: Eigenschaft (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- property_cpp
- Property
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d4cb68d02f9ee543c2d3271bc48ad4318352faa2
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
