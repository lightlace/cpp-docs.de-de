---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 2cc5884a7473da9175a6b6af4b4251314deffeb4
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313391"
---
# <a name="externdef"></a>EXTERNDEF

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole namens *Name* , deren Typ *Type*ist.

## <a name="syntax"></a>Syntax

> **EXTERNDEF** ⟦*Language-Type*⟧ *Name* __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* __:__ *Type* ... ⟧

## <a name="remarks"></a>Hinweise

Das *Sprachtyp-* Argument ist nur in 32-Bit-MASM gültig.

Wenn *Name* im Modul definiert ist, wird er als [öffentlich](public-masm.md)behandelt. Wenn im Modul auf *Name* verwiesen wird, wird es als [extern](extern-masm.md)behandelt. Wenn auf den *Namen* nicht verwiesen wird, wird er ignoriert. Der *Typ* kann " [ABS](operator-abs.md)" lauten, wodurch der *Name* als Konstante importiert wird. Wird normalerweise in include-Dateien verwendet.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
