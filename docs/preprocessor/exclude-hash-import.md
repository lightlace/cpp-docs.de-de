---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: 1de1376fbe80147bc9fe01ea83bad81912431310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498253"
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