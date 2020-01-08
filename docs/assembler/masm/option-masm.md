---
title: OPTION (MASM)
ms.date: 12/17/2019
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: bd50ac2e051db7f02ac077054e5856524745df54
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318747"
---
# <a name="option"></a>OPTION

Aktiviert und deaktiviert die Funktionen des Assemblers.

## <a name="syntax"></a>Syntax

> *Optionsliste* für Optionen

## <a name="remarks"></a>Hinweise

Folgende Optionen sind verfügbar:

|||||
|-|-|-|-|
|**CaseMap**|**DOTNAME**|**NODOTNAME**|**Ragend**|
|**Noemulator**|**Epilog**|**EXPR16**|**EXPR32**|
|**LANGUAGE**|**LJMP**|**Noljmp**|**M510**|
|**NOM510**|**Nokeyword**|**Nosignextend**|**OFFSET**|
|**OLDMACROS**|**Nooldmakros**|**OLDSTRUCTS**|**Nooldstructs**|
|**PROC**|**Prolog**|**ReadOnly**|**Noreadonly**|
|**Bereich**|**Im Gültigkeitsbereich**|**SEGMENT**|**SETIF2**.|

Die Syntax für language ist **options Sprache:** <em>x</em>, wobei *x* der Wert C, syscall, STDCALL, Pascal, Fortran oder Basic ist.  Syscall, Pascal, Fortran und Basic werden bei nicht unterstützt [. Modell](dot-model.md) flach.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
