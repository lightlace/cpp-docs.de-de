---
title: Aufrufen von C++-Funktionen in der Inlineassembly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c91829eac3247255d8fe3cb966a61fca5319f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="calling-c-functions-in-inline-assembly"></a>Aufrufen von C++-Funktionen in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Ein `__asm` Block kann nur globale C++ Funktionen aufzurufen, die nicht überladen werden. Wenn Sie eine globale überladene C++-Funktion oder eine C++-Memberfunktion aufrufen, gibt der Compiler einen Fehler aus.  
  
 Sie können auch alle mit deklarierten Funktionen aufrufen **"extern"C""** Verknüpfung. Dies ermöglicht eine `__asm` Block innerhalb eines C++-Programms die C-Bibliotheksfunktionen aufrufen, da es sich bei die standardmäßigen Headerdateien die Bibliotheksfunktionen haben deklarieren **"extern"C""** Verknüpfung.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)