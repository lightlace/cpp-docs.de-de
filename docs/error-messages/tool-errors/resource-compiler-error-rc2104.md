---
title: 'Ressourcencompiler: Fehler RC2104 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd602dcde34aa7cc08486188ab5fb5925eca0eb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081090"
---
# <a name="resource-compiler-error-rc2104"></a>Ressourcencompiler: Fehler RC2104

Undefiniertes Schlüsselwort oder Schlüsselname: Schlüssel

Das angegebene Schlüsselwort oder der Schlüsselname ist nicht definiert.

Dieser Fehler wird häufig durch einen Tippfehler in die Definition der Ressource oder in der zugehörigen Header-Datei verursacht. Er kann auch durch eine fehlende Headerdatei verursacht werden.

Um das Problem zu beheben, suchen Sie die Header-Datei, die das definierte Schlüsselwort oder den Schlüsselnamen enthält und stellen Sie sicher, dass er in Ihrer Ressourcendatei enthalten ist und dass das Schlüsselwort oder der Schlüsselname richtig geschrieben ist. Wenn das Projekt mit einem vorkompilierten Header erstellt wurde und Sie es anschließend entfernen, stellen Sie sicher, dass die Ressourcendatei erforderliche Header enthält.

Öffnen Sie zum Überprüfen der definierten Schlüsselwörter und Schlüsselnamen in Ihrer Ressourcendatei in Visual Studio die **Ressourcenansicht** Fenster – Wählen Sie auf der Menüleiste **Ansicht**, **Ressourcenansicht**– und Klicken Sie dann öffnen Sie das Kontextmenü für die RC-Datei, und wählen Sie **Ressourcensymbole** um die Liste der definierten Symbole anzuzeigen. Um die enthaltenen Header zu ändern, öffnen Sie das Kontextmenü für die RC-Datei, und wählen Sie **Ressourcenincludes**.

Wenn Sie diese Meldung erhalten:

```
undefined keyword or key name: MFT_STRING
```

Öffnen Sie \MCL\MFC\Include\AfxRes.h, und fügen Sie diese Eingüge-Direktive ein:

```
#include <winresrc.h>
```