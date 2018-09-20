---
title: 'Gewusst wie: Angeben eines Out Parameter | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3af9c1d10206e89b0ad8462bd95fdf3b6062d713
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419502"
---
# <a name="how-to-specify-an-out-parameter"></a>Gewusst wie: Angeben eines out-Parameters

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