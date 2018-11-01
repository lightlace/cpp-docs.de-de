---
title: Compilerfehler C3859
ms.date: 11/04/2016
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: be6ccaab49cb329e862fb6068af1337eddbaac8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490275"
---
# <a name="compiler-error-c3859"></a>Compilerfehler C3859

Virtueller Speicherbereich für PCH wurde überschritten; kompilieren Sie erneut mit einer Befehlszeilenoption von -Zmvalue oder größer

Ihr vorkompilierter Header ist zu klein für die Menge an Daten, die der Compiler versucht einzufügen. Verwenden der **/Zm** Compiler-Flag, um einen höheren Wert für die vorkompilierte Headerdatei anzugeben. Weitere Informationen finden Sie unter [/Zm (Geben Sie vorkompilierte Header Begrenzung der Speicherzuweisung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).