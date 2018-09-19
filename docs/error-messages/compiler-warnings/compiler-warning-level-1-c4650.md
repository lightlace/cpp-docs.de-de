---
title: Compilerwarnung (Stufe 1) C4650 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d49b21452465f26d6e696f928c04c20dc0e33307
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052886"
---
# <a name="compiler-warning-level-1-c4650"></a>Compilerwarnung (Stufe 1) C4650

die Debuginformationen nicht in vorkompilierter Headerdatei vorhanden; nur globale Symbole aus dieser Datei werden verfügbar sein.

Die vorkompilierte Headerdatei wurde nicht mit Microsoft symbolische Debuginformationen kompiliert.

Wenn verknüpft, berücksichtigt die resultierende ausführbare Datei oder eine Dynamic Link Library-Datei keine Debuginformationen für das lokale Symbole in der vorkompilierten Headerdatei.

Diese Warnung kann vermieden werden, durch das erneute Kompilieren der vorkompilierten Headerdatei mit dem ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) Befehlszeilenoption.