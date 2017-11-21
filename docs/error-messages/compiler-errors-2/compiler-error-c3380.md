---
title: Compilerfehler C3380 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3380
dev_langs: C++
helpviewer_keywords: C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b06f57795cea7dda7b3ba2797f7c57026a9acf60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3380"></a>Compilerfehler C3380
"Klasse": Ungültiger Assembler-Zugriffsspezifizierer - nur "public" oder "private" sind zulässig  
  
 Wenn das [public](../../cpp/public-cpp.md) - oder [private](../../cpp/private-cpp.md) -Schlüsselwort auf eine verwaltete Klasse oder Struktur angewendet wird, gibt es an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird. Nur `public` oder `private` kann auf eine Klasse in einem Programm angewendet werden, das mit [/clr](../../build/reference/clr-common-language-runtime-compilation.md)kompiliert wird.  
  
 Die `ref` und `value` Keywords-Eigenschaft, bei der Verwendung mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md), um anzugeben, dass eine verwaltete Klasse handelt (finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 Im folgenden Beispiel wird C3380 generiert:  
  
```  
// C3380_2.cpp  
// compile with: /clr  
protected ref class A {   // C3380  
// try the following line instead  
// ref class A {  
public:  
   static int i = 9;  
};  
  
int main() {  
   A^ myA = gcnew A;  
   System::Console::WriteLine(myA->i);  
}  
```  
