---
title: Extract-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd91da5296df92103f3d10fd399bd7d53bc57b5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="extract-function"></a>Extract-Funktion
**Was:** können Sie ein Fragment des Codes in eine eigene Funktion zu aktivieren.

**Wann:** haben Sie ein Fragment von vorhandenem Code, in eine Funktion, die von einer anderen Funktion aufgerufen werden muss.  

**Grund:** Sie konnte Kopieren/Einfügen dieses Codes jedoch, die zu Duplizierung führen würde.  Eine bessere Lösung ist dieses Fragment in eine eigene Funktion umgestaltet werden, die kostenlos von jeder anderen Funktion aufgerufen werden kann.

**Vorgehensweise:**

1. Markieren Sie den Code, die extrahiert werden:

   ![Hervorgehobene code](images/extractfunction_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG + R**, klicken Sie dann **STRG + M**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü **Extract-Funktion (experimentell)** aus dem Kontextmenü.
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Extract-Funktion (experimentell)**.
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **Extract-Funktion (experimentell)** aus dem Kontextmenü.
     * Klicken Sie auf die ![Lightbulb](images/bulb.png) im linken Rand, und wählen erscheint das Symbol für **Extract-Funktion (experimentell)** aus dem Kontextmenü.

1. In der **Funktion/Methode extrahieren (experimentell)** , geben Sie den neuen Funktionsnamen, auswählen soll den Code platziert werden soll, und klicken Sie auf die **OK** Schaltfläche.  

   ![Extract-Funktion](images/extractfunction_dialog.png)

1. Die neue Funktion erstellt werden, die Sie angegeben haben, einen Funktionsprototyp in die entsprechende Headerdatei und der ursprüngliche Code geändert werden, damit diese Funktion aufrufen.

   ![Extrahieren Sie Funktionsergebnis](images/extractfunction_result.png)