---
title: EVEN- und ALIGN-Anweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- align
- EVEN
dev_langs:
- C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06a1007c50e3490e5b14e4da886494557be0d37e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688300"
---
# <a name="even-and-align-directives"></a>EVEN- und ALIGN-Anweisungen

**Microsoft-spezifisch**

Obwohl der Inlineassembler von den meisten MASM-makroanweisungen unterstützt, unterstützt es `EVEN` und **AUSRICHTEN**. Fügen Sie diese Direktiven **NOP** (kein Vorgang) Anweisungen in der Code für die Assembly nach Bedarf, um Bezeichnungen zu bestimmten Grenzen ausgerichtet. Dies wird Anweisung-Abrufvorgänge für einige Prozessoren effizienter.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>