---
title: 'Ressourcencompiler: Fehler RC2104'
ms.date: 11/04/2016
f1_keywords:
- RC2104
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
ms.openlocfilehash: 6ac1786e795c0c8ed57af2d341f43b8ba39229c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346560"
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