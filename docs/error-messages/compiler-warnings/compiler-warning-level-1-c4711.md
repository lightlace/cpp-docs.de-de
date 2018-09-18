---
title: Compilerwarnung (Stufe 1) C4711 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4711
dev_langs:
- C++
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d184d5043dad1138f774ca7288a773bcc38c6d9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069942"
---
# <a name="compiler-warning-level-1-c4711"></a>Compilerwarnung (Stufe 1) C4711

' Funktion ' für die Inlineerweiterung ausgewählt

Der Compiler auf die angegebene Funktion inlining ausgeführt, obwohl es nicht für die markiert wurde inlining.

C4711 ist aktiviert, wenn [/Ob2](../../build/reference/ob-inline-function-expansion.md) angegeben ist.

Inlining wird nach Ermessen des Compilers ausgeführt. Diese Warnung dient nur zu Informationszwecken.

Diese Warnung ist standardmäßig deaktiviert. Verwenden Sie zum Aktivieren einer Warnung [#pragma-Warnung](../../preprocessor/warning.md). Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .