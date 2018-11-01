---
title: no_registry
ms.date: 10/18/2018
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: bd101f5ca1776518ff4c5092da99134110bbb0b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503024"
---
# <a name="noregistry"></a>no_registry

**No_registry** weist den Compiler nicht an die Registrierung nach Typbibliotheken, die mit importiert suchen `#import`.

## <a name="syntax"></a>Syntax

```
#import filename no_registry
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Eine Typbibliothek.

## <a name="remarks"></a>Hinweise

Wenn keine referenzierte Typbibliothek in der Include-Verzeichnissen nicht gefunden wird, wird die Kompilierung fehlschlagen, auch wenn die Typbibliothek in der Registrierung ist.  **No_registry** überträgt auf andere Typbibliotheken importiert implizit mit `auto_search`.

Der Compiler durchsucht niemals die Registrierung nach Typbibliotheken, die mit Dateinamen angegeben und direkt an `#import` übergeben werden.

Bei der `auto_search` angegeben wird, die zusätzliche `#import`mit s generiert werden die **No_registry** -Einstellung des ursprünglichen `#import` (wenn der ursprüngliche `#import` Richtlinie wurde **No_registry** , `auto_search`-generiert `#import` auch **No_registry**.)

**No_registry** ist nützlich, wenn Sie plattformübergreifende Typbibliotheken ohne das Risiko des Compilers finden in der Registrierung eine ältere Version der Datei importieren möchten. **No_registry** ist auch nützlich, wenn die Typbibliothek nicht registriert ist.

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)