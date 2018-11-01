---
title: Compilerwarnung (Stufe 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: fe5306cc7909138fea0159553b53c2adc6a46dc0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498240"
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