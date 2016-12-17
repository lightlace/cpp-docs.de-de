---
title: "MASM-Makros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# MASM-Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um die Verwendung von [Unformatierte Pseudooperationen](../build/raw-pseudo-operations.md) zu vereinfachen, stehen Makros zur Verfügung, die in ksamd64.inc definiert sind und zum Erstellen typischer Prologe und Epiloge für eine Prozedur verwendet werden können.  
  
## Hinweise  
  
|Makro|Beschreibung|  
|-----------|------------------|  
|alloc\_stack\(n\)|Weist einen Stapelrahmen mit n Byte zu \(unter Verwendung von sub rsp, n\) und gibt die entsprechenden Entladeinformationen aus \(.allocstack n\).|  
|save\_reg reg, loc|Speichert ein nicht flüchtiges Register reg am RSP\-Offset loc im Stapel und gibt die entsprechenden Entladeinformationen aus.  \(.savereg reg, loc\)|  
|push\_reg reg|Verschiebt ein nicht flüchtiges Register reg in den Stapel und gibt die entsprechenden Entladeinformationen aus.  \(.pushreg reg\)|  
|rex\_push\_reg reg|Speichern Sie ein nicht flüchtiges Register auf dem Stapel mit einem 2\-Byte\-Pushs Ausgaben, und die entsprechenden Entladungsinformationen \(.pushreg\-Reg\) dieses sollten verwendet werden, wenn der Push die erste Anweisung in der Funktion ist, sicherzustellen, dass die Funktion heiß\-patchable ist.|  
|save\_xmm128 reg, loc|Speichert ein nicht flüchtiges XMM\-Register reg am RSP\-Offset loc auf dem Stapel und gibt die entsprechenden Entladeinformationen aus \(.savexmm128 reg, loc\).|  
|set\_frame reg, offset|Legt das Frameregister reg auf RSP \+ offset fest \(mit einer mov\- oder lea\-Anweisung\) und gibt die entsprechenden Entladeinformationen aus \(.set\_frame reg, offset\).|  
|push\_eflags|Verschiebt eflags mit einer pushfq\-Anweisung und gibt die entsprechenden Entladeinformationen aus \(.alloc\_stack 8\).|  
  
 Im Folgenden finden Sie einen Beispielfunktionsprolog mit richtiger Verwendung der Makros:  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
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
  
## Siehe auch  
 [Entladehilfen für MASM](../build/unwind-helpers-for-masm.md)