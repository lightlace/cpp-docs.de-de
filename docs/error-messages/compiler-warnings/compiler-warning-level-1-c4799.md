---
title: Compilerwarnung (Stufe 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 475451b47d461e7ea1428eb715a876fb023694d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152215"
---
# <a name="compiler-warning-level-1-c4799"></a>Compilerwarnung (Stufe 1) C4799

> Keine EMMS-Funktion "*Funktion*"

Die Funktion verfügt über mindestens eine MMX-Anweisung, aber verfügt nicht über eine `EMMS` Anweisung. Wenn eine multimedia-Anweisung verwendet wird, eine `EMMS` Anweisung oder `_mm_empty` systeminterne sollte auch zum Deaktivieren Sie des Worts multimedia-Tag, am Ende der MMX-Code verwendet werden.

Sie erhalten möglicherweise C4799, bei der Verwendung von ivec.h, dass der Code nicht ordnungsgemäß verwendet wird, führen die EMMS-Anweisung vor der Rückgabe. Dies ist eine "false" Warnung für diese Header. Sie können Sie deaktivieren, indem _SILENCE_IVEC_C4799 in ivec.h definieren. Bedenken Sie jedoch, dass dies auch den Compiler aus, sodass richtige Warnungen dieses Typs beibehält.

Weitere Informationen finden Sie unter [Intel MMX-Befehlssatz](../../assembler/inline/intel-s-mmx-instruction-set.md).