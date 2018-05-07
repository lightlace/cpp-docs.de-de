---
title: Compilerfehler C3390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc731f714976d8ab32c5e7a629d008fde008a218
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3390"></a>Compilerfehler C3390
"Typargument": Ungültiges Typargument für den generischen Parameter "Param" von "generischer_Typ" (generisch). Muss ein Referenztyp sein.  
  
Ein generischer Typ wurde fehlerhaft instanziiert.  Überprüfen Sie die Typdefinition.  Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
Im ersten Beispiel wird c# eine Komponente erstellen, die einen generischen Typ mit bestimmten Einschränkungen, die nicht unterstützt werden, wenn generische Typen in C++ zu erstellen, enthält c++ / CLR. Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
Wenn die Komponente C3390.dll verfügbar ist, im folgende Beispiel wird C3390 generiert:  
  
```cpp  
// C3390_b.cpp  
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>  
ref class R { R(int) {} };  
value class V {};  
ref struct N { N() {} };  
  
int main () {  
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type  
   GR<R^, V, N^>^ gr2b; // OK  
}  
```