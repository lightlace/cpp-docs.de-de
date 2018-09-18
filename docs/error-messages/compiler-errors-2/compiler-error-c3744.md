---
title: Compilerfehler C3744 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d644a621fc6d8e460e1b97e5baec360de8662365
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063722"
---
# <a name="compiler-error-c3744"></a>Compilerfehler C3744

__unhook muss wenigstens 3 Argumente für verwaltete Ereignisse haben.

Die [__unhook](../../cpp/unhook.md) Funktion muss drei Parameter, wenn in einem Programm verwendet werden, die für Managed Extensions für C++ kompiliert wird ausführen.

`__hook` und `__unhook` sind nicht kompatibel mit/CLR-Programmierung. Verwenden Sie stattdessen die Operatoren += und -=.

C3744 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.
