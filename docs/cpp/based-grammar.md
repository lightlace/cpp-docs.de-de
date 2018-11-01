---
title: __based-Grammatik
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 8dec9b0bcc7db25e2ec4c39b9d907922691bfc05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558144"
---
# <a name="based-grammar"></a>__based-Grammatik

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Die basierende Adressierung ist nützlich, wenn eine genaue Kontrolle über das Segment erforderlich ist, in dem Objekte zugeordnet sind (statische und dynamische basierende Daten).

Die einzige Form der basierenden Adressierung in 32-Bit- und 64-Bit-Kompilierungen zulässig ist "basiert auf einem Zeiger" definiert, die einen Typ, der eine 32-Bit oder 64-Bit-Verschiebung auf einen 32-Bit oder 64-Bit-Basis enthält oder basierend auf **"void"**.

## <a name="grammar"></a>Grammatik

*Basis-Range-Modifier*: **__based (***Basis-Expression***)** 

*Basis-Expression*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*Basis-Variable*: *Bezeichner*

*Basis-Abstract-Declarator*: *Abstract-Declarator*

*Basistyp*: *Typname*

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[based-Zeiger](../cpp/based-pointers-cpp.md)