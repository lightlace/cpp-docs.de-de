---
title: MASM-Makros
ms.date: 11/04/2016
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
ms.openlocfilehash: 8a00852a3a763aae5fda34d7e0fde664997a0bdb
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328824"
---
# <a name="masm-macros"></a>MASM-Makros

Um die Verwendung zu vereinfachen die [unformatierte Pseudooperationen](../build/raw-pseudo-operations.md), es gibt eine Reihe von Makros, definiert in ksamd64.inc, die verwendet werden kann, um typische Vorgehensweise Prologe und Epiloge zu erstellen.

## <a name="remarks"></a>Hinweise

|Makro|Beschreibung|
|-----------|-----------------|
|alloc_stack(n)|Weist einen Stapelrahmen von n Bytes (mit Sub Rsp, n), und gibt die entsprechenden Entladeinformationen aus (.allocstack-n)|
|Save_reg Reg, Lokalisierung|Speichert einen nicht flüchtigen Register Reg im Stapel auf RSP-Offset Loc und gibt die entsprechenden Entladeinformationen. (Reg .savereg, Loc)|
|Push_reg reg|Verschiebt ein nicht flüchtigen Register Reg auf dem Stapel und gibt die entsprechenden Entladeinformationen. (.pushreg Reg)|
|Rex_push_reg reg|Ein nicht flüchtiges Register speichern, auf dem Stapel mit einem Push-2-Byte und gibt die entsprechenden Entladeinformationen (.pushreg Reg) dies verwendet werden, sollte Wenn der Push-Vorgang die erste Anweisung in der Funktion ist, um sicherzustellen, dass die Funktion "heiß"-patchfähigen ist.|
|save_xmm128 Reg, Lokalisierung|Speichert einen permanenten XMM-Registers Reg im Stapel auf RSP-Offset Loc und gibt die entsprechenden Entladeinformationen aus (savexmm128 Reg, Loc)|
|Set_frame Reg, offset|Legt die Frame-Register Reg werden die RSP + offset (mithilfe einer MOV- oder Lea), und gibt die entsprechenden Entladeinformationen aus ("set_frame Reg", "Offset")|
|push_eflags|Verschiebt Eflags mit einer Pushfq-Anweisung aus, und gibt die entsprechenden Entladeinformationen aus (. alloc_stack 8)|

Hier ist eine Beispiel-Funktionsprologs mit richtiger Verwendung der Makros:

```asm
SkFrame struct
Fill    dq ?; fill to 8 mod 16
SavedRdi dq ?; saved register RDI
SavedRsi dq ?; saved register RSI
SkFrame ends

sampleFrame struct
Filldq?; fill to 8 mod 16
SavedRdidq?; Saved Register RDI
SavedRsi  dq?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
alloc_stack(sizeof sampleFrame)
save_reg rdi, sampleFrame.SavedRdi
save_reg rsi, sampleFrame.SavedRsi
.end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here’s the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="see-also"></a>Siehe auch

[Entladehilfen für MASM](../build/unwind-helpers-for-masm.md)