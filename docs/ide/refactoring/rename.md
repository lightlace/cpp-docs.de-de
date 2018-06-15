---
title: Umbenennen | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33339812"
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

1. Geben Sie den neuen Namen für das ausgewählte Element im angezeigten Fenster **Umbenennen** ein, und klicken Sie auf die Schaltfläche **Vorschau**.  Ändern Sie den **Suchbereich**, wenn Sie den Bereich für das Umbenennen erweitern und einschränken müssen.

   ![Dialogfeld „Umbenennen“](images/rename_dialog.png)

   > [!TIP]
   > Sie können die Vorschau überspringen, indem Sie die Option **Vorschau der Änderungen überspringen, wenn alle Verweise bestätigt sind** aktivieren.

1. Wenn das Fenster **Vorschau der Änderungen – Umbenennen** angezeigt wird, stellen Sie sicher, dass Ihre angeforderten Änderungen ordnungsgemäß ausgeführt werden.  Verwenden Sie die Kontrollkästchen in der oberen Hälfte des Fensters, um das Umbenennen von Elementen zu aktivieren oder zu deaktivieren.

   ![Vorschau für das Umbenennen](images/rename_preview.png)

1. Klicken Sie auf die Schaltfläche **Anwenden**, wenn alles Ihren Erwartungen entspricht, damit das Element in Ihrem Quellcode umbenannt wird.
