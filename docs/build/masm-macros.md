---
title: MASM-Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 403220306a2585b1506a990664eaa2ec8f2ac1a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="masm-macros"></a>MASM-Makros
Um die Verwendung zu vereinfachen die [unformatierte Pseudooperationen](../build/raw-pseudo-operations.md), es gibt ein Satz von Makros, definiert in ksamd64.inc, bei der Erstellung der übliche Verfahren Prologe und Epiloge verwendet werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|alloc_stack(n)|Ordnet einen Stapelrahmen von n Bytes (mit Sub Rsp, n) und gibt die entsprechenden Informationen (.allocstack-n) entladen|  
|Save_reg Reg, Lokalisierung|Speichert einen nicht flüchtigen Register Reg auf dem Stapel am RSP-Offset Loc und gibt die entsprechenden Informationen zu entladen. (.savereg Reg, Loc)|  
|Push_reg reg|Verschiebt einen nicht flüchtigen Register Reg auf dem Stapel und gibt die entsprechenden Informationen zu entladen. (.pushreg Reg)|  
|Rex_push_reg reg|Speichern Sie ein nicht flüchtiges Register auf dem Stapel mit einem 2-Byte-Push und gibt die entsprechenden Informationen (.pushreg Reg), dies verwendet werden, sollte Wenn die Clientpushinstallation die erste Anweisung in der Funktion wird, um sicherzustellen, dass die Funktion während des Betriebs-patchfähigen wird, entladen.|  
|save_xmm128 Reg, Lokalisierung|Speichert einem nichtflüchtigen XMM registrieren Reg auf dem Stapel am RSP-Offset Loc und gibt die entsprechenden Informationen (savexmm128 Reg, Loc) entladen|  
|Set_frame Reg, offset|Legt die Frame-Register Reg werden RSP + offset (mit einer MOV- oder Lea) und gibt die entsprechenden Informationen (set_frame Reg, Offset) entladen|  
|push_eflags|Verschiebt Eflags mit einer Pushfq-Anweisung und gibt den entsprechenden entladen Informationen (. alloc_stack 8)|  
  
 Dies ist eine Beispiel-Funktionsprologs mit richtige Verwendung von Makros:  
  
```  
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