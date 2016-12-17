---
title: "PROC"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "PROC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROC directive"
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# PROC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Starten und Beenden eines Prozedurblocks Markierungen, der *Bezeichnung*aufgerufen wird.  Die Anweisungen im Block können mit der Aufrufanweisung oder den [AUFRUF](../../assembler/masm/invoke.md)\-Direktive aufgerufen werden.  
  
## Syntax  
  
```  
  
   label PROC [[distance]] [[langtype]] [[visibility]] [[<prologuearg>]]   
[[USES reglist]] [[, parameter [[:tag]]]]...  
[FRAME [:ehandler-address] ]  
statements  
label ENDP  
```  
  
## Hinweise  
 \[FRAME \[:*Ehandler ADDRESS*\]\] ist mit ml64.exe nur gültig und veranlasst MASM, einen Funktionstabelleneintrag in .pdata und Informationen in .xdata für Entladungs Verhalten der strukturierten Ausnahmebehandlung eine Funktion zu entladen.  
  
 Wenn das **FRAME**\-Attribut verwendet wird, muss es aus [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)\-Direktive folgen.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md) Weitere Informationen über die Verwendung von ml64.exe.  
  
## Beispiel  
  
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
  
 Der obige Code gibt die folgende Funktionstabelle und entlädt Informationen:  
  
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
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)