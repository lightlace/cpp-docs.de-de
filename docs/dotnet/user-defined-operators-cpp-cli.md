---
title: Benutzerdefinierte Operatoren (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73a397664d5e5a9074731b6eac879fe965580f05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="user-defined-operators-ccli"></a>Benutzerdefinierte Operatoren (C++/CLI)
Benutzerdefinierte Operatoren für verwaltete Typen sind als statische Member oder Instanzmember oder im globalen Gültigkeitsbereich zulässig. Allerdings werden nur statische Operatoren über Metadaten für Clients, die in einer anderen Sprache als Visual C++ geschrieben sind.  
  
 In einem Referenztyp muss einer der Parameter eines statischen benutzerdefinierten Operators eines der folgenden sein:  
  
-   Ein Handle (`type` ^) mit einer Instanz des einschließenden Typs.  
  
-   Ein Verweis Typ Dereferenzierung (`type`^ & oder Type ^ %) an ein Handle zu einer Instanz des einschließenden Typs.  
  
 In einen Werttyp aufweist muss einer der Parameter eines statischen benutzerdefinierten Operators eines der folgenden sein:  
  
-   Desselben Typs wie der einschließende Werttyp.  
  
-   Ein Typ Zeigerdereferenzierung (`type`^) in den einschließenden Typ.  
  
-   Ein Verweis Typ Dereferenzierung (`type`% oder `type`&) in den einschließenden Typ.  
  
-   Ein Verweis Typ Dereferenzierung (`type`^ % oder `type`^ &) an das Handle.  
  
 Sie können die folgenden Operatoren definieren:  
  
|Operator|Unärer/binärer Forms?|  
|--------------|--------------------------|  
|!|Unär|  
|!=|Binär|  
|%|Binär|  
|&|Unär und binär|  
|&&|Binär|  
|*|Unär und binär|  
|+|Unär und binär|  
|++|Unär|  
|,|Binär|  
|-|Unär und binär|  
|--|Unär|  
|->|Unär|  
|/|Binär|  
|<|Binär|  
|<<|Binär|  
|\<=|Binär|  
|=|Binär|  
|==|Binär|  
|>|Binär|  
|>=|Binär|  
|>>|Binär|  
|^|Binär|  
|false|Unär|  
|true|Unär|  
|&#124;|Binär|  
|&#124;&#124;|Binär|  
|~|Unär|  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
```Output  
-5  
-4  
-3  
-2  
-1  
-2  
-3  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Operator Sprachsynthese, die nur verfügbar ist, bei der Verwendung **"/ CLR"** zu kompilieren. Operator Sprachsynthese erstellt die Zuweisung eines binären Operators, sofern nicht definiert ist, hat die linke Seite des Zuweisungsoperators auf einen CLR-Typ.  
  
```cpp  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
```Output  
30  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)