---
title: Compilerwarnung (Stufe 1) C4799 | Microsoft-Dokumentation
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
ms.openlocfilehash: b3d83917289e5ad76a874587894a66e163fed90a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088227"
---
# <a name="compiler-warning-level-1-c4799"></a>Compilerwarnung (Stufe 1) C4799

> Keine EMMS-Funktion "*Funktion*"

Die Funktion verfügt über mindestens eine MMX-Anweisung, aber verfügt nicht über eine `EMMS` Anweisung. Wenn eine multimedia-Anweisung verwendet wird, eine `EMMS` Anweisung oder `_mm_empty` systeminterne sollte auch zum Deaktivieren Sie des Worts multimedia-Tag, am Ende der MMX-Code verwendet werden.

Sie erhalten möglicherweise C4799, bei der Verwendung von ivec.h, dass der Code nicht ordnungsgemäß verwendet wird, führen die EMMS-Anweisung vor der Rückgabe. Dies ist eine "false" Warnung für diese Header. Sie können Sie deaktivieren, indem _SILENCE_IVEC_C4799 in ivec.h definieren. Bedenken Sie jedoch, dass dies auch den Compiler aus, sodass richtige Warnungen dieses Typs beibehält.

Weitere Informationen finden Sie unter [Intel MMX-Befehlssatz](../../assembler/inline/intel-s-mmx-instruction-set.md).