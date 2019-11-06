---
title: Compilerwarnung (Stufe 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: f1db3eabc3b614019676dc4494e83104c62fe579
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627307"
---
# <a name="compiler-warning-level-1-c4218"></a>Compilerwarnung (Stufe 1) C4218

nicht dem Standard entsprechende Erweiterung: Es muss mindestens eine Speicher Klasse oder ein Typ angegeben werden.

Mit den standardmäßigen Microsoft-Erweiterungen (/Ze) können Sie eine Variable deklarieren, ohne einen Typ oder eine Speicher Klasse anzugeben. Der Standardtyp ist `int`.

## <a name="example"></a>Beispiel

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Diese Deklarationen sind unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ungültig.