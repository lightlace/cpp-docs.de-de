---
title: "Benutzerdefinierte Operatoren (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Operatoren unter /clr"
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzerdefinierte Operatoren (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benutzerdefinierte Operatoren für verwaltete Typen werden als statische Member kann oder Member oder im globalen Gültigkeitsbereich als Instanz zurückgibt.  jedoch nur statische Operatoren sind durch Metadaten für Clients verfügbar, die in eine andere Sprache als Visual C\+\+ geschrieben sein.  
  
 In einem Verweistyp muss einer der Parameter einer statischen benutzerdefinierten Operators einem dieser sein:  
  
-   Ein Handle \(^`type` \) zu einer Instanz des einschließenden Typs.  
  
-   Eine Verweistypdereferenzierung \(`type` oder type^% ^& \) zu einem Handle einer Instanz des einschließenden Typs.  
  
 In einen Werttyp muss einer der Parameter einer statischen benutzerdefinierten Operators einem dieser sein:  
  
-   im selben Typ wie der einschließende Werttyp.  
  
-   Eine `type` Zeigertypdereferenzierung \(^\) dem einschließenden Typ.  
  
-   Eine Verweistypdereferenzierung % \(`type` oder `type`&\) auf den einschließenden Typ.  
  
-   Eine Verweistypdereferenzierung \(`type` oder `type`^% ^&\) in Anspruch.  
  
 Sie können die folgenden Operatoren definieren:  
  
|Operator|Unär\/binäre Formen?|  
|--------------|--------------------------|  
|\!|Unär|  
|\!\=|Binär|  
|%|Binär|  
|&|Unär und binär|  
|&&|Binär|  
|\*|Unär und binär|  
|\+|Unär und binär|  
|\+\+|Unär|  
|,|Binär|  
|\-|Unär und binär|  
|\-\-|Unär|  
|\-\>|Unär|  
|\/|Binär|  
|\<|Binär|  
|\<\<|Binär|  
|\<\=|Binär|  
|\=|Binär|  
|\=\=|Binär|  
|\>|Binär|  
|\>\=|Binär|  
|\>\>|Binär|  
|^|Binär|  
|false|Unär|  
|true|Unär|  
|&#124;|Binär|  
|&#124;&#124;|Binär|  
|~|Unär|  
  
## Beispiel  
  
```  
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
  
  **\-5**  
**\-4**  
**\-3**  
**\-2**  
**\-1**  
**\-2**  
**\-3**   
## Beispiel  
 Im folgenden Beispiel wird Operatorsynthese, die nur verfügbar ist, wenn Sie **\/clr** verwenden, um zu kompilieren.  Operatorsynthese erstellt das Abtretungsformular eines binären Operators, wenn nicht definiert ist, wobei die linke Seite des Zuweisungsoperators einen CLR\-Typ hat.  
  
```  
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
  
  **30**   
## Siehe auch  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)