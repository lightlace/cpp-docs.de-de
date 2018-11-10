---
title: C - Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
ms.openlocfilehash: 8d45ce34457779e668124d9f48b82a5b74da1c56
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506845"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C - Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation

Operanden der Postfix-Inkrement- und Postfix-Dekrementoperatoren sind skalare Typen, die änderbare L-Werte sind.

## <a name="syntax"></a>Syntax

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

Das Ergebnis des Postfix-Inkrementoperators oder Postfix-Dekrementoperators ist der Wert des Operanden. Nachdem das Ergebnis erreicht ist, wird der Wert des Operanden (erhöht oder verringert). Der folgende Code veranschaulicht den Postfix-Inkrementoperator.

```
if( var++ > 0 )
    *p++ = *q++;
```

In diesem Beispiel wird die Variable `var` mit 0 verglichen und dann erhöht. Wenn `var` vor der Erhöhung positiv war, wird die nächste Anweisung ausgeführt. Zuerst wird der Wert des Objekts, auf das durch `q` gezeigt wird, dem Objekt zugewiesen, auf das durch `p` gezeigt wird. Anschließend werden `q` und `p` erhöht.

## <a name="see-also"></a>Siehe auch

[Inkrementierungs- und Dekrementierungsoperatoren in Postfixnotation: ++ und --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)