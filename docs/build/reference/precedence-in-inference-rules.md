---
title: Vorrang in Rückschlussregeln
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: ca24134fd1829ad3d97ca67b8c30aae3af4109ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319680"
---
# <a name="precedence-in-inference-rules"></a>Vorrang in Rückschlussregeln

Wenn eine Rückschlussregel mehrfach definiert ist, verwendet NMAKE die Definition die höchsten Rangfolge aus. Die folgende Liste zeigt die Reihenfolge der Rangfolge von oben nach unten:

1. Eine Rückschlussregel in einem Makefile definiert. höhere Definitionen haben Vorrang vor.

1. Eine Rückschlussregel in Tools.ini definiert. höhere Definitionen haben Vorrang vor.

1. Eine vordefinierte Rückschlussregel.

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](inference-rules.md)
