---
title: Definitionsspeicherort verschieben | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44211105429e33c136999a7877ac6ee42af29f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="move-definition-location"></a>Definitionsspeicherort verschieben
**Was:** können Sie die Definition einer Funktion sofort auf die entsprechende Headerdatei verschieben.

**Wann:** Sie verfügen über Funktionen, die Sie in einer Headerdatei verschieben möchten.  

**Grund:** konnten Sie die Funktion manuell verschieben, aber dieses Feature wird es automatisch verschoben, die Header-Datei erstellen, falls erforderlich.

**Vorgehensweise**:

1. Platzieren Sie den Text oder mit dem Mauszeiger-Cursor über die Funktion für die Sie verschieben möchten.

   ![Markierter Code](images/movedefinition_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, Trigger die **Schnellaktionen und Refactorings** Menü **Definitionsspeicherort verschieben** aus dem Kontextmenü.
   * **Maus**
     * Mit der rechten Maustaste, und wählen Sie die **Schnellaktionen und Refactorings** Menü **Definitionsspeicherort verschieben** aus dem Kontextmenü.

1. Die Funktion wird in die entsprechende Headerdatei verschoben werden, die in einem Popup-Vorschaufenster angezeigt werden.  Wenn die Header-Datei nicht vorhanden ist, wird es auch erstellt und in das Projekt eingefügt.

   ![Erstellen Sie die Deklaration / Definition resultieren](images/movedefinition_result.png)
