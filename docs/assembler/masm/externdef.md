---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: e757781151bd1bb57940e5c54f7333a5daa93c74
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987894"
---
# <a name="externdef"></a>EXTERNDEF

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole namens *Name* , deren Typ *Type*ist.

## <a name="syntax"></a>Syntax

> **EXTERNDEF** ⟦*Language-Type*⟧ *Name* __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* __:__ *Type* ... ⟧

## <a name="remarks"></a>Hinweise

Das *Sprachtyp-* Argument ist nur in 32-Bit-MASM gültig.

Wenn *Name* im Modul definiert ist, wird er als [öffentlich](../../assembler/masm/public-masm.md)behandelt. Wenn im Modul auf *Name* verwiesen wird, wird es als [extern](../../assembler/masm/extern-masm.md)behandelt. Wenn auf den *Namen* nicht verwiesen wird, wird er ignoriert. Der *Typ* kann " [ABS](../../assembler/masm/operator-abs.md)" lauten, wodurch der *Name* als Konstante importiert wird. Wird normalerweise in include-Dateien verwendet.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
