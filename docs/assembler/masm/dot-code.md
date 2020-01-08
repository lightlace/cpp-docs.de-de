---
title: .CODE
ms.date: 12/17/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 0975e96e670400b7fa221ae2d1b9982b5cee613b
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75314145"
---
# <a name="code"></a>.CODE

(nur 32-Bit-MASM.) Bei Verwendung mit [. Model](dot-model.md)gibt den Anfang eines Code Segments an.

## <a name="syntax"></a>Syntax

> **. Code** ⟦*Name*⟧ \
> ⟦ *segmentitem* ⟧... \
> ⟦ *codesegmentnameid* wird **beendet**;; ⟧\

### <a name="parameters"></a>Parameters

*Name*\
Optionaler Parameter, der den Namen des Code Segments angibt. Der Standardname ist für kleine, kleine, kompakte und flache [Modelle](dot-model.md) **_text** . Der Standardname ist " *ModuleName*" _text für andere Modelle.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[. Daten](dot-data.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)

