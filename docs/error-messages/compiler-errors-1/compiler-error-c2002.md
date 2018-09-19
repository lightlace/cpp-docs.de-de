---
title: Compilerfehler C2002 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b87a7fe1513c695344676624ae1968060097c885
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116918"
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