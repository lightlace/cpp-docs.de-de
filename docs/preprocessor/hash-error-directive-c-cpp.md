---
title: '#Fehler-Direktive (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: dc229a8eae6938cba32787ecbec6a5aa6a17ab47
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037843"
---
# <a name="error-directive-cc"></a>#error-Anweisung (C/C++)
Die **#error** -Anweisung gibt eine benutzerdefinierte Fehlermeldung zur Kompilierzeit aus und beendet dann die Kompilierung.

## <a name="syntax"></a>Syntax

```
#errortoken-string
```

## <a name="remarks"></a>Hinweise

Die Fehlermeldung, die diese Direktive ausgibt, enthält die *-Token-Zeichenfolge* Parameter. Die *-Token-Zeichenfolge* -Parameter unterliegt nicht der makroerweiterung. Diese Direktive ist während der Vorverarbeitung am hilfreichsten, denn sie informiert den Entwickler über eine Programminkonsistenz oder einen Verstoß gegen eine Einschränkung. Das folgende Beispiel zeigt die Fehlerverarbeitung während der Vorverarbeitung:

```
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)