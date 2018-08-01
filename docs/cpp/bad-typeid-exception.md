---
title: Bad_typeid-Ausnahme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55718522bdbf618fb656eedc5c6afd59bfcaca08
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409005"
---
# <a name="badtypeid-exception"></a>bad_typeid-Ausnahme
Die **Bad_typeid** Ausnahme wird von der [Typeid-Operator](../cpp/typeid-operator.md) bei der der Operand für **Typeid** ist ein Nullzeiger.  
  
## <a name="syntax"></a>Syntax  
  
```  
catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Schnittstelle für **Bad_typeid** ist:  
  
```cpp 
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 Das folgende Beispiel zeigt die **Typeid** Operator Auslösen einer **Bad_typeid** Ausnahme.  
  
```cpp 
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```Output 
Object is NULL  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Typinformationen](../cpp/run-time-type-information.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)