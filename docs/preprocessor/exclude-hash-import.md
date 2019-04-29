---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: d6a320089d5954b2cf1d0d96ae1f37656f2ddd58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389319"
---
# <a name="exclude-import"></a>Ausschließen (\#importieren)

**C++-spezifisch**

Schließt Elemente aus den Headerdateien der Typbibliothek aus, die generiert werden.

## <a name="syntax"></a>Syntax

```
exclude("Name1"[, "Name2",...])
```

### <a name="parameters"></a>Parameter

*Name1*<br/>
Erstes auszuschließendes Element.

*Name2*<br/>
Zweites auszuschließendes Element (falls erforderlich).

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. Dieses Attribut kann eine beliebige Anzahl von Argumenten annehmen, die jeweils ein auszuschließendes Typbibliothekelement der höchsten Ebene sind.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)