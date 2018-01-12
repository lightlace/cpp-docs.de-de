---
title: Compilerfehler C2885 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2885
dev_langs: C++
helpviewer_keywords: C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98f3501cc029094d7f00e941026c0f7d1ed7d80b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2885"></a>Compilerfehler C2885
'class:: Identifier': keine gültige using-Deklaration im Gültigkeitsbereich einer nicht-Klasse  
  
 Sie verwendet ein [mit](../../cpp/using-declaration.md) Deklaration nicht ordnungsgemäß.  
  
## <a name="example"></a>Beispiel  
 Dieser Fehler kann infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: Es ist nicht mehr zulässig, eine `using` Deklaration, um einen geschachtelten Typ handelt; qualifizieren Sie explizit alle Verweise, die Sie, um den geschachtelten Typ, der den Typ in einen Namen einfügen vornehmen Speicherplatz, oder erstellen Sie eine Typdefinition.  
  
 Im folgende Beispiel wird C2885 generiert.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Bei Verwendung der `using` -Schlüsselwort mit einem Klassenmember C++ erfordert, dass Sie dieses Element innerhalb einer anderen Klasse (in einer abgeleiteten Klasse) zu definieren.  
  
 Im folgende Beispiel wird C2885 generiert.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```