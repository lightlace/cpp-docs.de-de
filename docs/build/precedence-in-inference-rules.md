---
title: Vorrang in Rückschlussregeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4f2e7ff55e935b7e425b552ba85f47f134c6b80
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725230"
---
# <a name="precedence-in-inference-rules"></a>Vorrang in Rückschlussregeln

Wenn eine Rückschlussregel mehrfach definiert ist, verwendet NMAKE die Definition die höchsten Rangfolge aus. Die folgende Liste zeigt die Reihenfolge der Rangfolge von oben nach unten:

1. Eine Rückschlussregel in einem Makefile definiert. höhere Definitionen haben Vorrang vor.

1. Eine Rückschlussregel in Tools.ini definiert. höhere Definitionen haben Vorrang vor.

1. Eine vordefinierte Rückschlussregel.

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](../build/inference-rules.md)