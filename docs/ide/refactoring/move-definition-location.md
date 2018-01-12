---
title: Definitionsspeicherort verschieben | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 838f3d01f5e6d8612948304b80b79cf9c7cb4720
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="move-definition-location"></a>Definitionsspeicherort verschieben
**Was:** können Sie die Definition einer Funktion sofort auf die entsprechende Headerdatei verschieben.

**Wann:** Sie verfügen über Funktionen, die Sie in einer Headerdatei verschieben möchten.  

**Grund:** konnten Sie die Funktion manuell verschieben, aber dieses Feature wird es automatisch verschoben, die Header-Datei erstellen, falls erforderlich.

**Vorgehensweise:**

1. Platzieren Sie den Text oder mit dem Mauszeiger-Cursor über die Funktion für die Sie verschieben möchten.

   ![Hervorgehobene code](images/movedefinition_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü **Definitionsspeicherort verschieben** aus dem Kontextmenü.
   * **Maus**
     * Mit der rechten Maustaste, und wählen Sie die **Schnellaktionen und Refactorings** Menü **Definitionsspeicherort verschieben** aus dem Kontextmenü.

1. Die Funktion wird in die entsprechende Headerdatei verschoben werden, die in einem Popup-Vorschaufenster angezeigt werden.  Wenn die Header-Datei nicht vorhanden ist, wird es auch erstellt und in das Projekt eingefügt.

   ![Erstellen Sie die Deklaration / Definition resultieren](images/movedefinition_result.png)
