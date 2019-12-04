---
title: Schwerwiegender Fehler C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 95e13a6914b5e02441f95dd2256532dbd1d718e5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747019"
---
# <a name="fatal-error-c1308"></a>Schwerwiegender Fehler C1308

Verknüpfen von Assemblys

Eine NETMODULE-Datei ist als Eingabe für den Linker zulässig, aber eine Assembly ist nicht. Dieser Fehler kann generiert werden, wenn versucht wird, eine mit `/clr:safe`kompilierte Assembly zu verknüpfen.

Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).

Im folgenden Beispiel wird C1308 generiert:

```cpp
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

Und dann

```cpp
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```
