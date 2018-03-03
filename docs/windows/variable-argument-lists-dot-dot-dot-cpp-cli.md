---
title: Variable Argumentlisten (...) (C + C++ / CLI) | Microsoft Docs
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
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b78b244a93bea0c669c37b5df32ec7146f7ac3b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="variable-argument-lists--ccli"></a>Variable Argumentlisten (...) (C++/CLI)
Dieses Beispiel zeigt, wie Sie die Syntax `...` in Visual C++ verwenden können, um Funktionen zu implementieren, die eine variable Anzahl von Argumenten haben.  
  
> [!NOTE]
>  Dieses Thema betrifft C++/CLI. Informationen zum Verwenden der `...` in ISO-Standard C++ finden Sie unter [Auslassungszeichen- und Variadic-Vorlagen](../cpp/ellipses-and-variadic-templates.md) und Ellipsen und Standardargumente in [Postfixausdrücke](../cpp/postfix-expressions.md).  
  
 Der Parameter, der `...` verwendet, muss der letzte Parameter in der Parameterliste sein.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```  
// mcppv2_paramarray.cpp  
// compile with: /clr  
using namespace System;  
double average( ... array<Int32>^ arr ) {  
   int i = arr->GetLength(0);  
   double answer = 0.0;  
  
   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];  
  
   return answer / i;  
}  
  
int main() {  
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));  
}  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
3  
```  
  
## <a name="code-example"></a>Codebeispiel  
 Das folgende Beispiel zeigt, wie Sie in C# eine Visual C++-Funktion aufrufen, die eine variable Anzahl von Argumenten akzeptiert.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 Die Funktion `f` kann beispielsweise von C# oder Visual Basic aufgerufen werden, als wäre sie eine Funktion, die eine variable Anzahl von Argumenten akzeptieren kann.  
  
 In C# kann ein Argument, das an ein `ParamArray`-Parameter übergeben wird, durch eine variable Anzahl von Argumenten aufgerufen werden. Das folgende Codebeispiel ist in C#.  
  
```  
// mcppv2_paramarray3.cs  
// compile with: /r:mcppv2_paramarray2.dll  
// a C# program  
  
public class X {  
   public static void Main() {  
      // Visual C# will generate a String array to match the   
      // ParamArray attribute  
      C myc = new C();  
      myc.f("hello", "there", "world");  
   }  
}  
```  
  
 Ein Aufruf von `f` in Visual C++ kann ein initialisiertes Array oder ein Array mit variabler Länge übergeben.  
  
```  
// mcpp_paramarray4.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
  
int main() {  
   C ^ myc = gcnew C();  
   myc->f("hello", "world", "!!!");  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../windows/arrays-cpp-component-extensions.md)