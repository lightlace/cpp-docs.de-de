---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: c409bf10a2f863c380cda6b4822583ffb3787da6
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934092"
---
# <a name="model"></a>.MODEL

Initialisiert das Programmspeichermodell.

## <a name="syntax"></a>Syntax

> .MODEL memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>Parameter

*memorymodel*<br/>
Erforderlicher Parameter, der die Größe von Code- und Datenzeigern bestimmt.

*langtype*<br/>
Optionaler Parameter, der die Aufruf- und Namenskonventionen für Prozeduren und öffentliche Symbole festlegt.

*stackoption*<br/>
Optionaler Parameter.

Der Parameter *stackoption* wird nicht verwendet, wenn *memorymodel* den Wert `FLAT` aufweist.

Wenn `NEARSTACK` angegeben wird, werden die Stapelsegmente zusammen mit Daten in ein Segment (`DGROUP`) gruppiert. Es wird angenommen, dass das Stapelsegmentregister (`SS`) dieselbe Adresse wie das Datensegmentregister (`DS`) beinhaltet. `FARSTACK` gruppiert den Stapel nicht mithilfe von `DGROUP`. Daher entspricht `SS` nicht `DS`.

## <a name="remarks"></a>Anmerkungen

.`MODEL` wird in [MASM für x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) nicht verwendet.

In der folgenden Tabelle werden die möglichen Werte für die einzelnen Parameter auf 16-Bit- und 32-Bit-Plattformen aufgelistet:

|Parameter|32-Bit-Werte|16-Bit-Werte (Support für frühere 16-Bit-Entwicklungen)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|Nicht verwendet|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>Code

Beispiele zu MASM finden Sie in den Compilerbeispielen, die Sie unter [Visual C++ Samples and Related Documentation for Visual Studio 2010 (Visual C++-Beispiele und passende Dokumentation für Visual Studio 2010)](https://go.microsoft.com/fwlink/p/?linkid=178749) herunterladen können.

Im folgenden Beispiel wird die Verwendung der `.MODEL`-Anweisung gezeigt.

## <a name="example"></a>Beispiel

```asm
; file simple.asm
; For x86 (32-bit), assemble with debug information:
;   ml -c -Zi simple.asm
; For x64 (64-bit), assemble with debug information:
;   ml64 -c -DX64 -Zi simple.asm
;
; In this sample, the 'X64' define excludes source not used
;  when targeting the x64 architecture

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
