---
title: Compilerwarnung (Stufe 1) C4651
ms.date: 11/04/2016
f1_keywords:
- C4651
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
ms.openlocfilehash: 01e2472a547e73eda5fcc56952949a0d9611029f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393518"
---
# <a name="compiler-warning-level-1-c4651"></a>Compilerwarnung (Stufe 1) C4651

"Definition" für vorkompilierte Header, aber nicht für aktuelle Kompilierung angegeben

Die Definition wurde angegeben, wann der vorkompilierten Headerdatei generiert wurde, aber nicht in dieser Kompilierung.

Die Definition wird in der vorkompilierten Headerdatei, aber nicht in der Rest des Codes wirksam.

Wenn ein vorkompilierter Header mit DSYMBOL erstellt wurde, generiert der Compiler diese Warnung, wenn die Kompilierung von "/ Yu" DSYMBOL besitzt.  Die Befehlszeile "/ Yu" DSYMBOL hinzugefügt, wird diese Warnung aufgelöst.