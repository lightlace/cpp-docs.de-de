---
title: Makroersetzung
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 43dc9133c53b1c436c0df8c3db66ae8f18604222
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825847"
---
# <a name="macro-substitution"></a>Makroersetzung

Wenn *Macroname* aufgerufen wird, jedes Vorkommen von *string1* Zeichenfolge wird in der Definition durch ersetzt *Zeichenfolge2*.

## <a name="syntax"></a>Syntax

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Hinweise

Makroersetzung wird Groß-/Kleinschreibung beachtet und literal wird; *string1* und *Zeichenfolge2* Makros kann nicht aufgerufen werden. Ersetzen werden die ursprüngliche Definition nicht geändert werden. Sie können Text in jeder vordefinierte Makro außer ersetzen [ $$@ ](filename-macros.md).

Keine Leerzeichen oder Tabstopps vor dem Doppelpunkt befinden; nach dem Doppelpunkt werden als Literal interpretiert. Wenn *Zeichenfolge2* null festgelegt ist, alle Vorkommen von *string1* aus parameterdefinitions-Zeichenfolge des Makros gelöscht.

## <a name="see-also"></a>Siehe auch

[Verwenden eines NMAKE-Makros](using-an-nmake-macro.md)
