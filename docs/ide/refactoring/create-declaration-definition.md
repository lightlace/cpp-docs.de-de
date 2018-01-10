---
title: Erstellen Sie die Deklaration / Definition | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 889c8acf5e0ef0ed6a7ac90088a6188658d49d75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="create-declaration--definition"></a>Deklaration/Definition erstellen
**Was:** können Sie der Deklaration oder Definition einer Funktion sofort zu generieren.

**Wann:** Sie verfügen über Funktionen, die eine verfügt, oder umgekehrt.  

**Grund:** konnten Sie die Deklaration/Definition manuell erstellen, aber dies wird es automatisch erstellt, die Header/Codedatei erstellen, falls erforderlich.

**Vorgehensweise:**

1. Platzieren Sie den Text oder mit dem Mauszeiger-Cursor über die Funktion für die Sie der Deklaration oder Definition erstellen möchten.

   ![Hervorgehobene code](images/createdefinition_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü **erstellen Deklaration / Definition** aus dem Kontextmenü.
   * **Maus**
     * Mit der rechten Maustaste, und wählen Sie die **Schnellaktionen und Refactorings** Menü **erstellen Deklaration / Definition** aus dem Kontextmenü.

1. Die Funktion Deklaration/Definition wird in der Quelle oder das Header-Datei erstellt werden, die in einem Popup-Vorschaufenster angezeigt werden.  Wenn die Quelle oder das Header-Datei nicht vorhanden ist, wird er auch erstellt und in das Projekt eingefügt.

   ![Erstellen Sie die Deklaration / Definition resultieren](images/createdefinition_result.png)
