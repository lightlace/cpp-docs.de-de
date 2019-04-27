---
title: Compilerfehler C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 407ed4b30b55b63aa9bf36de9f8675a531d70534
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227107"
---
# <a name="compiler-error-c3744"></a>Compilerfehler C3744

__unhook muss wenigstens 3 Argumente für verwaltete Ereignisse haben.

Die [__unhook](../../cpp/unhook.md) Funktion muss drei Parameter, wenn in einem Programm verwendet werden soll, die Kompilierung für Managed Extensions for ausführen C++.

`__hook` und `__unhook` sind nicht kompatibel mit/CLR-Programmierung. Verwenden Sie stattdessen die Operatoren += und -=.

C3744 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.
