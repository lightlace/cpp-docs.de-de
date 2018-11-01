---
title: Vorrang in Rückschlussregeln
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: 30dee54c99115c076f7662bafb8aa22d97f234fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548732"
---
# <a name="precedence-in-inference-rules"></a>Vorrang in Rückschlussregeln

Wenn eine Rückschlussregel mehrfach definiert ist, verwendet NMAKE die Definition die höchsten Rangfolge aus. Die folgende Liste zeigt die Reihenfolge der Rangfolge von oben nach unten:

1. Eine Rückschlussregel in einem Makefile definiert. höhere Definitionen haben Vorrang vor.

1. Eine Rückschlussregel in Tools.ini definiert. höhere Definitionen haben Vorrang vor.

1. Eine vordefinierte Rückschlussregel.

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](../build/inference-rules.md)