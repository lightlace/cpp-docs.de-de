---
title: Vorrang in Rückschlussregeln | Microsoft Docs
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
ms.openlocfilehash: 36d462d4222cbfc143dd7487d4cb6b1b8bb3ba3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="precedence-in-inference-rules"></a>Vorrang in Rückschlussregeln
Wenn eine Rückschlussregel mehrfach definiert ist, wird NMAKE die Definition die höchsten Rangfolge verwendet. Die folgende Liste zeigt die Reihenfolge der Priorität von der höchsten zur niedrigsten:  
  
1.  Eine Rückschlussregel in einem Makefile definiert. höhere Definitionen haben Vorrang vor.  
  
2.  Eine Rückschlussregel in Tools.ini definiert. höhere Definitionen haben Vorrang vor.  
  
3.  Eine vordefinierte Rückschlussregel.  
  
## <a name="see-also"></a>Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)