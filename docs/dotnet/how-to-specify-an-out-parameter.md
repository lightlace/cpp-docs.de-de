---
title: 'Vorgehensweise: Angeben eines Out Parameter'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: 901257b92aaa5e13e6e79d612ca590b734e15881
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387215"
---
# <a name="how-to-specify-an-out-parameter"></a>Vorgehensweise: Angeben eines Out Parameter

Dieses Beispiel zeigt, wie um anzugeben, dass ein Funktionsparameter Ausgabeparameter ist und wie Sie diese Funktion aus einem C#-Programm aufrufen.

Ein Out-Parameter wird angegeben, in Visual C++ mit <xref:System.Runtime.InteropServices.OutAttribute> .

## <a name="example"></a>Beispiel

Der erste Teil dieses Beispiels ist ein Visual C++-DLL mit einem Typ, der eine Funktion mit der Out-Parameter enthält.

```
// cpp_out_param.cpp
// compile with: /LD /clr:safe
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

## <a name="example"></a>Beispiel

Dies ist ein C#-Client, der im vorherigen Beispiel erstellte Visual C++-Komponente verwendet.

```
// cpp_out_param_2.cs
// compile with: /reference:cpp_out_param.dll
using System;
class TestClass {
   public static void Main() {
      String t;
      TestStruct.Test(out t);
      System.Console.WriteLine(t);
   }
}
```

```Output
a string
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
