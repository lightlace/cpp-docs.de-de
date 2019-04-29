---
title: Schwerwiegender Fehler C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: 91753a49498548b4e523cd8564ee7a7ca7a3b373
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406950"
---
# <a name="fatal-error-c1076"></a>Schwerwiegender Fehler C1076

> Compilerlimit: Interne Heapgrenze erreicht; Verwenden Sie /Zm, um eine höhere Grenze anzugeben

Dieser Fehler kann durch zu viele Symbole oder Vorlageninstanziierungen verursacht werden. Ab Visual Studio 2015 können möglicherweise diese Meldung aus der Windows virtuellen arbeitsspeicherauslastung durch zu viele parallele Buildprozesse verursacht werden. In diesem Fall ist die Empfehlung, verwenden die **/Zm** Option ignoriert werden sollen, es sei denn, Sie verwenden eine `#pragma hdrstop` Richtlinie.

So beheben Sie diesen Fehler:

1. Wenn Ihr vorkompilierte Header verwendet eine `#pragma hdrstop` Direktive, verwenden die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) Option aus, um das Arbeitsspeicherlimit des Compilers auf den im angegebenen Wert festgelegt die [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) Fehlermeldung angezeigt. Weitere Informationen, die zum Festlegen dieses Werts in Visual Studio enthält, finden Sie im Abschnitt "Hinweise" in [/Zm (Geben Sie vorkompilierte Header Begrenzung der Speicherzuweisung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).

1. Reduzieren Sie die Anzahl von parallelen Prozessen angegeben, mit der **maxcpucount** Option aus, um MSBUILD. EXE-Datei in Verbindung mit der **/MP** Option aus, um CL. EXE-DATEI. Weitere Informationen finden Sie unter [Probleme für vorkompilierte Header (PCH) und Empfehlungen](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

1. Verwenden Sie in einem 64-Bit-Betriebssystem anstelle von gehosteten 32-Bit-Compilern gehostete 64-Bit-Compiler. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren eines 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. Löschen Sie überflüssige Includedateien.

1. Entfernen Sie unnötige globale Variablen, indem Sie beispielsweise Speicher dynamisch belegen, anstatt ein umfangreiches Array zu deklarieren.

1. Entfernen Sie nicht benötigte Deklarationen.

Wenn C1076 tritt auf, unmittelbar nachdem der Build gestartet wurde, der für Wert angegebene **/Zm** ist wahrscheinlich für das Programm zu hoch. Reduzieren der **/Zm** Wert.