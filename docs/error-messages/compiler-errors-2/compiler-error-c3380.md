---
title: Compilerfehler C3380 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 315031946f9a89f53097e4c2371286fba213f698
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252447"
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
