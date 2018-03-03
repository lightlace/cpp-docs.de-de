---
title: Systeminterne Funktionen und Inlineassemblys | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80eb16eb7fde49c499227bb3d60000e2ac6e5143
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="intrinsics-and-inline-assembly"></a>Systeminterne Funktionen und Inlineassemblys
Eine der Einschränkungen für die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] Compiler besteht darin, keine Inline-Assembler-Unterstützung. Das bedeutet, die Funktionen, die kann in C oder C++ geschrieben werden, entweder als Unterroutinen oder als systeminterne Funktionen unterstützt, die vom Compiler geschrieben werden müssen. Bestimmte Funktionen sind Leistung vertrauliche, andere hingegen nicht. Leistungsabhängigen Funktionen sollten als systeminterne Funktionen implementiert werden.  
  
 Die systeminternen Funktionen, die vom Compiler unterstützt werden in beschrieben [Compilerfunktionen](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)