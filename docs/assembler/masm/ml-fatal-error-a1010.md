---
title: Schwerwiegender ML-Fehler A1010
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: b3141f8819a33281c70e34bd7772d4475886e557
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312585"
---
# <a name="ml-fatal-error-a1010"></a>Schwerwiegender ML-Fehler A1010

**fehlende Block Schachtelung:**

Ein Block Anfang hat kein entsprechendes Ende, oder für ein Block Ende war kein entsprechender Anfang vorhanden. Eine der folgenden Aktionen ist möglicherweise beteiligt:

- Eine Direktive auf hoher Ebene, z [. b. Wenn](dot-if.md), [. Wiederholen](dot-repeat.md)Sie oder [. Während](dot-while.md).

- Eine bedingte Assemblydirektive, z. b. [if](if-masm.md), [Repeat](repeat.md)oder **while**.

- Eine Struktur-oder Union-Definition.

- Eine Prozedur Definition.

- Eine Segment Definition.

- Eine [POPCONTEXT](popcontext.md) -Direktive.

- Eine bedingte Assemblydirektive, z. b. ein [else](else-masm.md)-, [ElseIf](elseif-masm.md)-oder **EndIf** -Direktive ohne übereinstimmendes [if](if-masm.md).

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)
