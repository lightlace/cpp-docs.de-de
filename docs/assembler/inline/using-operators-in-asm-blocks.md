---
title: Verwenden von Operatoren in __asm-Blöcken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca8ac739793c81ef18f8657cbf53c9cb018b3e38
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="using-operators-in-asm-blocks"></a>Verwenden von Operatoren in __asm-Blöcken
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Ein `__asm` Block können keine C- oder C++-spezifische Operatoren, wie z. B. die **<<** Operator. Allerdings Operatoren gemeinsame von C und MASM, z. B. die \* Operator als Assemblersprache Operatoren interpretiert werden. Beispielsweise außerhalb einer `__asm` blockieren, eckige Klammern (**[]**) wie der einschließende Arrayfeldindizes, C automatisch auf die Größe eines Elements im Array skaliert interpretiert werden. Innerhalb einer `__asm` Block, sind sie als den MASM-Index-Operator, der ergibt einen nicht skalierten Byte-Offset von einem Datenobjekt oder Bezeichnung (nicht nur ein Array) sichtbar. Der folgende Code veranschaulicht den Unterschied:  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 Der erste Verweis auf `array` wird nicht skaliert werden, aber die zweite ist. Beachten Sie, die Sie verwenden können, die **Typ** Operator, um die Skalierung zu erzielen auf Grundlage einer Konstante. Beispielsweise sind die folgenden Anweisungen äquivalent:  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)