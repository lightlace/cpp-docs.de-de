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
ms.openlocfilehash: 4577bd5d76949dfb777a359c80d91814f1c45fe2
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703948"
---
# <a name="safeseh-32-bit-masm"></a>. SAFESEH (32-Bit-MASM)

Registriert eine Funktion als einen strukturierten Ausnahmehandler. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> . SAFESEH-Bezeichner

## <a name="remarks"></a>Hinweise

der *Bezeichner* muss die ID für eine lokal [definierte Prozedur](../../assembler/masm/proc.md) oder eine [EXTRN](../../assembler/masm/extrn.md) -Prozedur sein. Eine [Bezeichnung](../../assembler/masm/label-masm.md) ist nicht zulässig. Die. Die SAFESEH-Direktive erfordert die Befehlszeilenoption [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml. exe.

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

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>