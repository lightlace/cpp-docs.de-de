---
title: __uuidof-Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 172ed545eb2c46db8df12e3e12a2296a5f172a1f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="uuidof-operator"></a>__uuidof-Operator
**Microsoft-spezifisch**  
  
 Ruft die GUID ab, die dem Ausdruck angefügt ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Ausdruck* einen Typnamen, Zeiger, Verweis oder Array dieses Typs ist möglich, eine Vorlage, die auf diese Typen oder eine Variable dieser Typen spezialisiert. Das Argument ist gültig, solange der Compiler es verwenden kann, um das angefügte GUID zu suchen.  
  
 Ist ein Sonderfall dieser systeminternen Funktion, wenn entweder **0** oder **NULL** als Argument angegeben ist. In diesem Fall gibt `__uuidof` eine GUID zurück, die aus Nullen besteht.  
  
 Verwenden Sie dieses Schlüsselwort, um die an folgende Elemente angefügte GUID zu extrahieren:  
  
-   Ein Objekt durch die [Uuid](../cpp/uuid-cpp.md) erweiterten Attribute.  
  
-   Ein bibliotheksblock erstellt, mit der [Modul](../windows/module-cpp.md) Attribut.  
  
> [!NOTE]
>  In einem Debugbuild initialisiert `__uuidof` ein Objekt immer dynamisch (zur Laufzeit). In einem Releasebuild kann `__uuidof` ein Objekt statistisch initialisieren (zur Kompilierzeit).  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code (kompiliert mit "ole32.lib") wird das "uuid" eines Bibliotheksblocks angezeigt, der mit dem Modulattribut erstellt wird:  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## <a name="comments"></a>Kommentare  
 In Fällen, in denen der Bibliotheksname nicht mehr im Gültigkeitsbereich, können Sie __LIBID\_ anstelle von `__uuidof`. Zum Beispiel:  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
