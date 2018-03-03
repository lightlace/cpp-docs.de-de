---
title: C-Stil mit Clr - wandelt (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e529a40f8eb876791f49559d3970696fdece489d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="c-style-casts-with-clr-ccli"></a>C-stilartige Umwandlungen mit /clr (C++/CLI)
Das folgende Thema gilt nur für die Common Language Runtime.  
  
 Mit CLR-Typen verwendet, versucht der Compiler die C-Format eine Umwandlung in einen der unten aufgeführten, in der folgenden Reihenfolge Umwandlungen zuordnen:  
  
1.  const_cast  
  
2.  safe_cast  
  
3.  "safe_cast" plus const_cast-Operator  
  
4.  static_cast  
  
5.  Static_cast plus const_cast-Operator  
  
 Wenn keines der oben aufgeführten Umwandlungen gültig ist und der Typ des Ausdrucks und der Zieltyp CLR-Verweistypen sind, wird eine laufzeitüberprüfung (Castclass MSIL-Anweisung) Umwandlung im C-Stil zugeordnet. Andernfalls eine Umwandlung im C-Format ist als ungültig betrachtet, und der Compiler eines Fehlers.  
  
## <a name="remarks"></a>Hinweise  
 Eine Umwandlung im C-Format wird nicht empfohlen. Beim Kompilieren mit [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md), verwenden Sie ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md).  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine `const_cast`.  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine `safe_cast`.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine `safe_cast` plus `const_cast`.  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine `static_cast`.  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine `static_cast` plus `const_cast`.  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das eine Überprüfung zur Laufzeit zugeordnet.  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 Das folgende Beispiel zeigt ein ungültige C-Format umgewandelt, die bewirkt, dass der Compiler einen Fehler ausgeben.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)