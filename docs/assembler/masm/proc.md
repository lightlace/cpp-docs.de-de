---
title: PROC
ms.date: 08/30/2018
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: e7931c97570c0fefcacb0123d75934867793fba4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210533"
---
# <a name="proc"></a>PROC

Markiert die Anfang und Ende einer Prozedur-Block aufgerufen *Bezeichnung*. Die Anweisungen im Block können aufgerufen werden, mit der **Aufrufen** Anweisung oder [INVOKE](../../assembler/masm/invoke.md) Richtlinie.

## <a name="syntax"></a>Syntax

> *Bezeichnung* PROC [[*Abstand*]] [[*Langtype*]] [[*Sichtbarkeit*]] [[\<*Prologuearg*>]] [[ VERWENDET *Reglist*]] [[, *Parameter* [[:*Tag*]]]...<br/>
> [[FRAME [[:*Ehandler-Address*]]]]<br/>
> *statements*<br/>
> *label* ENDP

## <a name="remarks"></a>Hinweise

[[FRAME [[:*Ehandler-Address*]]]] ist nur gültig mit ml64.exe und bewirkt, dass MASM Funktionstabelleneintrag im .pdata-Datensatz zu generieren und Entladeinformationen in .xdata für eine Funktion der strukturierten Ausnahmebehandlung entladen Verhalten.

Wenn die **FRAME** Attribut wird verwendet, muss ihm durch einen [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie.

Finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) für Weitere Informationen zur Verwendung von ml64.exe.

## <a name="example"></a>Beispiel

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

Der obige Code wird in der folgenden Funktionstabelle ausgeben und Entladeinformationen:

```Output
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

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>