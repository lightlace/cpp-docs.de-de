---
title: Benennen Sie | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a064527f6afcbf91be3fb4e51180be647c1f506
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="rename"></a>Umbenennen
**Beschreibung**: Hiermit können Sie Bezeichner für Codesymbole (z.B. Felder, lokale Variablen, Methoden, Namespaces, Eigenschaften und Typen) umbenennen.

**Hintergrund**: Sie möchten ein Element sicher umbenennen, ohne alle Instanzen suchen und den neuen Namen kopieren und einfügen zu müssen.  

**Vorteile**: Das Kopieren und Einfügen des neuen Namens in ein ganzes Projekt würde aller Wahrscheinlichkeit nach zu Fehlern führen.  Dieses Refactoringtool führt die Umbenennungsaktion ordnungsgemäß durch.

**Vorgehensweise**:

1. Markieren Sie den Namen des umzubenennenden Elements, oder platzieren Sie den Textcursor in das Element:

   ![Markierter Code](images/rename_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+R** und dann **STRG+R**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Umbenennen** aus.
     * Klicken Sie mit der rechten Maustaste auf den Code, und wählen Sie **Umbenennen** aus.

1. In der **umbenennen** -Fenster angezeigt wird, geben Sie den neuen Namen für das ausgewählte Element und auf die **Vorschau** Schaltfläche.  Ändern der **Suchbereich** erweitert werden, oder schränken Sie die Umbenennung des Bereichs werden sollen.

   ![Umbenennen von Dialogfeld](images/rename_dialog.png)

   > [!TIP]
   > Sie können die Vorschau überspringen, indem Sie die Überprüfung der **Skip Vorschau ändert, wenn Verweise auf alle bestätigt werden** Option.

1. Wenn die **benennen Sie die Vorschau der Änderungen -** Fenster angezeigt wird, stellen Sie sicher, dass die Änderungen, die Sie anfordern ordnungsgemäß ausgeführt werden.  Verwenden Sie die Kontrollkästchen aktivieren oder deaktivieren das Umbenennen eines Elements in der oberen Hälfte des Fensters.

   ![Benennen Sie die Vorschau](images/rename_preview.png)

1. Wenn alles gut aussieht, klicken Sie auf die **übernehmen** Schaltfläche und das Element werden in Ihrem Quellcode umbenannt werden.
