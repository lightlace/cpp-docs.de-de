---
title: Compilerwarnung C4746
ms.date: 11/04/2016
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
ms.openlocfilehash: 1b79eed2134b8c6310e508e56b3388c6f38fe4b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311107"
---
# <a name="compiler-warning-c4746"></a>Compilerwarnung C4746

flüchtiger Zugriff auf "\<Ausdruck >" / volatile unterliegt: [Iso&#124;ms] festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen.

C4746 wird ausgegeben, wenn eine flüchtige Variable direkt zugegriffen wird. Es soll ermöglicht es Entwicklern, die Codepositionen zu identifizieren, die von der bestimmten flüchtiges Modell, die aktuell angegebene betroffen sind (das kann gesteuert werden, mit der [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption). Insbesondere kann es hilfreich sein beim Suchen von vom Compiler generierter hardwarearbeitsspeicherbarrieren, wenn angegebenem verwendet wird.

Die systeminternen "__iso_volatile_load/Store" Funktionen können verwendet werden, auf explizit flüchtigen Speicher zugreifen, ohne von den flüchtiges Modell betroffen sind. Verwenden diese systeminternen Funktionen wird C4746 nicht ausgelöst.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .