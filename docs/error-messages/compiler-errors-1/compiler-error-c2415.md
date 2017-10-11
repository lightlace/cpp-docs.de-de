---
title: Compilerfehler C2415 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2415
dev_langs:
- C++
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 68666ba203897b43fb1658525e1f342bcb923c09
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2415"></a>Compilerfehler C2415
Ungültiger Operandentyp  
  
 Der Opcode verwendet keine Operanden dieses Typs.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der Opcode unterstützt die Anzahl der verwendeten Operanden nicht. Lesen Sie in einem Assemblerreferenzhandbuch nach, wie viele Operanden zulässig sind.  
  
2.  Neuere Prozessoren unterstützen die Anweisung durch zusätzliche Typen. Anpassen der [/arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md) Option, um den neueren Prozessor verwenden.
