---
title: Compilerfehler C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: 30f472aa7a9475a19eea0e92fe5c2ea0d54e382b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442847"
---
# <a name="compiler-error-c2002"></a>Compilerfehler C2002

Ungültige Breitzeichen-Konstante

Die Multibyte-Zeichenfolgen-Konstante ist ungültig.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der Breitzeichenkonstante enthält mehr Bytes als erwartet.

1. Der Standardheader STDDEF.h ist nicht enthalten.

1. Breitzeichen können nicht mit normalen Zeichenfolgenliteralen verkettet werden.

1. Das Zeichen "L" muss eine Breitzeichen-Konstante vorangestellt werden:

    ```
    L'mbconst'
    ```

1. Für Microsoft C++ müssen die Textargumente einer Präprozessordirektive ASCII sein. Z. B. die Direktive `#pragma message(L"string")`, ist ungültig.