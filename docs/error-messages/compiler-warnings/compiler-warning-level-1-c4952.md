---
title: Compilerwarnung (Stufe 1) C4952 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f62f4c18380d89eb516a5fa49ef63e92ab79a6f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207150"
---
# <a name="compiler-warning-level-1-c4952"></a>Compilerwarnung (Stufe 1) C4952

> "*Funktion*": keine Profildaten gefunden wird, in der Programmdatenbank '*PDG-Datei*"

Bei Verwendung [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), der Compiler ein Eingabemodul, die nach der neu kompilierten `/LTCG:PGINSTRUMENT` und eine neue Funktion (*Funktion*) vorhanden.

Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.

Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.