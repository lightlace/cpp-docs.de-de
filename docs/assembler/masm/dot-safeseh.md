---
title: .SAFESEH
ms.date: 11/05/2019
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: 5953ad6bdf1d9d1b0070ce83dd1d764799b7440a
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317564"
---
# <a name="safeseh-32-bit-masm"></a>. SAFESEH (32-Bit-MASM)

Registriert eine Funktion als einen strukturierten Ausnahmehandler. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **. SAFESEH** - *Bezeichner*

## <a name="remarks"></a>Hinweise

der *Bezeichner* muss die ID für eine lokal [definierte Prozedur](proc.md) oder eine [EXTRN](extrn.md) -Prozedur sein. Eine [Bezeichnung](label-masm.md) ist nicht zulässig. Die. Die SAFESEH-Direktive erfordert die Befehlszeilenoption [/SAFESEH](ml-and-ml64-command-line-reference.md) ml. exe.

Weitere Informationen zu strukturierten Ausnahme Handlern finden Sie unter [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Um z. b. einen sicheren Ausnahmehandler zu registrieren, erstellen Sie eine neue MASM-Datei (wie folgt), assemblieren Sie mit/SAFESEH, und fügen Sie Sie den verknüpften Objekten hinzu.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
