---
title: "Compilerfehler C3380"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3380"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3380"
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3380
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klasse": Ungültiger Assembler\-Zugriffsspezifizierer \- nur "public" oder "private" sind zulässig  
  
 Wenn das [public](../../cpp/public-cpp.md)\- oder [private](../../cpp/private-cpp.md)\-Schlüsselwort auf eine verwaltete Klasse oder Struktur angewendet wird, gibt es an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird. Nur `public` oder `private` kann auf eine Klasse in einem Programm angewendet werden, das mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert wird.  
  
 Die Schlüsselwörter `ref` und `value` geben bei Verwendung mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) an, dass eine Klasse verwaltet ist \(weitere Informationen finden Sie unter [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)\).  
  
 Im folgenden Beispiel wird C3380 generiert:  
  
```  
// C3380_2.cpp // compile with: /clr protected ref class A {   // C3380 // try the following line instead // ref class A { public: static int i = 9; }; int main() { A^ myA = gcnew A; System::Console::WriteLine(myA->i); }  
```  
  
 Im folgenden Beispiel wird C3380 generiert:  
  
```  
// C3380.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> protected __gc class A {   // C3380 // try the following line instead // __gc class A { public: static int i = 9; }; int main() { A *myA = new A; Console::WriteLine(myA->i); }  
```