---
title: ATL-Dialogfeld-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
ms.openlocfilehash: 7f868800bb8453ac47ec0f188d6a2970aee7a55f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458053"
---
# <a name="atl-dialog-wizard"></a>ATL-Dialogfeld-Assistent

Dieser Assistent fügt dem Projekt eine ATL-Dialogfeldobjekt abgeleitet [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Ein Dialogfeld, das von abgeleiteten `CAxDialogImpl` können ActiveX-Steuerelemente hosten.

Der Assistent erstellt eine Dialogfeldressource Standardwert **OK** und **Abbrechen** Schaltflächen. Können die Dialogfeldressource bearbeiten und Hinzufügen von ActiveX-Steuerelemente mithilfe der [Dialog-Editor](../../windows/dialog-editor.md) in der Ressourcenansicht.

Der Assistent fügt die Header-Datei eine [meldungszuordnung](../../atl/message-maps-atl.md) und Deklarationen für die Behandlung von Standard auf Ereignisse. Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) für Weitere Informationen über ATL-Dialogfelder.

- **Kurzname**

   Legt fest, den abgekürzten Namen für das ATL-Dialogfeld-Objekt. Der Name, den Sie angeben, bestimmt den Klassennamen und den Dateinamen (cpp- und .h), wenn Sie die Felder einzeln ändern.

- **Klasse**

   Legt den Namen der Klasse erstellt werden. Dieser Name basiert auf den Namen, die Sie, in angeben **Kurznamen**ist 'C', das typische Präfix für einen Klassennamen vorangestellt.

- **H-Datei**

   Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **CPP-Datei**

   Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

## <a name="see-also"></a>Siehe auch

[ATL-Dialogfeld](../../atl/reference/adding-an-atl-dialog-box.md)

