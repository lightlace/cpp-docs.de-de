---
title: Erstellen Sie die Deklaration / Definition | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d583ec47a3f9c5b61599a5945e3cfa0d375b1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="create-declaration--definition"></a>Deklaration/Definition erstellen
**Was:** können Sie der Deklaration oder Definition einer Funktion sofort zu generieren.

**Wann:** Sie verfügen über Funktionen, die eine verfügt, oder umgekehrt.  

**Grund:** konnten Sie die Deklaration/Definition manuell erstellen, aber dies wird es automatisch erstellt, die Header/Codedatei erstellen, falls erforderlich.

**Vorgehensweise**:

1. Platzieren Sie den Text oder mit dem Mauszeiger-Cursor über die Funktion für die Sie der Deklaration oder Definition erstellen möchten.

   ![Markierter Code](images/createdefinition_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, Trigger die **Schnellaktionen und Refactorings** Menü **erstellen Deklaration / Definition** aus dem Kontextmenü.
   * **Maus**
     * Mit der rechten Maustaste, und wählen Sie die **Schnellaktionen und Refactorings** Menü **erstellen Deklaration / Definition** aus dem Kontextmenü.

1. Die Funktion Deklaration/Definition wird in der Quelle oder das Header-Datei erstellt werden, die in einem Popup-Vorschaufenster angezeigt werden.  Wenn die Quelle oder das Header-Datei nicht vorhanden ist, wird er auch erstellt und in das Projekt eingefügt.

   ![Erstellen Sie die Deklaration / Definition resultieren](images/createdefinition_result.png)
