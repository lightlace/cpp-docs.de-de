---
title: PROC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- PROC
dev_langs:
- C++
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48eb872d394c3b131d32d4b41c5923883ff36cee
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="proc"></a>PROC
Kennzeichnet, Start- und Ende einer Prozedurblocks aufgerufen *Bezeichnung*. Die Anweisungen im Block können aufgerufen werden, mit der **Aufrufen** Anweisung oder [INVOKE](../../assembler/masm/invoke.md) Richtlinie.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   label PROC [[distance]] [[langtype]] [[visibility]] [[<prologuearg>]]   
[[USES reglist]] [[, parameter [[:tag]]]]...  
[FRAME [:ehandler-address] ]  
statements  
label ENDP  
```  
  
## <a name="remarks"></a>Hinweise  
 [FRAME [:*Ehandler Adresse*]] ist nur gültig, wenn ml64.exe und bewirkt, dass MASM, generieren eine Tabelle Funktionsstart im .pdata und Entladen von Informationen im .xdata für eine Funktion der strukturierten Ausnahmebehandlung entladen Verhalten.  
  
 Wenn die **FRAME** Attribut verwendet wird, es muss darauf folgen einer [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie.  
  
 Finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) für Weitere Informationen finden Sie unter ml64.exe.  
  
## <a name="example"></a>Beispiel  
  
```  
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
  
 Der obige Code wird ausgeben die folgenden Tabelle für die Funktionen und Informationen zu entladen:  
  
```  
FileHeader->Machine 34404  
Dumping Unwind Information for file ex2.exe  
  
.pdata entry 1 0x00001000 0x00001023  
  
  Unwind data: 0x00002000  
  
    Unwind version: 1  
    Unwind Flags: None  
    Size of prologue: 0x08  
    Count of codes: 3  
    Frame register: rbp  
    Frame offset: 0x0  
    Unwind codes:  
  
      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00  
      Code offset: 0x05, ALLOC_SMALL, size=0x10  
      Code offset: 0x01, PUSH_NONVOL, register=rbp  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)