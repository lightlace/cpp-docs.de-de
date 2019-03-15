---
title: Verwenden eines NMAKE-Makros
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: fb3b154ba8b30bbfc9a6c7c6b37720e5c60d6327
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825775"
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

[Makroersetzung](macro-substitution.md)

## <a name="see-also"></a>Siehe auch

[Makros und NMAKE](macros-and-nmake.md)
