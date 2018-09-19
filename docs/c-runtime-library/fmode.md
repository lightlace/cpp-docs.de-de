---
title: _fmode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfc89eeda690632979521fa8a4e91c48c8b3c866
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080830"
---
# <a name="fmode"></a>_fmode

Die Variable `_fmode` legt den standardmäßigen Dateiübersetzungsmodus für die Text- oder Binärübersetzung fest. Diese globale Variable ist für die sichereren funktionalen Versionen [_get_fmode](../c-runtime-library/reference/get-fmode.md) und [_set_fmode](../c-runtime-library/reference/set-fmode.md) veraltet, die anstelle der globalen Variable verwendet werden sollten. Dies ist in Stdlib.h folgendermaßen deklariert.

## <a name="syntax"></a>Syntax

```
extern int _fmode;
```

## <a name="remarks"></a>Hinweise

Die Standardeinstellung von `_fmode` für die Textmodusübersetzung ist `_O_TEXT`. `_O_BINARY` ist die Einstellung für den Binärmodus.

Sie können den Wert von `_fmode` wie folgt ändern:

- Eine Verknüpfung mit „Binmode.obj“. Dadurch wird die ursprüngliche Einstellung von `_fmode` auf `_O_BINARY` geändert, woraufhin alle Dateien außer `stdin`, `stdout` und `stderr` im Binärmodus geöffnet werden.

- Ein Aufruf von `_get_fmode` oder `_set_fmode`, um die globale `_fmode`-Variable abzurufen bzw. festzulegen.

- Ändern Sie den Wert `_fmode` direkt, indem Sie ihn in Ihrem Programm festlegen.

## <a name="see-also"></a>Siehe auch

[Globale Variablen](../c-runtime-library/global-variables.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)