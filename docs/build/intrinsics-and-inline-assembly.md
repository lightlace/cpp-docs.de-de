---
title: Systeminterne Funktionen und Inlineassemblys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a87e577af339099eda56a3b9d91929a05253a43
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716247"
---
# <a name="intrinsics-and-inline-assembly"></a>Systeminterne Funktionen und Inlineassemblys

Eine der Einschränkungen für die X64 Compiler nicht Inline-Assembler unterstützt werden. Dies bedeutet, die, die Funktionen, kann nicht in C oder C++ geschrieben werden, entweder als Unterroutinen oder als systeminterne Funktionen, die vom Compiler unterstützt geschrieben werden müssen. Bestimmte Funktionen sind leistungsabhängig, andere hingegen nicht. Leistungsorientierte Funktionen sollte als systeminterne Funktionen implementiert werden.

Die systeminternen Funktionen, die vom Compiler unterstützt werden, werden in beschrieben [intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md).

## <a name="see-also"></a>Siehe auch

[x64-Softwarekonventionen](../build/x64-software-conventions.md)