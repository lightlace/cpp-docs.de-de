---
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: 92f14a352e5c177d767232eed36a7e705fd155ce
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317629"
---
# <a name="model-32-bit-masm"></a>. Modell (32-Bit-MASM)

Initialisiert das Programmspeichermodell. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **. Modell** *Speicher-Model* ⟦ __,__ *Language-Type*⟧ ⟦ __,__ *Stack-Option*⟧

### <a name="parameters"></a>Parameters

*Speichermodell*\
Erforderlicher Parameter, der die Größe von Code- und Datenzeigern bestimmt.

*Sprachtyp*\
Optionaler Parameter, der die Aufruf- und Namenskonventionen für Prozeduren und öffentliche Symbole festlegt.

*Stack-Option-* \
Optionaler Parameter.

*Stack-Option* wird nicht verwendet, wenn das *Speichermodell* **flach**ist.

Durch Angeben von **nearstack** wird das Stapel Segment zusammen mit Daten in einem einzelnen physischen Segment (**DGROUP**) gruppiert. Es wird davon ausgegangen, dass das Stapel Segment Register (**SS**) dieselbe Adresse wie das Daten Segment Register (**DS**) enthält. **Farstack** gruppiert den Stapel nicht mit **DGROUP**. Daher entspricht **SS** nicht der **DS**.

## <a name="remarks"></a>Hinweise

**. Das Modell** wird in [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md)nicht verwendet.

In der folgenden Tabelle werden die möglichen Werte für die einzelnen Parameter auf 16-Bit- und 32-Bit-Plattformen aufgelistet:

|Parameter|32-Bit-Werte|16-Bit-Werte (Support für frühere 16-Bit-Entwicklungen)|
|---------------|--------------------|----------------------------------------------------------------|
|*Speichermodell*|**Rate**|**winzig**, **klein**, **kompakt**, **Mittel**, **groß**,groß, **flach**|
|*Sprachtyp*|**C**, **StdCall**|**C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**|
|*Stack-Option*|Nicht verwendet|**nearstack**, **farstack**|

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

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
