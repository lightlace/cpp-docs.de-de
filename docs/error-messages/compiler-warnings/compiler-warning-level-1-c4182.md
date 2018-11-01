---
title: Compilerwarnung (Stufe 1) C4182
ms.date: 11/04/2016
f1_keywords:
- C4182
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
ms.openlocfilehash: 49e3e2f62b4be50d14cb8da3d776b4640be7160c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486111"
---
# <a name="compiler-warning-level-1-c4182"></a>Compilerwarnung (Stufe 1) C4182

\#umfassen Schachtelungsebene ist "Anzahl" tief; Endlosschleife möglich

Dem Compiler stand aufgrund der Anzahl geschachtelter Includedateien kein Heapspeicherplatz mehr zur Verfügung. Eine Includedatei, die aus einer anderen Includedatei eingefügt wird, ist geschachtelt.

Diese Meldung dient zur Information und wird vor dem Fehler [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)ausgegeben.