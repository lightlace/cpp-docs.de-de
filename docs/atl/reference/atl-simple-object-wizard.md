---
title: ATL-Assistent für einfache Objekte
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.overview
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
ms.openlocfilehash: e18c1848c55208b02026aba7684db928e0d6fc0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260895"
---
# <a name="atl-simple-object-wizard"></a>ATL-Assistent für einfache Objekte

Dieser Assistent fügt dem Projekt ein minimales COM-Objekt. Verwenden Sie auf dieser Seite des Assistenten, um die Namen anzugeben, die die C++-Klasse und die Dateien für das Objekt und seine COM-Funktionen zu identifizieren.

Verwenden der [Optionen](../../atl/reference/options-atl-simple-object-wizard.md) Seiten des Assistenten angeben des Objekts Threadingmodell und der Aggregation unterstützt und gibt an, ob duale Schnittstellen und die Automatisierung unterstützt. Sie können auch Unterstützung für den Fehler Informationen der Schnittstelle, Verbindungspunkte, Internet Explorer-Support und Marshalling von Freethreadobjekten angeben.

## <a name="remarks"></a>Hinweise

Ab Visual Studio 2008 wird von diesem Assistenten erstellte Registrierungsskript seine COM-Komponenten unter registriert **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **registerkomponenten für alle Benutzer** des ATL-Assistenten die Option.

## <a name="names"></a>Namen

Geben Sie die Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle anderen Felder bearbeitet werden können, unabhängig von den anderen. Wenn Sie den Text für ändern **Kurznamen**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Name in der COM-Abschnitt die Änderung wirkt sich die **Typ** und **ProgID** Dialogfelder, aber die **Schnittstelle** Name wird nicht geändert. Diese Namenssystem ist so ausgelegt, alle Namen leicht identifizierbaren für Sie, wie Sie das Steuerelement entwickeln.

> [!NOTE]
>  **Co-Klasse** kann nur nicht attributierte Projekten bearbeitet werden. Wenn Ihr Projekt zugeordnet sind, können nicht bearbeitet **Co-Klasse**.

## <a name="c"></a>C++

Enthält Informationen für die C++-Klasse, die für das Objekt erstellt wurde.

- **Kurzname**

   Legt den abgekürzten Namen für das Objekt fest. Der Name, den Sie angeben, bestimmt die `Class` und `Coclass` Namen, die **cpp-Datei** und **.h-Datei** Namen, die **Schnittstelle** Namen verwenden, die **Typ** Namen, und die **ProgID**, es sei denn, Sie diese Felder einzeln ändern.

- **H-Datei**

   Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird speichern Sie es nicht in den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Klasse**

   Legt den Namen der Klasse erstellt werden. Dieser Name basiert auf den Namen, den Sie in bereitstellen **Kurznamen**ist 'C', das typische Präfix für einen Klassennamen vorangestellt.

- **CPP-Datei**

   Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Zugeordnet sind**

   Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt eine attributierten ATL-Projekt hinzufügen, ist diese Option ausgewählt und nicht verfügbar, um zu ändern. Also können Sie ein Projekt erstellt wurde, mit Attribut-Unterstützung nur attributierter Objekte hinzufügen.

   Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für ein ATL-Projekt, die nicht unterstützen Attribut verfügt auswählen, fordert der Assistent Sie angeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.

   Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributierten festgelegt (das Kontrollkästchen ist aktiviert). Sie können festlegen, löschen Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die keine Attribute verwendet.

   Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.

## <a name="com"></a>COM

Enthält Informationen über die COM-Funktionalität für das Objekt.

- **Co-Klasse**

   Legt den Namen der Komponentenklasse, die eine Liste der Schnittstellen, die vom Objekt unterstützten enthält.

   > [!NOTE]
   > Wenn Sie das Projekt mithilfe von Attributen erstellen, oder auf dieser Seite des Assistenten angeben, dass das Objekt Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist das `coclass` Attribut.

- **Type**

   Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird

- **Interface**

   Legt die Schnittstelle, die Sie für Ihr Objekt zu erstellen. Diese Schnittstelle enthält die benutzerdefinierten Methoden.

- **ProgID**

   Legt den Namen, den Container anstatt der CLSID des Objekts verwenden können.

## <a name="see-also"></a>Siehe auch

[ATL Simple Object (Einfaches ATL-Objekt)](../../atl/reference/adding-an-atl-simple-object.md)
