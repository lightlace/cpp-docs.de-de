---
title: Extract-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dbcd323292e301857c65d908047ab14948b86573
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="extract-function"></a>Extract-Funktion
**Was:** können Sie ein Fragment des Codes in eine eigene Funktion zu aktivieren.

**Wann:** haben Sie ein Fragment von vorhandenem Code, in eine Funktion, die von einer anderen Funktion aufgerufen werden muss.  

**Vorteile**: Sie könnten diesen Code kopieren und einfügen, dies würde jedoch zu einer Duplizierung führen.  Eine bessere Lösung ist dieses Fragment in eine eigene Funktion umgestaltet werden, die kostenlos von jeder anderen Funktion aufgerufen werden kann.

**Vorgehensweise**:

1. Markieren Sie den zu extrahierenden Code:

   ![Markierter Code](images/extractfunction_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+R** und dann **STRG+M**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG+.**, Trigger die **Schnellaktionen und Refactorings** Menü **Extract-Funktion (experimentell)** aus dem Kontextmenü.
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Extract-Funktion (experimentell)**.
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **Extract-Funktion (experimentell)** aus dem Kontextmenü.
     * Klicken Sie auf die ![Lightbulb](images/bulb.png) im linken Rand, und wählen erscheint das Symbol für **Extract-Funktion (experimentell)** aus dem Kontextmenü.

1. In der **Funktion/Methode extrahieren (experimentell)** , geben Sie den neuen Funktionsnamen, auswählen soll den Code platziert werden soll, und klicken Sie auf die **OK** Schaltfläche.  

   ![Extract-Funktion](images/extractfunction_dialog.png)

1. Die neue Funktion erstellt werden, die Sie angegeben haben, einen Funktionsprototyp in die entsprechende Headerdatei und der ursprüngliche Code geändert werden, damit diese Funktion aufrufen.

   ![Extrahieren Sie Funktionsergebnis](images/extractfunction_result.png)