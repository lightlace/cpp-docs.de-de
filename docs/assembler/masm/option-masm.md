---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: 0f90ab0115c3dde894d468bbbe60ffa0193b8336
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395167"
---
# <a name="option-masm"></a>OPTION (MASM)

Aktiviert und deaktiviert die Funktionen des Assemblers.

## <a name="syntax"></a>Syntax

> *Optionsliste* für Optionen

## <a name="remarks"></a>Hinweise

Zu den verfügbaren Optionen gehören:

|||||
|-|-|-|-|
|**CaseMap**|**Dotname**|**Nodotname**|**Ragend**|
|**Noemulator**|**Epilog**|**EXPR16**|**EXPR32**|
|**Kurse**|**Ljmp**|**Noljmp**|**M510**|
|**NOM510**|**Nokeyword**|**Nosignextend**|**Kompensieren**|
|**Oldmakros**|**Nooldmakros**|**Oldstructs**|**Nooldstructs**|
|**PROC**|**Prolog**|**ReadOnly**|**Noreadonly**|
|**Bereich**|**Im Gültigkeitsbereich**|**SEGMENT**|**SETIF2**.|

Die Syntax für language ist **options Sprache:** <em>x</em>, wobei *x* der Wert C, syscall, STDCALL, Pascal, Fortran oder Basic ist.  Syscall, Pascal, Fortran und Basic werden bei Verwendung mit nicht unterstützt [. Modell](../../assembler/masm/dot-model.md) flach.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
