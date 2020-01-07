---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: a74a5336e626f561f1fc61e866792ce193332d84
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316537"
---
# <a name="assume"></a>ASSUME

Aktiviert die Fehlerüberprüfung für Registerwerte. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> *Segregister* __:__ *Name* ⟦ __,__ *segregister* __:__ *Name*... ⟧\
> *Dataregiester* __:__ *Type* ⟦ __,__ *dataregiester* __:__ *Type*... ⟧\
> *Register* __: Error__ ⟦ __,__ *Register* __: Error__... ⟧\
> **Angenommen** ⟦*Register* __:__ ⟧**Nothing** ⟦ __,__ *Register* __: Nothing__... ⟧

## <a name="remarks"></a>Hinweise

Wenn eine **Annahme** wirksam wird, überwacht der Assembler Änderungen an den Werten der angegebenen Register. **Fehler** generiert einen Fehler, wenn das Register verwendet wird. **Nothing** entfernt die Register Fehlerüberprüfung nicht. Sie können verschiedene Arten von Annahmen in einer Anweisung kombinieren.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
