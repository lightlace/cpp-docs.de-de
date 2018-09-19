---
title: Compilerwarnung (Stufe 2) C4653 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4653
dev_langs:
- C++
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 376da24d4619eacc3e6b3defe8fdfc582800a898
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045977"
---
# <a name="compiler-warning-level-2-c4653"></a>Compilerwarnung (Stufe 2) C4653

die Compileroption "Option" inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert

Eine mit der vorkompilierte Header angegebene Option (["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md)) Option inkonsistent mit den Optionen, die beim Erstellen des vorkompilierten Headers angegeben. Dieser Kompilierung verwendet die Option beim Erstellen des vorkompilierten Headers angegeben werden.

Diese Warnung kann auftreten, wenn auf einen anderen Wert für die Option Pack Strukturen ([/Zp](../../build/reference/zp-struct-member-alignment.md)) während der Kompilierung des vorkompilierten Headers angegeben wurde.