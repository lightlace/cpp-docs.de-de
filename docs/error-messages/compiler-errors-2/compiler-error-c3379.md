---
title: Compilerfehler C3379 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3379
dev_langs: C++
helpviewer_keywords: C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9fd5a8acf918a0f6b485cf9ba94ad759d58f7b2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3379"></a>Compilerfehler C3379
'Klasse': eine geschachtelte Klasse darf nicht als Teil der Deklaration einen Assembly-Zugriffsspezifizierer haben  
  
 Bei Anwendung auf einem verwalteten Typ, z. B. Klasse oder Struktur, die [öffentlichen](../../cpp/public-cpp.md) und [private](../../cpp/private-cpp.md) -Schlüsselwort geben an, ob die Klasse über Assemblymetadaten verfügbar gemacht werden. `public`oder `private` kann nicht angewendet werden, um eine geschachtelte Klasse, die den Assemblyzugriff der einschließenden Klasse erben.  
  
 Bei Verwendung mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md), `ref` und `value` -Schlüsselwort geben an, dass eine Klasse verwaltet wird (finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 Im folgende Beispiel wird C3379 generiert:  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
