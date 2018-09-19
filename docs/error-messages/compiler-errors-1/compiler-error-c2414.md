---
title: Compilerfehler C2414 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2414
dev_langs:
- C++
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 642cb00605ed13146288edf5d39cb5d0c14c6e9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089917"
---
# <a name="compiler-error-c2414"></a>Compilerfehler C2414

Ungültige Operandenanzahl

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht. Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.

1. Neuere Prozessoren unterstützen die Anweisung mit einer unterschiedlichen Anzahl von Operanden. Anpassen der [/arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md) Option, um den neueren Prozessor zu verwenden.