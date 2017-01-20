---
title: "C-Style Casts with /clr (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C-style casts and /clr"
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# C-Style Casts with /clr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das folgende Thema gilt nur für Common Language Runtime zu.  
  
 Wenn Sie mit CLR verwendet werden, gibt, der Compiler versucht, im C\-Format bis eine der Licht zuzuordnen Umwandlung ein, unten, in der folgenden Reihenfolge aufgeführt sind:  
  
1.  const\_cast  
  
2.  safe\_cast  
  
3.  safe\_cast plus const\_cast  
  
4.  static\_cast  
  
5.  static\_cast plus const\_cast  
  
 Wenn keine der Umwandlungen, die oben aufgeführten, gültig und wenn der Typ des Ausdrucks und des Zieltyps CLR\-Verweistypen sind, Umwandlungszuordnungen im C\-Format an eine LaufzeitÜberprüfung \(castclass MSIL Anweisung\).  Andernfalls wird eine C\-Typumwandlung ungültig und die Compilerprobleme ein Fehler betrachtet.  
  
## Hinweise  
 E\-ähnlich Umwandlung einer wird nicht empfohlen.  Beim Kompilieren mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md), verwenden Sie [safe\_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird eine Formatzeichenfolge Umwandlung veranschaulicht, die `const_cast` zugeordnet wird.  
  
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
  
 Im folgenden Beispiel wird eine Formatzeichenfolge Umwandlung veranschaulicht, die `safe_cast` zugeordnet wird.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 Im folgenden Beispiel wird eine Formatzeichenfolge Umwandlung veranschaulicht, die `safe_cast` und `const_cast` zuordnet.  
  
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
  
 Im folgenden Beispiel wird eine Formatzeichenfolge Umwandlung veranschaulicht, die `static_cast` zugeordnet wird.  
  
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
  
 Im folgenden Beispiel wird eine Formatzeichenfolge Umwandlung veranschaulicht, die `static_cast` und `const_cast` zuordnet.  
  
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
  
 Im folgenden Beispiel wird eine Formatzeichenfolge Umwandlung veranschaulicht, die in eine Laufzeitüberprüfung zuordnet.  
  
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
  
 Im folgenden Beispiel wird eine ungültige Umwandlung im C\-Format an, die der Compiler angewiesen wird, einen Fehler ausgegeben.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## Voraussetzungen  
 Compileroption: **\/clr**  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)