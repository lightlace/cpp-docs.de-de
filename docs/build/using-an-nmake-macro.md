---
title: Verwenden eines NMAKE-Makros
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: a5f0fb9b13c5d5647b8f4ee382951df6282e8d68
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415642"
---
# <a name="using-an-nmake-macro"></a>Verwenden eines NMAKE-Makros

Um ein Makro zu verwenden, schließen Sie den Namen in Klammern, die wie folgt durch ein Dollarzeichensymbol ($) vorangestellt.

## <a name="syntax"></a>Syntax

```
$(macroname)
```

## <a name="remarks"></a>Hinweise

Es sind keine Leerzeichen zulässig. Die Klammern sind optional, wenn *Macroname* ist ein einzelnes Zeichen. Die parameterdefinitions-Zeichenfolge ersetzt $(*Macroname*); ein nicht definiertes Makro wird durch eine null-Zeichenfolge ersetzt.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Makroersetzung](../build/macro-substitution.md)

## <a name="see-also"></a>Siehe auch

[Makros und NMAKE](../build/macros-and-nmake.md)
