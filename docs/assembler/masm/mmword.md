---
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: fd3b9f40b7ff9fa4dae570e0ed906c13a9456424
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75311922"
---
# <a name="mmword"></a>MMWORD

Wird für 64-Bit-Multimedia-Operanden mit MMX-und SSE (XMM)-Anweisungen verwendet.

## <a name="syntax"></a>Syntax

> **MMWORD**

## <a name="remarks"></a>Hinweise

**MMWORD** ist ein-Typ.  Vor dem Hinzufügen von **MMWORD** zu MASM konnte eine entsprechende Funktionalität mit folgenden Funktionen erzielt werden:

```asm
    mov mm0, qword ptr [ebx]
```

Obwohl beide Anweisungen auf 64-Bit-Operanden funktionieren, ist **QWORD** der Typ für 64-Bit-Ganzzahlen ohne Vorzeichen und **MMWORD** ist der Typ für einen multimediawert von 64-Bit.

**MMWORD** soll denselben Typ wie [__m64](../../cpp/m64.md)darstellen.

## <a name="example"></a>Beispiel

```asm
    movq     mm0, mmword ptr [ebx]
```

## <a name="see-also"></a>Siehe auch

[MASM-BNF-Grammatik](masm-bnf-grammar.md)
