---
title: Systeminterne Funktionen und Inlineassemblys
ms.date: 11/04/2016
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
ms.openlocfilehash: 033225259c0a33414fe45eba313bb1f1c94eb379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515101"
---
# <a name="intrinsics-and-inline-assembly"></a>Systeminterne Funktionen und Inlineassemblys

Eine der Einschränkungen für die X64 Compiler nicht Inline-Assembler unterstützt werden. Dies bedeutet, die, die Funktionen, kann nicht in C oder C++ geschrieben werden, entweder als Unterroutinen oder als systeminterne Funktionen, die vom Compiler unterstützt geschrieben werden müssen. Bestimmte Funktionen sind leistungsabhängig, andere hingegen nicht. Leistungsorientierte Funktionen sollte als systeminterne Funktionen implementiert werden.

Die systeminternen Funktionen, die vom Compiler unterstützt werden, werden in beschrieben [intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md).

## <a name="see-also"></a>Siehe auch

[x64-Softwarekonventionen](../build/x64-software-conventions.md)