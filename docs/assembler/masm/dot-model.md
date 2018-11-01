---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: 5c7d5a1cfe16ef3cb1d79617133cd1ceccdfb78c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633508"
---
# <a name="model"></a>.MODEL

Initialisiert das Speichermodell der Anwendung an.

## <a name="syntax"></a>Syntax

> . Modell Memorymodel [[, Langtype]] [[, Stackoption]]

### <a name="parameters"></a>Parameter

*memorymodel*<br/>
Erforderlicher Parameter, der bestimmt, die Größe der Zeiger für Code und Daten.

*langtype*<br/>
Optionaler Parameter, der die aufrufenden und der naming-Konventionen für die Prozeduren und die öffentlichen Symbole festlegt.

*stackoption*<br/>
Optionaler Parameter.

*Stackoption* wird nicht verwendet werden, wenn *Memorymodel* ist `FLAT`.

Angeben von `NEARSTACK` das Stack-Segment in einem einzigen physischen Segment gruppiert (`DGROUP`) zusammen mit Daten. Das Stapelregister-Segment (`SS`) wird davon ausgegangen, dass die gleiche Adresse wie dem Datenregister-Segment enthalten (`DS`). `FARSTACK` den Stapel mit werden nicht gruppiert `DGROUP`; daher `SS` ist nicht gleich `DS`.

## <a name="remarks"></a>Hinweise

.`MODEL` werden nicht in [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

Die folgende Tabelle enthält die möglichen Werte für jeden Parameter aus, wenn 16-Bit- und 32-Bit-Zielplattformen:

|Parameter|32-Bit-Werten|16-Bit-Werte (Unterstützung für ältere 16-Bit-Entwicklung)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|Nicht verwendet|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>Code

MASM-bezogene Beispiele herunterladen Sie die Compiler-Beispiele von [Visual C++-Beispiele und die zugehörige Dokumentation für Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749).

Das folgende Beispiel zeigt die Verwendung der `.MODEL` Richtlinie.

## <a name="example"></a>Beispiel

```asm
; file simple.asm
; For x86 (32-bit), assemble with debug information:
;   ml -c -Zi simple.asm
; For x64 (64-bit), assemble with debug information:
;   ml64 -c -DX64 -Zi simple.asm
;
; In this sample, the 'X64' define excludes source not used
;  when targeting the x64 architecture

ifndef X64
.686p
.XMM
.model flat, C
endif

.data
; user data

.code
; user code

fxn PROC public
  xor eax, eax ; zero function return value
  ret
fxn ENDP

end
```

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>

