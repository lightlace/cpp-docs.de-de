---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 324cf0e70a7ad619e5741c9acc18c24a72f54d13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397972"
---
# <a name="savereg"></a>.SAVEREG

Generiert entweder einen `UWOP_SAVE_NONVOL` oder einen `UWOP_SAVE_NONVOL_FAR` Entladungs Code Eintrag für das angegebene Register (*reg*) und den Offset (*Offset*) mithilfe des aktuellen prologoffsets. MASM wählt die effizienteste Codierung aus.

## <a name="syntax"></a>Syntax

> **. SAVEREG** *reg* __,__ *Offset*

## <a name="remarks"></a>Hinweise

**. Mit SAVEREG**können Benutzer von ml64. exe angeben, wie sich eine Frame Funktion entlädt und nur innerhalb des Prologs zulässig ist, der von der [proc](../../assembler/masm/proc.md) Frame-Deklaration zum reicht [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. SAVEREG** sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
