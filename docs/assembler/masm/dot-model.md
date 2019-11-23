---
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: bfc114a6e71c0eb0ae70005c2657871b6c9e9692
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398110"
---
# <a name="model-32-bit-masm"></a>.MODEL (32-bit MASM)

Initialisiert das Programmspeichermodell. (32-bit MASM only.)

## <a name="syntax"></a>Syntax

> **.MODEL** *memory-model* ⟦ __,__ *language-type*⟧ ⟦ __,__ *stack-option*⟧

### <a name="parameters"></a>Parameter

*memory-model*\
Erforderlicher Parameter, der die Größe von Code- und Datenzeigern bestimmt.

*language-type*\
Optionaler Parameter, der die Aufruf- und Namenskonventionen für Prozeduren und öffentliche Symbole festlegt.

*stack-option*\
Optionaler Parameter.

*stack-option* is not used if *memory-model* is **FLAT**.

Specifying **NEARSTACK** groups the stack segment into a single physical segment (**DGROUP**) along with data. The stack segment register (**SS**) is assumed to hold the same address as the data segment register (**DS**). **FARSTACK** does not group the stack with **DGROUP**; thus **SS** does not equal **DS**.

## <a name="remarks"></a>Hinweise

**.MODEL** is not used in [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

In der folgenden Tabelle werden die möglichen Werte für die einzelnen Parameter auf 16-Bit- und 32-Bit-Plattformen aufgelistet:

|Parameter|32-Bit-Werte|16-Bit-Werte (Support für frühere 16-Bit-Entwicklungen)|
|---------------|--------------------|----------------------------------------------------------------|
|*memory-model*|**FLAT**|**TINY**, **SMALL**, **COMPACT**, **MEDIUM**, **LARGE**, **HUGE**, **FLAT**|
|*language-type*|**C**, **STDCALL**|**C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**|
|*stack-option*|Nicht verwendet|**NEARSTACK**, **FARSTACK**|

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

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
