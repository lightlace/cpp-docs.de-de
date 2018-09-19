---
title: Compilerwarnung (Stufe 1) C4218 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1970dd1bd231716f59508a7cca9f82d3e13151ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074044"
---
# <a name="compiler-warning-level-1-c4218"></a>Compilerwarnung (Stufe 1) C4218

nicht dem Standard entsprechende Erweiterung: müssen mindestens eine Speicherklasse oder einen Typ angeben

Mit den Standard-Microsoft-Erweiterungen (/ Ze) können Sie eine Variable deklarieren, ohne dass eine Klasse vom Typ oder Speicher. Der Standardtyp ist `int`.

## <a name="example"></a>Beispiel

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Derartige Deklarationen sind ungültige ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).