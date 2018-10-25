---
title: '#Fehler-Direktive (C/C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 143733af9003442996d9f649825f45f93643f536
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078800"
---
# <a name="error-directive-cc"></a>#error-Anweisung (C/C++)
Die **#error** -Anweisung gibt eine benutzerdefinierte Fehlermeldung zur Kompilierzeit aus und beendet dann die Kompilierung.

## <a name="syntax"></a>Syntax

```
#errortoken-string
```

## <a name="remarks"></a>Hinweise

Die Fehlermeldung, die diese Direktive ausgibt, enthält die *-Token-Zeichenfolge* Parameter. Die *-Token-Zeichenfolge* -Parameter unterliegt nicht der makroerweiterung. Diese Anweisung ist während der Vorverarbeitung am hilfreichsten, denn sie informiert den Entwickler über eine Programminkonsistenz oder einen Verstoß gegen eine Einschränkung. Das folgende Beispiel zeigt die Fehlerverarbeitung während der Vorverarbeitung:

```
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)