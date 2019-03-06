---
title: Vorrang in Rückschlussregeln
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: 99d92985b00f7c05f409b43009eb61cec6d6f1b1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413276"
---
# <a name="precedence-in-inference-rules"></a>Vorrang in Rückschlussregeln

Wenn eine Rückschlussregel mehrfach definiert ist, verwendet NMAKE die Definition die höchsten Rangfolge aus. Die folgende Liste zeigt die Reihenfolge der Rangfolge von oben nach unten:

1. Eine Rückschlussregel in einem Makefile definiert. höhere Definitionen haben Vorrang vor.

1. Eine Rückschlussregel in Tools.ini definiert. höhere Definitionen haben Vorrang vor.

1. Eine vordefinierte Rückschlussregel.

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](../build/inference-rules.md)
