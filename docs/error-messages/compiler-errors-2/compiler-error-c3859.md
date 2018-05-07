---
title: Compilerfehler C3859 | Microsoft Docs
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
ms.openlocfilehash: d2f8c51f25c09881e10e980276fc2035a6a70aed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3859"></a>Compilerfehler C3859
Virtueller Speicherbereich für PCH wurde überschritten; kompilieren Sie erneut mit einer Befehlszeilenoption von -Zmvalue oder größer  
  
 Ihr vorkompilierter Header ist zu klein für die Menge an Daten, die der Compiler versucht einzufügen. Verwenden der **/Zm** Compilerflag einen größeren Wert für die vorkompilierte Headerdatei anzugeben. Weitere Informationen finden Sie unter [/Zm (Geben Sie vorkompilierte Header Speicherbelegung)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).