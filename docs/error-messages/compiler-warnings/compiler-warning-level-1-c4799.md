---
title: Compilerwarnung (Stufe 1) C4799 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4799
dev_langs: C++
helpviewer_keywords: C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f41535c01d67e28baa2569ace2684865407a1d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4799"></a>Compilerwarnung (Stufe 1) C4799  
  
> Keine EMMS am Ende der Funktion "*Funktion*"  
  
Die Funktion hat mindestens eine MMX-Anweisung, aber verfügt nicht über eine `EMMS` Anweisung. Wenn eine multimedia-Anweisung verwendet wird, ein `EMMS` Anweisung oder `_mm_empty` systeminterne sollte auch zum Löschen des Worts multimedia-Tag, am Ende der MMX-Code verwendet werden.  
  
Führen Sie die EMMS-Anweisung vor der Rückgabe Verwendung von ivec.h, dass der Code nicht ordnungsgemäß verwendet wird, erhalten Sie möglicherweise C4799. Dies ist eine "false" Warnung für diese Header. Sie können Sie deaktivieren, indem Sie _SILENCE_IVEC_C4799 in ivec.h definieren. Denken Sie jedoch, dass dadurch auch den Compiler beibehalten werden sollen, über das Erteilen der richtigen Warnungen dieses Typs.  
  
Weitere Informationen finden Sie unter [Intel MMX-Befehlssatz](../../assembler/inline/intel-s-mmx-instruction-set.md).