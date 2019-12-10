---
title: EXTERN (MASM)
ms.date: 12/06/2019
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 38ea50e75f2a8e19a7a99860f691904053b6739a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987858"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole namens *Name* , deren Typ *Type*ist.

## <a name="syntax"></a>Syntax

> **Extern** ⟦*Language-Type*⟧ *Name* ⟦ __(__ *altid* __)__ ⟧ __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* ⟦ __(__ *altid* __)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Hinweise

Das *Sprachtyp-* Argument ist nur in 32-Bit-MASM gültig.

Der *Typ* kann " [ABS](../../assembler/masm/operator-abs.md)" lauten, wodurch der *Name* als Konstante importiert wird. Identisch mit [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
