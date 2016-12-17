---
title: "Variable Argument Lists (...) (C++/CLI)"
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
  - "variable argument lists"
  - "parameter arrays"
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# Variable Argument Lists (...) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie Sie die Syntax `...` in Visual C\+\+ verwenden können, um Funktionen zu implementieren, die eine variable Anzahl von Argumenten haben.  
  
> [!NOTE]
>  Dieses Thema betrifft C\+\+\/CLI.  Weitere Informationen über die Verwendung der `...` in ISO\-Standard\-C\+\+ finden Sie unter [Auslassungszeichen\- und Variadic\-Vorlagen](../cpp/ellipses-and-variadic-templates.md) und [Ellipsen und Standardargumente](../misc/ellipses-and-default-arguments.md).  
  
 Der Parameter, der `...` verwendet, muss der letzte Parameter in der Parameterliste sein.  
  
## Beispiel  
  
### Code  
  
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
  
### Ausgabe  
  
```  
3  
```  
  
## Codebeispiel  
 Das folgende Beispiel zeigt, wie Sie in C\# eine Visual C\+\+\-Funktion aufrufen, die eine variable Anzahl von Argumenten akzeptiert.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 Die Funktion `f` kann beispielsweise von C\# oder Visual Basic aufgerufen werden, als wäre sie eine Funktion, die eine variable Anzahl von Argumenten akzeptieren kann.  
  
 In C\# kann ein Argument, das an ein `ParamArray`\-Parameter übergeben wird, durch eine variable Anzahl von Argumenten aufgerufen werden.  Das folgende Codebeispiel ist in C\#.  
  
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
  
 Ein Aufruf von `f` in Visual C\+\+ kann ein initialisiertes Array oder ein Array mit variabler Länge übergeben.  
  
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
  
## Siehe auch  
 [Arrays](../windows/arrays-cpp-component-extensions.md)