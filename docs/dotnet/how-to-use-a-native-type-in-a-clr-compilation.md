---
title: 'Vorgehensweise: Verwenden eines nativen Typs in einer Clr - Kompilierung'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: 0079be21b474858684e1abaaeb363820764a701d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459952"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>Gewusst wie: Verwenden eines systemeigenen Typs in einer /clr-Kompilierung

Sie können definieren, einen systemeigenen Typ in eine **"/ CLR"** Kompilierung und jede Verwendung dieses nativen Typs von innerhalb der Assembly ist gültig. Allerdings werden systemeigene Typen für die Verwendung von Metadaten verwiesen wird nicht verfügbar.

Jede Assembly muss die Definition aller systemeigenen Typen enthalten, die dazu verwendet werden.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Dieses Beispiel erstellt eine Komponente, die definiert und verwendet einen systemeigenen Typ.

```
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

## <a name="example"></a>Beispiel

In diesem Beispiel definiert einen Client, der Komponente verwendet. Beachten Sie, dass es ist ein Fehler den nativen Typ, den Zugriff auf, es sei denn, sie in der Kompiliereinheit definiert ist.

```
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)