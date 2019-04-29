---
title: Linkertoolfehler LNK2028
ms.date: 11/04/2016
f1_keywords:
- LNK2028
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
ms.openlocfilehash: ed2dc1a95d4dd7c447b360da21b5046e20f79083
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298983"
---
# <a name="linker-tools-error-lnk2028"></a>Linkertoolfehler LNK2028

"*Exported_function*" (*ergänzter_Name*) verwiesen wird, in der Funktion "*Funktion_mit_Funktionsaufruf*" (*ergänzter_Name*)

## <a name="remarks"></a>Hinweise

Beim Versuch, eine native Funktion in einem reinen Image importieren, denken Sie daran, dass die Konventionen für die impliziten Aufrufen zwischen systemeigenen und reinen Kompilierungen unterscheiden.

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

## <a name="example"></a>Beispiel

In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen-Funktion, deren Aufrufkonvention implizit wird, generiert [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt einen reinen Client, der in der nativen Funktion benötigt. Allerdings die Aufrufkonvention unter **/CLR: pure** ist [__clrcall](../../cpp/clrcall.md). Im folgende Beispiel wird die LNK2028 generiert.

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```