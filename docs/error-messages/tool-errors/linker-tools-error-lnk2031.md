---
title: Linkertoolfehler LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 003b9a58bfb08130f034530f59e2de27efa2ae8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484836"
---
# <a name="linker-tools-error-lnk2031"></a>Linkertoolfehler LNK2031

> kann nicht generiert werden für p/invoke "*Function_declaration*" *ergänzter_Name*; in den Metadaten fehlt die Aufrufkonvention

## <a name="remarks"></a>Hinweise

Beim Versuch, eine native Funktion in einem reinen Image importieren, denken Sie daran, dass die Konventionen für die impliziten Aufrufen zwischen systemeigenen und reinen Kompilierungen unterscheiden. Weitere Informationen zu reinen Bildern finden Sie unter [reiner und überprüfbarer Code (C++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

## <a name="example"></a>Beispiel

In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen-Funktion, deren Aufrufkonvention implizit wird, generiert [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt einen reinen Client, der in der nativen Funktion benötigt. Allerdings die Aufrufkonvention unter **/CLR: pure** ist [__clrcall](../../cpp/clrcall.md). Im folgende Beispiel wird die LNK2031 generiert.

```cpp
// LNK2031_b.cpp
// compile with: /clr:pure LNK2031.lib
// LNK2031 expected
extern "C" int func();

int main() {
   return func();
}
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie die systemeigene Funktion in einem reinen Image genutzt wird. Beachten Sie den expliziten **__cdecl** Spezifizierer der Aufrufkonvention.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```