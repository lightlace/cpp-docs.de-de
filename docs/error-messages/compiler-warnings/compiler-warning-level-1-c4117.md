---
title: Compilerwarnung (Stufe 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 657963dd0199c1474f0cef566e5a177a16247521
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466214"
---
# <a name="compiler-warning-level-1-c4117"></a>Compilerwarnung (Stufe 1) C4117

Makroname 'Name' ist reserviert. 'Befehl' wird ignoriert.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Versuchen Sie, ein vordefiniertes Makro zu definieren bzw. dessen Definition aufzuheben.

1. Versuchen Sie, den **defined**-Präprozessoroperator zu definieren bzw. dessen Definition aufzuheben.

Im folgenden Beispiel wird C4117 generiert:

```
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```