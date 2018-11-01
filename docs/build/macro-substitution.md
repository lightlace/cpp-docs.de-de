---
title: Makroersetzung
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 8daaa55418839fa969cf3a31efa092fcf21487e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616085"
---
# <a name="macro-substitution"></a>Makroersetzung

Wenn *Macroname* aufgerufen wird, jedes Vorkommen von *string1* Zeichenfolge wird in der Definition durch ersetzt *Zeichenfolge2*.

## <a name="syntax"></a>Syntax

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Hinweise

Makroersetzung wird Groß-/Kleinschreibung beachtet und literal wird; *string1* und *Zeichenfolge2* Makros kann nicht aufgerufen werden. Ersetzen werden die ursprüngliche Definition nicht geändert werden. Sie können Text in jeder vordefinierte Makro außer ersetzen [ $$@ ](../build/filename-macros.md).

Keine Leerzeichen oder Tabstopps vor dem Doppelpunkt befinden; nach dem Doppelpunkt werden als Literal interpretiert. Wenn *Zeichenfolge2* null festgelegt ist, alle Vorkommen von *string1* aus parameterdefinitions-Zeichenfolge des Makros gelöscht.

## <a name="see-also"></a>Siehe auch

[Verwenden eines NMAKE-Makros](../build/using-an-nmake-macro.md)