---
title: "Ändern der Signatur | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5280b4940c2a52fc6e72b397300040ca4c1ac92e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="change-signature"></a>Signatur ändern
**Was:** können Sie die Parameter einer Funktion zu ändern.

**Wann:** Sie verwenden möchten, neu anordnen, hinzufügen, entfernen oder ändern Sie die Parameter für eine Funktion, die zurzeit in einer Vielzahl von Standorten verwendet wird.  

**Grund:** Sie konnte manuell ändern diese Parameter selbst, und klicken Sie dann Suchen aller Aufrufe dieser Funktion und geändert werden, indem nacheinander, aber, die zu Fehlern führen.  Dieses refactoring-Tool wird automatisch den Task ausgeführt werden.

**Vorgehensweise:**

1. Platzieren Sie den Text oder mit dem Mauszeiger Cursor innerhalb der Name der die Methode zum Ändern oder eines seiner Verwendungen:

   ![Hervorgehobene code](images/changesignature_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG + R**, klicken Sie dann **STRG + O**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü **Signatur ändern** aus dem Kontextmenü.
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Parameter neu anordnen**.
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **Signatur ändern** aus dem Kontextmenü.

1. In der **ändern Signatur** oben angezeigten Dialogfeld können Sie die Schaltflächen auf der rechten Seite so ändern Sie die Signatur der Methode:

   ![Ändern der Signatur-Dialogfeld](images/changesignature_dialog.png)

   | Schaltfläche | Beschreibung
   | ------ | ---
   | **Nach oben/unten**    | Verschiebt den ausgewählten Parameter nach oben oder unten der Liste
   | **Add**        | Fügen Sie der Liste einen neuen Parameter hinzu
   | **Entfernen**     | Entfernt den ausgewählten Parameter aus der Liste
   | **Ändern Sie**     | Ändern Sie den ausgewählten Parameter durch Ändern seines Typs für Namen und optional, und was mit der eingefügte Wert wäre
   | **Wiederherstellen**     | Wiederherstellen der ausgewählten Parameters den ursprünglichen Zustand
   | **Alle zurücksetzen** | Alle Parameter in ihren ursprünglichen Zustand wiederherstellen

   > [!TIP]
   > Verwenden der **Skip Preview Verweis ändert, wenn alle Verweise bestätigt werden** Kontrollkästchen, um die Änderungen sofort ohne zuerst das herunternehmen Vorschaufenster vornehmen.

   Beim Hinzufügen oder Ändern eines Parameters, sehen Sie die **Parameter hinzufügen** oder **Parameter bearbeiten** Fenster.

   ![Parameter hinzufügen/ändern](images/changesignature_addmodify.png)

   Hier können Sie Folgendes tun:

   | Eingabe | Beschreibung
   | ----- | ---
   | **Type**               | Der Typ des Parameters (Int, double, float usw..)
   | **Name**               | Der Name des Parameters
   | **Optionale Parameter** | Stellt die Parameter, die optional angegeben werden
   | **Eingefügten Wert**     | Der Wert eingefügt alle Aufrufe an die Funktion, in dem der Parameter wurde nicht angegeben (nur gültig für **hinzufügen**)
   | **Standardwert**      | Der Wert, der von der Funktion verwendet werden, wenn der Aufrufer nicht angeben (nur gültig für **optionale Parameter**)

1. Verwenden der **Suchbereich** Dropdown-Liste auswählen, wenn die Änderungen auf das Projekt oder die gesamte Lösung angewendet werden.

1. Wenn Sie fertig sind, drücken Sie die **OK** Schaltfläche, um die Änderungen vornehmen.  Stellen Sie sicher, dass die Änderungen auf die angeforderte entsprechend durchgeführt werden.  Verwenden Sie die Kontrollkästchen aktivieren oder deaktivieren das Umbenennen eines Elements in der oberen Hälfte des Fensters.

   ![Ändern der Signatur-Vorschau](images/changesignature_preview.png)

1. Wenn alles gut aussieht, klicken Sie auf die **übernehmen** Schaltfläche und die Funktion werden in Ihrem Quellcode geändert werden.

   ![Ergebnis der Signatur](images/changesignature_result.png)