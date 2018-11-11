---
title: Hinzufügen einer Klasse mit dem ActiveX-Steuerelement-Assistenten
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.axcontrol
helpviewer_keywords:
- ActiveX Control Wizard
- Add Class from ActiveX Control Wizard [C++]
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
ms.openlocfilehash: 736ac50f14d8434584c6f47b2953913c79b0b00a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472487"
---
# <a name="add-class-from-activex-control-wizard"></a>Hinzufügen einer Klasse mit dem ActiveX-Steuerelement-Assistenten

Verwenden Sie diesen Assistenten, um eine MFC-Klasse aus einem verfügbaren ActiveX-Steuerelement hinzuzufügen. Der Assistent erstellt eine Klasse für jede Schnittstelle, die Sie aus dem ausgewählten ActiveX-Steuerelement hinzufügen.

- **Add Class From** (Klasse hinzufügen aus)

   Gibt den Speicherort der Typbibliothek an, aus der die Klasse erstellt wird.

   |Option|Beschreibung |
   |------------|-----------------|
   |**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken werden unter **Available ActiveX controls** (Verfügbare ActiveX-Steuerelemente) aufgeführt.|
   |**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, sondern in einer Datei enthalten. Sie müssen den Dateispeicherort unter **Speicherort** angeben.|

- **Verfügbare ActiveX-Steuerelemente**

   Gibt die ActiveX-Steuerelemente an, die derzeit im System registriert sind. Wählen Sie ein ActiveX-Steuerelement aus dieser Liste aus, um dessen Schnittstellen in der Liste **Schnittstellen** anzuzeigen. Weitere Informationen zur Registrierung von ActiveX-Steuerelementen finden Sie unter [MFC ActiveX Controls: Distributing ActiveX Controls (MFC-ActiveX-Steuerelemente: Weitergabe von ActiveX-Steuerelementen)](../mfc/mfc-activex-controls-distributing-activex-controls.md).

   Wenn Sie unter **Add Class From** (Klasse hinzufügen aus) auf **Datei** klicken, kann dieses Feld nicht geändert werden.

- **Position**

   Gibt den Speicherort des ActiveX-Steuerelements an. Wenn Sie unter **Add Class From** (Klasse hinzufügen aus) auf **Datei** klicken, können Sie den Speicherort der Datei angeben, die die Typbibliothek enthält. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um nach dem Speicherort der Datei zu suchen.

   Wenn Sie unter **Add Class From** (Klasse hinzufügen aus) auf **Registrierung** klicken, kann dieses Feld nicht geändert werden.

- **Schnittstellen**

   Gibt die Schnittstellen des ActiveX-Steuerelements an, das derzeit unter **Available ActiveX controls** (Verfügbare ActiveX-Steuerelemente) oder in der Typbibliothek in der Datei angegeben ist, die unter **Speicherort** angegeben ist.

   |Schaltfläche „Übertragen“|Beschreibung |
   |---------------------|-----------------|
   |**>**|Fügt die Schnittstelle hinzu, die derzeit in der Liste **Schnittstellen** ausgewählt ist. Nicht verfügbar, wenn keine Schnittstelle ausgewählt ist.|
   |**>>**|Fügt alle Schnittstellen des ActiveX-Steuerelements hinzu, das derzeit unter **Available ActiveX controls** (Verfügbare ActiveX-Steuerelemente) oder in der Typbibliothek in der Datei angegeben ist, die unter **Speicherort** angegeben ist.|
   |**\<**|Entfernt die Klasse, die derzeit in der Liste **Generierte Klassen** ausgewählt ist. Nicht verfügbar, wenn derzeit keine Klasse in der Liste **Generierte Klassen** ausgewählt ist.|
   |**\<\<**|Entfernt alle Klassen in der Liste **Generierte Klassen**. Nicht verfügbar, wenn die Liste **Generierte Klassen** leer ist.|

- **Generierte Klassen**

   Gibt die Klassennamen an, die aus den Schnittstellen generiert werden sollen, die mithilfe der Schaltfläche **>** oder **>>** hinzugefügt wurden. Sie können auf dieses Feld klicken, um eine Klasse auszuwählen und die Pfeiltasten verwenden, um durch die Liste zu scrollen. Dabei wird jeder Klassenname im Feld `Class` und jeder Dateiname im Feld **H-Datei** angezeigt. Diese werden vom Assistenten generiert, wenn Sie auf **Fertig stellen** klicken. Sie können nur eine Klasse in diesem Feld auswählen.

   Sie können eine Klasse entfernen, indem Sie diese in der Liste auswählen und auf **<** klicken. Sie müssen keine Klasse im Feld **Generierte Klassen** auswählen, um alle Klassen zu entfernen. Sie können alle Klassen im Feld **Generierte Klassen** entfernen, indem Sie auf **<<** klicken.

- **Klasse**

   Gibt den Namen der Klasse an, die im Feld **Generierte Klassen** ausgewählt ist. Dieses wird vom Assistenten hinzugefügt, wenn Sie auf **Fertig stellen** klicken. Sie können den Namen im Feld **Klasse** bearbeiten.

- **H-Datei**

   Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Generierte Klassen** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **CPP-Datei**

   Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Generierte Klassen** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Klasse aus einem ActiveX-Steuerelement](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)<br>
[Automatisierungsclients: Verwenden von Typbibliotheken](../mfc/automation-clients-using-type-libraries.md)