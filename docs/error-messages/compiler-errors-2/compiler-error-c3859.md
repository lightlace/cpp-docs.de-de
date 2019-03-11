---
title: Compilerfehler C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 9b20224207ba797c6ee93c06404e4d90c3d02525
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738648"
---
# <a name="compiler-error-c3859"></a>Compilerfehler C3859

> Virtueller Speicherbereich für PCH wurde überschritten; Kompilieren Sie erneut mit einer Befehlszeilenoption von "-Zm*Wert*' oder höher

Die virtuelle speicherbelegung für Ihr vorkompilierter Header ist zu klein ist, für die Menge an Daten, die der Compiler versucht einzufügen. Ab Visual Studio 2015 die **/Zm** Empfehlung spielt nur bei Verwendung der `#pragma hdrstop` Richtlinie. In anderen Fällen ist es sich um einen falschen Fehler, Probleme der Windows virtuellen Speichers Druck.

Wenn Ihr vorkompilierte Header verwendet eine `#pragma hdrstop` Direktive, verwenden die **/Zm** Compiler-Flag, um einen höheren Wert für die vorkompilierte Headerdatei anzugeben. Erwägen Sie andernfalls, verringert die Anzahl der parallelen Kompilierungsprozesse in Ihrem Build. Weitere Informationen finden Sie unter [/Zm (Geben Sie vorkompilierte Header Begrenzung der Speicherzuweisung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
