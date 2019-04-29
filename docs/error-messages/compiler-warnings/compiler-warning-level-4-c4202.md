---
title: Compilerwarnung (Stufe 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: c66e2243ee5eca55105de27c9824ee8ced338500
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401266"
---
# <a name="compiler-warning-level-4-c4202"></a>Compilerwarnung (Stufe 4) C4202

nicht dem Standard entsprechende Erweiterung: "...": Prototypparameter in der Namensliste ist unzulässig

Eine herkömmliche Funktionsdefinition enthält Variable Argumente. Diese Definitionen generiert einen Fehler ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Beispiel

```
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```