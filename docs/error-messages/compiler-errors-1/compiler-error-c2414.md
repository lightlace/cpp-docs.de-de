---
title: Compilerfehler C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: 84fa715c8bd567770f361552e203a37c44ffdde4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402982"
---
# <a name="compiler-error-c2414"></a>Compilerfehler C2414

Ungültige Operandenanzahl

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht. Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.

1. Neuere Prozessoren unterstützen die Anweisung mit einer unterschiedlichen Anzahl von Operanden. Anpassen der [/arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md) Option, um den neueren Prozessor zu verwenden.