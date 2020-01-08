---
title: .PUSHREG
ms.date: 12/16/2019
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: de6ffd3668f47732144e8c632410f6dfde6b2f31
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318292"
---
# <a name="pushreg"></a>.PUSHREG

Generiert einen `UWOP_PUSH_NONVOL` Ladungs Code Eintrag für die angegebene Registernummer unter Verwendung des aktuellen Offsets im Prolog.

## <a name="syntax"></a>Syntax

> . Pushreg- *Register*

## <a name="remarks"></a>Hinweise

**. Pushreg** ermöglicht Benutzern von ml64. exe, anzugeben, wie sich eine Frame Funktion entlädt, und ist nur innerhalb des Prologs zulässig, der von der [proc](proc.md) **Frame** -Deklaration zum reicht [. ENDPROLOG](dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. Der pushreg** sollten Anweisungen vorangestellt werden, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

*Register* kann eine der folgenden sein: \
Rax | RCX | RDX | RBX | RDI | RSI | RBP | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden Beispiel wird gezeigt, wie Sie nicht flüchtige Register per Push übersetzen.

### <a name="code"></a>Code

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
