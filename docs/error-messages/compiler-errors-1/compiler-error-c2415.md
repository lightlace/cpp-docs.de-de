---
title: Compilerfehler C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: 81e2da31b39b323919132ae86cd365d9c119be32
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402956"
---
# <a name="compiler-error-c2415"></a>Compilerfehler C2415

Ungültiger Operandentyp

Der Opcode verwendet keine Operanden dieses Typs.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht. Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.

1. Neuere Prozessoren unterstützen die Anweisung durch zusätzliche Typen. Anpassen der [/arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md) Option, um den neueren Prozessor zu verwenden.