---
title: .SAFESEH
ms.date: 08/30/2018
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: 417aea13518621f775cafa176ff7d74f9704d511
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178292"
---
# <a name="safeseh"></a>.SAFESEH

Registriert eine Funktion als strukturierte Ausnahmehandler.

## <a name="syntax"></a>Syntax

> . SAFESEH-Bezeichner

## <a name="remarks"></a>Hinweise

*Bezeichner* muss die ID für eine lokal definierte [PROC](../../assembler/masm/proc.md) oder [EXTRN](../../assembler/masm/extrn.md) Prozedur Ein [Bezeichnung](../../assembler/masm/label-masm.md) ist nicht zulässig. Die. SAFESEH-Anweisung erfordert die [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) Befehlszeilenoption "ml.exe".

Weitere Informationen zu strukturierten Ausnahmehandler, finden Sie unter [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Z. B. um eine sichere Ausnahmehandler registrieren, erstellen Sie eine neue MASM-Datei (wie folgt), mit/SAFESEH zusammenstellen Sie und die verknüpften Objekte hinzufügen.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>