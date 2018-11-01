---
title: Schwerwiegender Fehler C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 0128953b3b3fa0f29a6764c1d7dab0ece67dfae7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640621"
---
# <a name="fatal-error-c1308"></a>Schwerwiegender Fehler C1308

Verknüpfen von Assemblys wird nicht unterstützt.

Eine NETMODULE-Datei als Eingabe für den Linker zulässig ist, aber eine Assembly ist nicht. Dieser Fehler kann generiert werden, wenn versucht wird, verknüpfen Sie eine Assembly kompiliert mit `/clr:safe`.

Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).

Im folgende Beispiel wird die C1308 generiert:

```
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

Und dann

```
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```