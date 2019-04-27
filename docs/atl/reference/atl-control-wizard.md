---
title: ATL-Steuerelement-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.overview
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
ms.openlocfilehash: 58c3ebe4c2a15aa3f0d59191c37a7f2422a63ab5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261207"
---
# <a name="atl-control-wizard"></a>ATL-Steuerelement-Assistent

Einfügungen in einem ATL-Projekt (oder einem MFC-Projekt mit ATL-Unterstützung) ein ATL-Steuerelement. Sie können diesen Assistenten verwenden, um eine der drei Arten von Steuerelementen einzufügen:

- Standardsteuerelement

- Zusammengesetztes Steuerelement

- DHTML-Steuerelement

Sie können außerdem angeben, ein minimal-Steuerelement, entfernen die Schnittstellen aus der [Schnittstellen](../../atl/reference/interfaces-atl-control-wizard.md) Liste, die als Standardwerte für Steuerelemente, öffnen Sie in den meisten Containern bereitgestellt werden. Sie können festlegen, dass die Schnittstellen, die für das Steuerelement im unterstützt werden sollen die **Schnittstellen** Seite des Assistenten.

## <a name="remarks"></a>Hinweise

Vom Assistenten erstellte Registrierungsskript wird die COM-Komponenten unter HKEY_CURRENT_USER anstelle von HKEY_LOCAL_MACHINE registriert werden. Um dieses Verhalten zu ändern, legen Sie die **registerkomponenten für alle Benutzer** des ATL-Assistenten die Option.

## <a name="names"></a>Namen

Geben Sie die Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle anderen Felder können unabhängig geändert werden. Wenn Sie den Text für ändern **Kurznamen**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Name in der COM-Abschnitt die Änderung wirkt sich die **Typ** Feld jedoch **Schnittstelle** Name und **ProgID** führen nicht ändern. Diese Namenssystem ist so ausgelegt, alle Namen leicht identifizierbaren für Sie, wie Sie das Steuerelement entwickeln.

> [!NOTE]
>  **Co-Klasse** kann nur nicht attributierte Steuerelementen bearbeitet werden. Wenn Ihr Projekt zugeordnet sind, können nicht bearbeitet **Co-Klasse**.

### <a name="c"></a>C++

Enthält Informationen für die C++-Klasse erstellt, um das Objekt implementiert.

- **Kurzname**

   Legt den abgekürzten Namen für das Objekt fest. Der Name, den Sie angeben, bestimmt die Klasse und **Co-Klasse** -Namen ist, wird die Datei (. CPP und. H) Namen, den Schnittstellennamen und die **Typ** Namen, es sei denn, Sie diese Felder einzeln ändern.

- **Klasse**

   Legt den Namen der Klasse, die das Objekt implementiert. Dieser Name basiert auf den Namen, den Sie in bereitstellen **Kurznamen**ist 'C', das typische Präfix für einen Klassennamen vorangestellt.

- **H-Datei**

   Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird speichern Sie es nicht in den ausgewählten Speicherort bis auf **Fertig stellen**.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **CPP-Datei**

   Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Zugeordnet sind**

   Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt eine attributierten ATL-Projekt hinzufügen, ist diese Option ausgewählt und nicht verfügbar, um zu ändern. Also können Sie ein Projekt erstellt wurde, mit Attribut-Unterstützung nur attributierter Objekte hinzufügen.

   Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für ein ATL-Projekt, die nicht unterstützen Attribut verfügt auswählen, fordert der Assistent Sie angeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.

   Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributierten festgelegt (das Kontrollkästchen ist aktiviert). Sie können festlegen, löschen Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die keine Attribute verwendet.

   Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.

### <a name="com"></a>COM

Enthält Informationen über die COM-Funktionalität für das Objekt.

- **Co-Klasse**

   Legt den Namen der Komponentenklasse, die eine Liste der Schnittstellen, die vom Objekt unterstützten enthält.

   > [!NOTE]
   > Wenn Sie das Projekt mithilfe von Attributen erstellen, oder auf dieser Seite des Assistenten angeben, dass das Steuerelement Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist das **Co-Klasse** Attribut.

- **Interface**

   Legt den Namen der Schnittstelle für das Objekt. Standardmäßig wird ein Interface-Name mit "I" vorangestellt.

- **Type**

   Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird

- **ProgID**

   Legt den Namen, den Container anstatt der CLSID des Objekts verwenden können. Dieses Feld wird nicht automatisch aufgefüllt. Wenn Sie dieses Feld nicht manuell auffüllen, möglicherweise das Steuerelement nicht mit anderen Tools zur Verfügung. Z. B. ActiveX-Steuerelemente, die generiert werden, ohne eine `ProgID` sind nicht verfügbar, in der **ActiveX-Steuerelement einfügen** im Dialogfeld. Weitere Informationen zu diesem Dialogfeld finden Sie unter [Insert ActiveX Control Dialog Box („Dialogfeld ‚ActiveX-Steuerelement einfügen‘“)](../../windows/insert-activex-control-dialog-box.md).

## <a name="see-also"></a>Siehe auch

[ATL-Steuerelement](../../atl/reference/adding-an-atl-control.md)<br/>
[Hinzufügen von Funktionen zum zusammengesetzten Steuerelement](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)
