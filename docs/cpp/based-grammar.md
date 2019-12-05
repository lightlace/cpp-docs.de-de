---
title: __based-Grammatik
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: a8c923b5a111144c539b5bea1b2f47eb58dd1fbd
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857644"
---
# <a name="__based-grammar"></a>__based-Grammatik

**Microsoft-spezifisch**

Die basierende Adressierung ist nützlich, wenn eine genaue Kontrolle über das Segment erforderlich ist, in dem Objekte zugeordnet sind (statische und dynamische basierende Daten).

Die einzige Form der in 32-Bit-und 64-Bit-Kompilierungen akzeptablen basierten Adressierung ist "basierend auf einem Zeiger", die einen Typ definiert, der eine 32-Bit-oder 64-Bit-Verschiebung zu einer 32-Bit-oder einer 64-Bit-Basis oder auf " **void**" enthält.

## <a name="grammar"></a>Grammatik

*based-Range-Modifier*: **__based (**  *Basis Ausdruck*  **)**

*Basis Ausdruck*: *based-variablebased-Abstract-declaratorsegment-NameSEGMENT-Cast*

*based-Variable*: *Bezeichner*

*based-Abstract-declarator*: *abstract-declarator*

*Basistyp*: *Typname*

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[based-Zeiger](../cpp/based-pointers-cpp.md)