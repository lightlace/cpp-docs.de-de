---
title: Befehlszeilenwarnung D9041 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70bf82cfdca787898a02fb52926981bfd1a1b3e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033380"
---
# <a name="command-line-warning-d9041"></a>Befehlszeilenwarnung D9041

Ungültiger Wert "Value" für "/ option"; vorausgesetzt, 'Value'; Hinzufügen "/ analyze-den Befehlszeilenoptionen, die bei Angabe dieser Warnung

Eine Nummer der codeanalysewarnung wurde hinzugefügt, um die **/WD**, **/we**, **/wo**, oder **/WL** -Befehlszeilenoption, ohne dass auch die **/ analyze** -Befehlszeilenoption. Um diesen Fehler zu beheben, fügen Sie hinzu, die **/ analyze** -Befehlszeilenoption, oder entfernen Sie die ungültige Warnungsnummer, aus der entsprechenden **/w** -Befehlszeilenoption.

## <a name="example"></a>Beispiel

Im folgenden Befehlszeilenbeispiel wird die Warnung D9041 generiert:

```
cl /EHsc /LD /wd6001 filename.cpp
```

Um die Warnung zu beheben, fügen die **/ analyze** -Befehlszeilenoption. Wenn **/ analyze** ist in Ihrer Version des Compilers nicht unterstützt, entfernen Sie die ungültige Warnungsnummer aus der **/WD** Option.

## <a name="see-also"></a>Siehe auch

[Befehlszeilenfehler D8000 bis D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)