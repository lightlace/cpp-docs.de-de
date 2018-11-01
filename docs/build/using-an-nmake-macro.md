---
title: Verwenden eines NMAKE-Makros
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: 9d8ff76e1e730b65db363749797ef9ae2062adab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645080"
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