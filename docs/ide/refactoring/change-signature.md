---
title: Ändern der Signatur | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f913f0b3065b136f626ef15cc2a77dce8d0254f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="change-signature"></a>Signatur ändern
**Was:** können Sie die Parameter einer Funktion zu ändern.

**Wann:** Sie verwenden möchten, neu anordnen, hinzufügen, entfernen oder ändern Sie die Parameter für eine Funktion, die zurzeit in einer Vielzahl von Standorten verwendet wird.  

**Grund:** Sie konnte manuell ändern diese Parameter selbst, und klicken Sie dann Suchen aller Aufrufe dieser Funktion und geändert werden, indem nacheinander, aber, die zu Fehlern führen.  Bei diesem Refactoringtool wird der Task automatisch ausgeführt.

**Vorgehensweise**:

1. Platzieren Sie den Text oder mit dem Mauszeiger Cursor innerhalb der Name der die Methode zum Ändern oder eines seiner Verwendungen:

   ![Markierter Code](images/changesignature_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG + R**, klicken Sie dann **STRG + O**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG+.**, Trigger die **Schnellaktionen und Refactorings** Menü **Signatur ändern** aus dem Kontextmenü.
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Parameter neu anordnen** aus.
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **Signatur ändern** aus dem Kontextmenü.

1. Mit den Schaltflächen auf der rechten Seite im angezeigten Dialogfeld **Signatur ändern** können Sie die Methodensignatur ändern:

   ![Dialogfeld „Signatur ändern“](images/changesignature_dialog.png)

   | Schaltfläche | Beschreibung
   | ------ | ---
   | **Nach oben/unten**    | Den ausgewählten Parameter in der Liste nach oben oder nach unten verschieben
   | **Add**        | Fügen Sie der Liste einen neuen Parameter hinzu
   | **Entfernen**     | Den ausgewählten Parameter aus der Liste entfernen
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

1. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **OK**, um die Änderungen zu übernehmen.  Stellen Sie sicher, dass die Änderungen auf die angeforderte entsprechend durchgeführt werden.  Verwenden Sie die Kontrollkästchen aktivieren oder deaktivieren das Umbenennen eines Elements in der oberen Hälfte des Fensters.

   ![Ändern der Signatur-Vorschau](images/changesignature_preview.png)

1. Wenn alles gut aussieht, klicken Sie auf die **übernehmen** Schaltfläche und die Funktion werden in Ihrem Quellcode geändert werden.

   ![Ergebnis der Aktion zum Ändern einer Signatur](images/changesignature_result.png)