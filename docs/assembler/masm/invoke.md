---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: a5175252364918ca218e81536b29f084f7fd19cc
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397298"
---
# <a name="invoke-32-bit-masm"></a>Aufrufen (32-Bit-MASM)

Ruft die Prozedur bei der von *Ausdruck*angegebenen Adresse auf und übergibt die Argumente auf dem Stapel oder in Registern gemäß den Standard Aufruf Konventionen des sprach Typs. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> *Ausdruck* aufrufen ⟦ __,__ *Argument* ... ⟧

## <a name="remarks"></a>Hinweise

Jedes Argument, das an die Prozedur übermittelt wird, kann ein Ausdruck, ein Registrierungs Paar oder ein Adress Ausdruck (ein Ausdruck mit vorangestelltem **addr**) sein.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](../../assembler/masm/directives-reference.md)
