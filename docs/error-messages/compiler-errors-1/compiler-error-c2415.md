---
title: Compilerfehler C2415 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2415
dev_langs:
- C++
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd889880997828396521ddba638bb606552e7d92
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112576"
---
# <a name="compiler-error-c2415"></a>Compilerfehler C2415

Ungültiger Operandentyp

Der Opcode verwendet keine Operanden dieses Typs.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht. Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.

1. Neuere Prozessoren unterstützen die Anweisung durch zusätzliche Typen. Anpassen der [/arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md) Option, um den neueren Prozessor zu verwenden.