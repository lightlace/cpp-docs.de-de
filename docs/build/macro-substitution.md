---
title: Makroersetzung
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: d82aed5a34b7cafad0e40146470972dc6ff02424
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414680"
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
