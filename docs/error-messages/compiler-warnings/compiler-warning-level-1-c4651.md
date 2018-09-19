---
title: Compilerwarnung (Stufe 1) C4651 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b516ef86372901d00dd20d94ed10d5e361bbab8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099465"
---
# <a name="compiler-warning-level-1-c4651"></a>Compilerwarnung (Stufe 1) C4651

"Definition" für vorkompilierte Header, aber nicht für aktuelle Kompilierung angegeben

Die Definition wurde angegeben, wann der vorkompilierten Headerdatei generiert wurde, aber nicht in dieser Kompilierung.

Die Definition wird in der vorkompilierten Headerdatei, aber nicht in der Rest des Codes wirksam.

Wenn ein vorkompilierter Header mit DSYMBOL erstellt wurde, generiert der Compiler diese Warnung, wenn die Kompilierung von "/ Yu" DSYMBOL besitzt.  Die Befehlszeile "/ Yu" DSYMBOL hinzugefügt, wird diese Warnung aufgelöst.