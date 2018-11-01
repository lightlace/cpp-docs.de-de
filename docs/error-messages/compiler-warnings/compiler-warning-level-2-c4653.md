---
title: Compilerwarnung (Stufe 2) C4653
ms.date: 11/04/2016
f1_keywords:
- C4653
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
ms.openlocfilehash: 664b1b3ec732c323d0074310902890cdd6eca9a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588593"
---
# <a name="compiler-warning-level-2-c4653"></a>Compilerwarnung (Stufe 2) C4653

die Compileroption "Option" inkonsistent mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert

Eine mit der vorkompilierte Header angegebene Option (["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md)) Option inkonsistent mit den Optionen, die beim Erstellen des vorkompilierten Headers angegeben. Dieser Kompilierung verwendet die Option beim Erstellen des vorkompilierten Headers angegeben werden.

Diese Warnung kann auftreten, wenn auf einen anderen Wert für die Option Pack Strukturen ([/Zp](../../build/reference/zp-struct-member-alignment.md)) während der Kompilierung des vorkompilierten Headers angegeben wurde.