---
title: Compilerwarnung (Stufe 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: c2e9b88125655d9ea0abe3e65500b149289ba83b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393284"
---
# <a name="compiler-warning-level-1-c4952"></a>Compilerwarnung (Stufe 1) C4952

> "*Funktion*": keine Profildaten gefunden wird, in der Programmdatenbank '*PDG-Datei*"

Bei der Verwendung von [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` erneut kompiliert wurde und eine neue Funktion (*Funktion*) aufweist.

Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.

Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.