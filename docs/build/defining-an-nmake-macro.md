---
title: Definieren eines NMAKE-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c266a0be1c5ff16b719e9055f79b377d13ffbf3c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715707"
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

[Sonderzeichen in Makros](../build/special-characters-in-macros.md)

[NULL und Undefinierte Makros](../build/null-and-undefined-macros.md)

[Definieren von Makros](../build/where-to-define-macros.md)

[Rangfolge bei Makrodefinitionen](../build/precedence-in-macro-definitions.md)

## <a name="see-also"></a>Siehe auch

[Makros und NMAKE](../build/macros-and-nmake.md)