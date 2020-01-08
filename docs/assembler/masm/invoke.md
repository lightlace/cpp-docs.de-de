---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: 7a005e5e70a2696ca89fb0ad1a3ff02aab8ffe5a
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317187"
---
# <a name="invoke"></a>INVOKE

(nur 32-Bit-MASM.) Ruft die Prozedur bei der von *Ausdruck*angegebenen Adresse auf und übergibt die Argumente auf dem Stapel oder in Registern gemäß den Standard Aufruf Konventionen des sprach Typs.     

## <a name="syntax"></a>Syntax

> *Ausdruck* aufrufen ⟦ __,__ *Argument* ... ⟧

## <a name="remarks"></a>Hinweise

Jedes Argument, das an die Prozedur übermittelt wird, kann ein Ausdruck, ein Registrierungs Paar oder ein Adress Ausdruck (ein Ausdruck mit vorangestelltem **addr**) sein.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
