---
title: Compilerwarnung (Stufe 1) C4953 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0af5a16ebbf7851eceb2f2cd355f953b14c4bd38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4953"></a>Compilerwarnung (Stufe 1) C4953
Inlinee "function" wurde bearbeitet, seit die Konfigurationsdaten erfasst wurden. Die Profildaten werden nicht verwendet  
  
 Bei Verwendung von [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` neu kompiliert wurde und eine Funktion (***function***) aufweist, die bearbeitet wurde und die in vorhandenen Testläufen als Kandidat für Inlining identifiziert wurde. Infolge der Neukompilierung des Moduls ist die Funktion jedoch kein Kandidat für Inlining mehr.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.  
  
 Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.