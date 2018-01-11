---
title: Benennen Sie | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ca06ef5a11d674d35aff7276e14312c456c60e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rename"></a>Umbenennen
**Was:** können Sie die Bezeichner für die Code-Symbolen, z. B. Felder, lokale Variablen, Methoden, Namespaces, Eigenschaften und Typen umbenennen.

**Wann:** Sie etwas problemlos ohne Suchen nach allen Instanzen und den neuen Namen kopieren/einfügen umbenennen möchten.  

**Grund:** kopieren und Einfügen von den neuen Namen für ein Gesamtprojekt würde wahrscheinlich zu Fehlern führen.  Dieses refactoring Tool führt genau umbenennen.

**Vorgehensweise:**

1. Markieren Sie, oder platzieren Sie den Textcursor innerhalb des Elements an, der umbenannt werden:

   ![Hervorgehobene code](images/rename_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG + R**, klicken Sie dann **STRG + R**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Umbenennen**.
     * Mit der rechten Maustaste in des Codes, und wählen Sie **umbenennen**.

1. In der **umbenennen** -Fenster angezeigt wird, geben Sie den neuen Namen für das ausgewählte Element und auf die **Vorschau** Schaltfläche.  Ändern der **Suchbereich** erweitert werden, oder schränken Sie die Umbenennung des Bereichs werden sollen.

   ![Umbenennen von Dialogfeld](images/rename_dialog.png)

   > [!TIP]
   > Sie können die Vorschau überspringen, indem Sie die Überprüfung der **Skip Vorschau ändert, wenn Verweise auf alle bestätigt werden** Option.

1. Wenn die **benennen Sie die Vorschau der Änderungen -** Fenster angezeigt wird, stellen Sie sicher, dass die Änderungen, die Sie anfordern ordnungsgemäß ausgeführt werden.  Verwenden Sie die Kontrollkästchen aktivieren oder deaktivieren das Umbenennen eines Elements in der oberen Hälfte des Fensters.

   ![Benennen Sie die Vorschau](images/rename_preview.png)

1. Wenn alles gut aussieht, klicken Sie auf die **übernehmen** Schaltfläche und das Element werden in Ihrem Quellcode umbenannt werden.
