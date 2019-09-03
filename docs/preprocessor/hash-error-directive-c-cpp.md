---
title: '##error-Anweisung (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: bfb5c18f20319e6e6d345f28d3e1850714334b71
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216121"
---
# <a name="error-directive-cc"></a>#Error-Direktive (C++C/)

Die **#Error** -Direktive gibt zum Zeitpunkt der Kompilierung eine benutzerdefinierte Fehlermeldung aus und beendet dann die Kompilierung.

## <a name="syntax"></a>Syntax

> **#Error** *Tokenzeichenfolge*

## <a name="remarks"></a>Hinweise

Die Fehlermeldung, die diese Anweisung ausgibt, enthält den Tokenzeichenfolgen *-* Parameter. Der *Tokenzeichenfolgen-* Parameter unterliegt nicht der Makro Erweiterung. Diese Direktive ist während der Vorverarbeitung am nützlichsten, um den Entwickler über eine Programm Inkonsistenz oder einen Verstoß gegen eine Einschränkung zu benachrichtigen. Das folgende Beispiel zeigt die Fehlerverarbeitung während der Vorverarbeitung:

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)
