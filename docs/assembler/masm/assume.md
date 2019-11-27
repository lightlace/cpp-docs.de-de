---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 73ef8bcc33087a56747b80f94482fcd6c50e3bf6
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399269"
---
# <a name="assume-32-bit-masm"></a>Annahme (32-Bit-MASM)

Aktiviert die Fehlerüberprüfung für Registerwerte. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> *Segregister* __:__ *Name* ⟦ __,__ *segregister* __:__ *Name*... ⟧\
> *Dataregiester* __:__ *Type* ⟦ __,__ *dataregiester* __:__ *Type*... ⟧\
> *Register* __: Error__ ⟦ __,__ *Register* __: Error__... ⟧\
> **Angenommen** ⟦*Register* __:__ ⟧**Nothing** ⟦ __,__ *Register* __: Nothing__... ⟧

## <a name="remarks"></a>Hinweise

Wenn eine **Annahme** wirksam wird, überwacht der Assembler Änderungen an den Werten der angegebenen Register. **Fehler** generiert einen Fehler, wenn das Register verwendet wird. **Nothing** entfernt die Register Fehlerüberprüfung nicht. Sie können verschiedene Arten von Annahmen in einer Anweisung kombinieren.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
