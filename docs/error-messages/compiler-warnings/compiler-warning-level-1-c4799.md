---
title: Compilerwarnung (Stufe 1) C4799 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f888d6a941ad487ce122e46c43582e1c96525c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4799"></a>Compilerwarnung (Stufe 1) C4799  
  
> Keine EMMS am Ende der Funktion "*Funktion*"  
  
Die Funktion hat mindestens eine MMX-Anweisung, aber verfügt nicht über eine `EMMS` Anweisung. Wenn eine multimedia-Anweisung verwendet wird, ein `EMMS` Anweisung oder `_mm_empty` systeminterne sollte auch zum Löschen des Worts multimedia-Tag, am Ende der MMX-Code verwendet werden.  
  
Führen Sie die EMMS-Anweisung vor der Rückgabe Verwendung von ivec.h, dass der Code nicht ordnungsgemäß verwendet wird, erhalten Sie möglicherweise C4799. Dies ist eine "false" Warnung für diese Header. Sie können Sie deaktivieren, indem Sie _SILENCE_IVEC_C4799 in ivec.h definieren. Denken Sie jedoch, dass dadurch auch den Compiler beibehalten werden sollen, über das Erteilen der richtigen Warnungen dieses Typs.  
  
Weitere Informationen finden Sie unter [Intel MMX-Befehlssatz](../../assembler/inline/intel-s-mmx-instruction-set.md).