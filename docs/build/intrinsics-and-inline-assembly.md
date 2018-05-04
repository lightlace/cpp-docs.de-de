---
title: Systeminterne Funktionen und Inlineassemblys | Microsoft Docs
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
ms.openlocfilehash: 5b8651bea0b1ee9f54ec0af704d92feef0722368
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="intrinsics-and-inline-assembly"></a>Systeminterne Funktionen und Inlineassemblys
Eine der Einschränkungen für die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] Compiler besteht darin, keine Inline-Assembler-Unterstützung. Das bedeutet, die Funktionen, die kann in C oder C++ geschrieben werden, entweder als Unterroutinen oder als systeminterne Funktionen unterstützt, die vom Compiler geschrieben werden müssen. Bestimmte Funktionen sind Leistung vertrauliche, andere hingegen nicht. Leistungsabhängigen Funktionen sollten als systeminterne Funktionen implementiert werden.  
  
 Die systeminternen Funktionen, die vom Compiler unterstützt werden in beschrieben [Compilerfunktionen](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)