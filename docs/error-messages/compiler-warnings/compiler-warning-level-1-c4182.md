---
title: Compilerwarnung (Stufe 1) C4182
ms.date: 11/04/2016
f1_keywords:
- C4182
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
ms.openlocfilehash: 49e3e2f62b4be50d14cb8da3d776b4640be7160c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391633"
---
# <a name="compiler-warning-level-1-c4182"></a>Compilerwarnung (Stufe 1) C4182

\#umfassen Schachtelungsebene ist "Anzahl" tief; Endlosschleife möglich

Dem Compiler stand aufgrund der Anzahl geschachtelter Includedateien kein Heapspeicherplatz mehr zur Verfügung. Eine Includedatei, die aus einer anderen Includedatei eingefügt wird, ist geschachtelt.

Diese Meldung dient zur Information und wird vor dem Fehler [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)ausgegeben.