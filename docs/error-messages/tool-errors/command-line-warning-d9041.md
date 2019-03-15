---
title: Befehlszeilenwarnung D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 2311c61c4d661d58302308f06b08971f94cdacab
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816307"
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
[MSVC-Compiler-Optionen](../../build/reference/compiler-options.md)