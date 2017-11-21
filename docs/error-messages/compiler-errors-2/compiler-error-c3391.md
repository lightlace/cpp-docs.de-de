---
title: Compilerfehler C3391 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3391
dev_langs: C++
helpviewer_keywords: C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8501d0a645d656bd0c86f093d1591985f9a3499a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3391"></a>Compilerfehler C3391
'Type_arg': Ungültiges Typargument für generischen Parameter 'Param' von 'Generic_type (generisch) muss ein NULL-Wert-Handletyp sein  
  
Ein generischer Typ wurde fehlerhaft instanziiert. Überprüfen Sie die Typdefinition. Weitere Informationen finden Sie unter <xref:System.Nullable> und [Generika](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird c# verwendet zum Erstellen einer Komponente, die einen generischen Typ mit bestimmten Einschränkungen, die nicht unterstützt werden, wenn generische Typen in C++ zu erstellen, enthält c++ / CLI. Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
Wenn die Komponente C3391.dll verfügbar ist, im folgende Beispiel wird C3391 generiert:  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```