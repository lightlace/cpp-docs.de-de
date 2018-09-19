---
title: Compilerfehler C3859 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3859
dev_langs:
- C++
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac06a09a6ad66384fd2b5423e3df046771f7653
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053388"
---
# <a name="compiler-error-c3859"></a>Compilerfehler C3859

Virtueller Speicherbereich für PCH wurde überschritten; kompilieren Sie erneut mit einer Befehlszeilenoption von -Zmvalue oder größer

Ihr vorkompilierter Header ist zu klein für die Menge an Daten, die der Compiler versucht einzufügen. Verwenden der **/Zm** Compiler-Flag, um einen höheren Wert für die vorkompilierte Headerdatei anzugeben. Weitere Informationen finden Sie unter [/Zm (Geben Sie vorkompilierte Header Begrenzung der Speicherzuweisung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).