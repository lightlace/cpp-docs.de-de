---
title: NULL-Anweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27180a8252344f7b3185ec83b48ebef42f832907
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077359"
---
# <a name="null-statement"></a>NULL-Anweisung

Die "null-Anweisung" ist eine Ausdrucksanweisung, bei der *Ausdruck* fehlt. Dies ist nützlich, wenn in der Syntax der Sprache eine Anweisung erwartet wird, jedoch keine Ausdrucksauswertung. Die Anweisung besteht aus einem Semikolon.

NULL-Anweisungen werden normalerweise als Platzhalter in Iterationsanweisungen oder als Anweisungen verwendet, um Bezeichnungen am Ende von Verbundanweisungen oder Funktionen zu platzieren.

Das folgende Codefragment zeigt, wie Sie eine Zeichenfolge zu einer anderen kopieren und die NULL-Anweisung integrieren:

```cpp
// null_statement.cpp
char *myStrCpy( char *Dest, const char *Source )
{
    char *DestStart = Dest;

    // Assign value pointed to by Source to
    // Dest until the end-of-string 0 is
    // encountered.
    while( *Dest++ = *Source++ )
        ;   // Null statement.

    return DestStart;
}

int main()
{
}
```

## <a name="see-also"></a>Siehe auch

[Ausdrucksanweisung](../cpp/expression-statement.md)