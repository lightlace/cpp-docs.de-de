---
title: __based-Grammatik | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43e9074de25d8cb914432123478f5f338ff4ba1e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103763"
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