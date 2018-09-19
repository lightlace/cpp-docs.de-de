---
title: Compilerwarnung C4746 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6abce7ebbcdc41effed05ccf54337e3976c34e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054863"
---
# <a name="compiler-warning-c4746"></a>Compilerwarnung C4746

flüchtiger Zugriff auf "\<Ausdruck >" / volatile unterliegt: [Iso&#124;ms] festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen.

C4746 wird ausgegeben, wenn eine flüchtige Variable direkt zugegriffen wird. Es soll ermöglicht es Entwicklern, die Codepositionen zu identifizieren, die von der bestimmten flüchtiges Modell, die aktuell angegebene betroffen sind (das kann gesteuert werden, mit der [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption). Insbesondere kann es hilfreich sein beim Suchen von vom Compiler generierter hardwarearbeitsspeicherbarrieren, wenn angegebenem verwendet wird.

Die systeminternen "__iso_volatile_load/Store" Funktionen können verwendet werden, auf explizit flüchtigen Speicher zugreifen, ohne von den flüchtiges Modell betroffen sind. Verwenden diese systeminternen Funktionen wird C4746 nicht ausgelöst.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .