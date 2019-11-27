---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: fc66338d90b54ecb12ef3ab1aa56214fb445cb13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397569"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole namens *Name* , deren Typ *Type*ist.

## <a name="syntax"></a>Syntax

> **Extern** ⟦*Language-Type*⟧ *Name* ⟦ __(__ *altid* __)__ ⟧ __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* ⟦ __(__ *altid* __)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Hinweise

Der *Typ* kann " [ABS](../../assembler/masm/operator-abs.md)" lauten, wodurch der *Name* als Konstante importiert wird. Identisch mit [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
