---
title: MFC-Klassen-Assistent
ms.date: 09/06/2019
f1_keywords:
- vc.wizards.classwizard
helpviewer_keywords:
- MFC Class Wizard
ms.assetid: 8b0dd867-5d07-4214-99be-2a1c1995e6d9
ms.openlocfilehash: be829156d8fea8188a217b2c0a189ac5d6057a7e
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907999"
---
# <a name="mfc-class-wizard"></a>MFC-Klassen-Assistent

Verwenden Sie den **Klassen-Assistenten** , um neue MFC-Klassen zu erstellen, oder fügen Sie den vorhandenen Klassen in Ihrem Projekt Nachrichten und Nachrichten Handler hinzu.

Es gibt drei Möglichkeiten, den **Klassen-Assistenten**zu öffnen:

- Wählen Sie im Menü **Projekt** die Option **Klassen-Assistent**aus.
- Geben Sie **STRG** > **UMSCHALT** > **X**ein.
- Klicken Sie in **Klassenansicht**mit der rechten Maustaste auf eine Klasse oder den Projekt Knoten, und wählen Sie **Klassen-Assistent**aus.

![Klassen-Assistent](media/class-wizard.png "MFC-Klassen-Assistent")

## <a name="uielement-list"></a>Liste der Benutzeroberflächenelemente

- **Projekt**

   Der Name eines Projekts in der Lösung.

   Sie können andere Projekte in der Projektmappe im Dropdown-Listenfeld auswählen.

- **Klassenname**

   Der Name einer Klasse im Projekt.

   Wenn Sie in der Liste **Klassenname** eine Klasse auswählen, werden die Steuerelemente im **MFC-Klassen-Assistenten**von Daten aus der-Klasse aufgefüllt. Wenn Sie den Wert eines Steuerelements ändern, sind Daten in der ausgewählten Klasse betroffen.

- **Klasse hinzufügen**

   Ermöglicht das Hinzufügen einer neuen Klasse zum MFC-Projekt.

- **Basisklasse**

   Die Basisklasse der Klasse, die unter **Klassenname**angezeigt wird.

- **Klassen Deklaration**

   Die Klasse, in der die **Klassennamen** Klasse deklariert wird.

   Das Feld **Klassen Deklaration** wird nur angezeigt, wenn der Name in diesem Feld von dem Namen in der **Klassen Implementierung**abweicht.

- **Ressource**

   Die ID der Ressource im **Klassennamen**(sofern vorhanden). Andernfalls ist das **Ressourcen** Feld leer.

- **Klassen Implementierung**

   Der Name der Datei, die die Implementierung der-Klasse in den **Klassennamen**enthält.

   Sie können eine andere Implementierungsdatei auswählen, indem Sie auf den Pfeil klicken. In der folgenden Tabelle sind die verfügbaren Optionen aufgelistet.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Datei öffnen**|Beendet den Klassen-Assistenten und öffnet die aktuelle Klassenimplementierungsdatei.|
   |**Enthaltenden Ordner öffnen**|Öffnet den Ordner, der die aktuelle Klassenimplementierungsdatei enthält.|
   |**Vollständigen Pfad in Zwischenablage kopieren**|Kopiert den Pfad der aktuellen Implementierungsdatei in die Zwischenablage.|

- **Respekt**

   Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einem Befehl und seinem Meldungshandler.

   Um einen Handler hinzuzufügen, klicken Sie auf **Handler hinzufügen**, oder Doppelklicken Sie auf ein Element in der Liste **Objekt-IDs** oder **Nachrichten** . Der resultierende Funktionsname, die ID und die Meldung werden in der Liste der Element **Funktionen** angezeigt.

   Um einen Handler zu löschen, wählen Sie ein Element in der Liste Element **Funktionen** aus, und klicken Sie dann auf **Handler löschen**.

   Um einen Handler zu ändern, doppelklicken Sie auf das entsprechende Element in der Liste Element **Funktionen** . Oder wählen Sie ein Element im Listenfeld aus, und klicken Sie dann auf **Code bearbeiten**.

- **Meldungen**

   Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer Meldung und ihrem Meldungshandler.

   Um einen Handler hinzuzufügen, klicken Sie auf **Handler hinzufügen**, oder Doppelklicken Sie auf ein Element in der Liste **Nachrichten** .

   Um eine benutzerdefinierte Meldung hinzuzufügen, klicken Sie auf **benutzerdefinierte Meldung hinzufügen** , oder drücken Sie die EINGABETASTE, und geben Sie dann im Dialogfeld **benutzerdefinierte Meldung hinzufügen** Werte an In diesem Dialogfeld können Sie auch **registrierte Nachricht** auswählen, um eine Fenster Meldung zu behandeln, die im gesamten Betriebssystem eindeutig ist.

- **Virtuelle Funktionen**

   Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer virtuellen Funktion oder einer überschriebenen virtuellen Funktion.

- **Element Variablen**

   Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer Membervariable.

- **Methoden**

   Ermöglicht das Hinzufügen, Löschen oder Suchen nach einer Methode. Sie können auch zur Definition oder der Deklaration einer Methode wechseln.

   Klicken Sie zum Hinzufügen einer Methode auf **Methode hinzufügen**, und geben Sie dann im Dialogfeld **Methode hinzufügen** Werte ein.

   Um eine Methode zu löschen, wählen Sie in der Liste **Methoden** ein Element aus, und klicken Sie dann auf **Methode löschen**.

   Um eine Deklaration anzuzeigen, wählen Sie ein Element in der Liste **Methoden** aus, und klicken Sie dann auf **Gehe zu Deklaration.**

   Doppelklicken Sie auf ein Element in der Liste der **Methoden** , um eine Definition anzuzeigen. Oder wählen Sie ein Element in der Liste **Methoden** aus, und klicken Sie dann auf die Schaltfläche **Gehe zu Definition** .

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
