---
title: Compilerfehler C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 407ed4b30b55b63aa9bf36de9f8675a531d70534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516232"
---
# <a name="compiler-error-c3744"></a>Compilerfehler C3744

__unhook muss wenigstens 3 Argumente für verwaltete Ereignisse haben.

Die [__unhook](../../cpp/unhook.md) Funktion muss drei Parameter, wenn in einem Programm verwendet werden, die für Managed Extensions für C++ kompiliert wird ausführen.

`__hook` und `__unhook` sind nicht kompatibel mit/CLR-Programmierung. Verwenden Sie stattdessen die Operatoren += und -=.

C3744 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.
