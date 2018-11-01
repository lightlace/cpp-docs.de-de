---
title: Befehlszeilenfehler D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: d3a7908ec9e7e37d83fd7b928cad2ef256313c40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526801"
---
# <a name="command-line-error-d8027"></a>Befehlszeilenfehler D8027

"Komponente" kann nicht ausgeführt werden

Der Compiler konnte nicht ausgeführt, die Compilerkomponente von angegebenen oder den Linker.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Nicht genügend Arbeitsspeicher zum Laden der Komponente. Wenn NMAKE den Compiler aufgerufen wird, führen Sie den Compiler außerhalb der makefile-Datei ein.

1. Das aktuelle Betriebssystem konnte die Komponente nicht ausgeführt werden. Vergewissern Sie sich der Pfad verweist auf die ausführbare Dateien für Ihr Betriebssystem geeignete.

1. Die Komponente wurde beschädigt. Kopieren Sie die Komponente von der Verteilung Datenträger über das Setup erneut.

1. Eine Option wurde falsch angegeben. Zum Beispiel:

    ```
    cl /B1 file1.c
    ```