---
title: __based-Grammatik
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 8dec9b0bcc7db25e2ec4c39b9d907922691bfc05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393947"
---
# <a name="based-grammar"></a>__based-Grammatik

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Die basierende Adressierung ist nützlich, wenn eine genaue Kontrolle über das Segment erforderlich ist, in dem Objekte zugeordnet sind (statische und dynamische basierende Daten).

Die einzige Form der basierenden Adressierung in 32-Bit- und 64-Bit-Kompilierungen zulässig ist "basiert auf einem Zeiger" definiert, die einen Typ, der eine 32-Bit oder 64-Bit-Verschiebung auf einen 32-Bit oder 64-Bit-Basis enthält oder basierend auf **"void"**.

## <a name="grammar"></a>Grammatik

*based-range-modifier*: **__based(**  *base-expression*  **)**

*base-expression*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*Basis-Variable*: *Bezeichner*

*based-abstract-declarator*: *abstract-declarator*

*base-type*: *type-name*

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[based-Zeiger](../cpp/based-pointers-cpp.md)