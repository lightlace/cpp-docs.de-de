---
title: Compilerwarnung (Stufe 3) C4240 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2f3c059e63bcca9bbde9e863cc17c9e240e4f78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057014"
---
# <a name="compiler-warning-level-3-c4240"></a>Compilerwarnung (Stufe 3) C4240

nicht dem Standard entsprechende Erweiterung: Zugriff auf "Classname" jetzt "Zugriffsspezifizierer ', zuvor definiert wurde ' Zugriffsspezifizierer ' definiert

ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), Sie können nicht den Zugriff auf eine geschachtelte Klasse ändern. Die Standard-Microsoft-Erweiterungen (/ Ze) können Sie folgende Warnung wird angezeigt.

## <a name="example"></a>Beispiel

```
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```