---
title: C-stilartige Umwandlungen mit / Clr (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ffb2e5a7276925c5f03d06a909803d001532f35
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464583"
---
# <a name="c-style-casts-with-clr-ccli"></a>C-stilartige Umwandlungen mit /clr (C++/CLI)
Das folgende Thema gilt nur für die Common Language Runtime.  
  
 Wenn mit CLR-Typen verwendet wird, versucht der Compiler Umwandlung im C-Format in eines der Umwandlungen zurückzuführen, die unten aufgeführten, in der folgenden Reihenfolge zugeordnet:  
  
1.  const_cast  
  
2.  safe_cast  
  
3.  "safe_cast" und "const_cast"  
  
4.  static_cast  
  
5.  "static_cast" plus "const_cast"  
  
 Wenn keines der oben aufgeführten Umwandlungen gültig ist und den Typ des Ausdrucks und den Typ des CLR-Verweistypen sind, wird eine laufzeitüberprüfung (Castclass MSIL-Anweisung) Umwandlung im C-Stil zugeordnet. Andernfalls wird eine Umwandlung im C-Stil ist ungültig, und gibt der Compiler einen Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Eine Umwandlung im C-Stil wird nicht empfohlen. Beim Kompilieren mit [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md), verwenden Sie ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md).  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine **"const_cast"**.  
  
```cpp  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine **"safe_cast"**.  
  
```cpp  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine **"safe_cast"** plus **"const_cast"**.  
  
```cpp  
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
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine **"static_cast"**.  
  
```cpp  
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
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das zugeordnet, eine **"static_cast"** plus **"const_cast"**.  
  
```cpp  
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
  
 Das folgende Beispiel zeigt eine Umwandlung im C-Format, das eine laufzeitüberprüfung zugeordnet.  
  
```cpp  
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
  
 Das folgende Beispiel zeigt ein ungültige C-Format umgewandelt, wodurch den Compiler einen Fehler ausgeben.  
  
```cpp  
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