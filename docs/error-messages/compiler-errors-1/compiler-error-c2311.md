---
title: Compilerfehler C2311
ms.date: 11/04/2016
f1_keywords:
- C2311
helpviewer_keywords:
- C2311
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
ms.openlocfilehash: f4eff6f88a247dd17a2c9399b9009717f8fb8e62
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303046"
---
# <a name="compiler-error-c2311"></a>Compilerfehler C2311

'Exception': wurde aufgefangen durch "..." in Zeilennummer

Der Catch-Handler für das Auslassungszeichen (…) muss der letzte Handler einer ausgelösten Ausnahme.

Im folgende Beispiel wird die C2311 generiert:

```
// C2311.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "ooops!";
   }
   catch( ... ) {}
   catch( int ) {}   // C2311  ellipsis handler not last catch
}
```