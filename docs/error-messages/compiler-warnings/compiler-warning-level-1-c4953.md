---
title: Compilerwarnung (Stufe 1) C4953 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: 9e53808d4ad97bad4eccdf81b0a863277f8f7796
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194631"
---
# <a name="compiler-warning-level-1-c4953"></a>Compilerwarnung (Stufe 1) C4953

> Inlinee "*Funktion*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, Profildaten werden nicht verwendet

Bei Verwendung [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), der Compiler ein Eingabemodul, die nach der neu kompilierten `/LTCG:PGINSTRUMENT` und verfügt über eine Funktion (*Funktion*), die bearbeitet wurde und in vorhandenen Testläufen identifiziert die Funktion als Kandidat für inlining. Infolge der Neukompilierung des Moduls ist die Funktion jedoch kein Kandidat für Inlining mehr.

Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.

Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.