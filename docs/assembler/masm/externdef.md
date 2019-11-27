---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 469b49832c171ee78336a0c457f0d269acd3b59d
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397543"
---
# <a name="externdef"></a>EXTERNDEF

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole namens *Name* , deren Typ *Type*ist.

## <a name="syntax"></a>Syntax

> **EXTERNDEF** ⟦*Language-Type*⟧ *Name* __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* __:__ *Type* ... ⟧

## <a name="remarks"></a>Hinweise

Wenn *Name* im Modul definiert ist, wird er als [öffentlich](../../assembler/masm/public-masm.md)behandelt. Wenn im Modul auf *Name* verwiesen wird, wird es als [extern](../../assembler/masm/extern-masm.md)behandelt. Wenn auf den *Namen* nicht verwiesen wird, wird er ignoriert. Der *Typ* kann " [ABS](../../assembler/masm/operator-abs.md)" lauten, wodurch der *Name* als Konstante importiert wird. Wird normalerweise in include-Dateien verwendet.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
