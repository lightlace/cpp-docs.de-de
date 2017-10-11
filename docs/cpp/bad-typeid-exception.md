---
title: Bad_typeid-Ausnahme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ea7dc85862622180038cf520ef92b752b65eba84
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="badtypeid-exception"></a>bad_typeid-Ausnahme
Die `bad_typeid` -Ausnahme wird ausgelöst durch den [Typeid-Operator](../cpp/typeid-operator.md) Wenn der Operand für `typeid` ist ein Nullzeiger.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Schnittstelle für `bad_typeid` ist:  
  
```  
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 Im folgenden Beispiel wird der `typeid`-Operators gezeigt, der eine `bad_typeid`-Ausnahme auslöst.  
  
```  
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
  
```  
Object is NULL  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Typinformationen](../cpp/run-time-type-information.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
