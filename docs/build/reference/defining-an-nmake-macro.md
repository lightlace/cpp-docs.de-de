---
title: Definieren eines NMAKE-Makros
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: b163c3dcbfb079a532bd1babca4ee881407bafc1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826168"
---
# <a name="defining-an-nmake-macro"></a>Definieren eines NMAKE-Makros

## <a name="syntax"></a>Syntax

```

macroname=string
```

## <a name="remarks"></a>Hinweise

Die *Macroname* ist eine Kombination aus Buchstaben, Ziffern und Unterstriche (_) bis zu 1.024 Zeichen und Fall sensible. Die *Macroname* kann ein aufgerufenes Makro enthalten. Wenn *Macroname* besteht ausschließlich aus einem aufgerufenen Makro, das Makro, das aufgerufen wird nicht null oder undefiniert sein.

Die `string` kann eine beliebige Sequenz von NULL oder mehr Zeichen sein. Eine null-Zeichenfolge enthält NULL-Zeichen oder nur Leerzeichen oder Tabstopps. Die `string` kann einen Makroaufruf enthalten.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Sonderzeichen in Makros](special-characters-in-macros.md)

[NULL und Undefinierte Makros](null-and-undefined-macros.md)

[Definieren von Makros](where-to-define-macros.md)

[Rangfolge bei Makrodefinitionen](precedence-in-macro-definitions.md)

## <a name="see-also"></a>Siehe auch

[Makros und NMAKE](macros-and-nmake.md)
