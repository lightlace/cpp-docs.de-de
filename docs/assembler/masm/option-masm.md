---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: a8215bf1f816baa490a768fb2cab0b3c2e53e20b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217256"
---
# <a name="option-masm"></a>OPTION (MASM)

Aktiviert und deaktiviert die Funktionen des Assemblers.

## <a name="syntax"></a>Syntax

> OPTION *Optionlist*

## <a name="remarks"></a>Hinweise

Verfügbare Optionen sind:

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULATOR**|
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|
|**SPRACHE**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**PROLOG**|**READONLY**|**NOREADONLY**|
|**IM BEREICH EINER**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|

Die Syntax für die Sprache ist **OPTION Sprache:**<em>x</em>, wobei *x* ist einer der C, SYSCALL, STDCALL, PASCAL, FORTRAN oder BASIC.  SYSCALL, PASCAL, FORTRAN und BASIC werden nicht unterstützt mit der Verwendung [. Modell](../../assembler/masm/dot-model.md) Flatfile.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>