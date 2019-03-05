---
title: ATL COM+ 1.0 Komponenten-Assistent
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.class.atl.mts.overview
helpviewer_keywords:
- ATL projects, adding components
- ATL COM+ 1.0 Component Wizard
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
ms.openlocfilehash: df13c94eb0cc2aa7e2dea49aba6901f01fce0a15
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326425"
---
# <a name="atl-com-10-component-wizard"></a>ATL COM+ 1.0 Komponenten-Assistent

Verwenden Sie diesen Assistenten, um ein Objekt zu Ihrem Projekt hinzuzufügen, die COM+ 1.0-Dienste, einschließlich Transaktionen unterstützt.

Sie können angeben, ob das Objekt duale Schnittstellen und die Automatisierung unterstützt. Sie können auch Unterstützung für den Fehler Informationen der Schnittstelle, erweiterte Objekt Kontrolle, Transaktionen und asynchrone Message Queuing-angeben.

> [!WARNING]
> Ab Version 15.9 von Visual Studio 2017 ist dieser Codeassistent veraltet. Er wird in einer zukünftigen Version von Visual Studio entfernt. Dieser Assistent wird nur selten verwendet. Die Entfernung dieses Assistenten wirkt sich nicht auf die allgemeine Unterstützung für Active Template Library (ATL) und Microsoft Foundation Classes (MFC) aus. In [dieser Umfrage](https://www.surveymonkey.com/r/QDWKKCN) können Sie Ihr Feedback zu dieser Veraltung mitteilen. Ihr Feedback ist uns wichtig.

## <a name="remarks"></a>Hinweise

Ab Visual Studio 2008 wird von diesem Assistenten erstellte Registrierungsskript seine COM-Komponenten unter registriert **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **registerkomponenten für alle Benutzer** des ATL-Assistenten die Option.

## <a name="names"></a>Namen

Geben Sie die Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle anderen Felder bearbeitet werden können, unabhängig von den anderen. Wenn Sie den Text für ändern **Kurznamen**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Name in der COM-Abschnitt die Änderung wirkt sich die **Typ** und **ProgID** Dialogfelder, aber die **Schnittstelle** Name wird nicht geändert. Diese Namenssystem ist so ausgelegt, alle Namen leicht identifizierbaren für Sie, wie Sie das Steuerelement entwickeln.

- **Kurzname**

   Legt den abgekürzten Namen für das Objekt fest. Der Name, den Sie angeben, bestimmt die `Class` und `Coclass` Namen, die **cpp-Datei** und **.h-Datei** Namen, die **Schnittstelle** Namen verwenden, die **Typ** Namen, und die **ProgID**, es sei denn, Sie diese Felder einzeln ändern.

- **H-Datei**

   Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Klasse**

   Legt den Namen der Klasse erstellt werden. Dieser Name basiert auf den Namen, die Sie, in angeben **Kurznamen**ist 'C', das typische Präfix für einen Klassennamen vorangestellt.

- **CPP-Datei**

   Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

- **Zugeordnet sind**

   Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt eine attributierten ATL-Projekt hinzufügen, ist diese Option ausgewählt und nicht verfügbar, um zu ändern. Also können Sie ein Projekt erstellt wurde, mit Attribut-Unterstützung nur attributierter Objekte hinzufügen.

   Wenn Sie diese Option für ein ATL-Projekt, die nicht unterstützen Attribut verfügt auswählen, fordert der Assistent Sie angeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.

   Alle Objekte, die Sie hinzufügen, befolgen diese Einstellung werden festgelegt, wie in der Standardeinstellung zugeordnet sind (das Kontrollkästchen ist aktiviert). Sie können festlegen, löschen Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die keine Attribute verwendet.

   Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.

### <a name="com"></a>COM

Enthält Informationen über die COM-Funktionalität für das Objekt.

- **Co-Klasse**

   Legt den Namen der Komponentenklasse, die eine Liste der Schnittstellen, die vom Objekt unterstützten enthält.

> [!NOTE]
>  Wenn Sie das Projekt mithilfe von Attributen erstellen, oder auf dieser Seite des Assistenten angeben, dass die Komponente von COM+ 1.0-Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist das `coclass` Attribut.

- **Type**

   Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird

- **Interface**

   Legt die Schnittstelle, die Sie für Ihr Objekt zu erstellen. Diese Schnittstelle enthält die benutzerdefinierten Methoden.

- **ProgID**

   Legt den Namen, den Container anstatt der CLSID des Objekts verwenden können.

## <a name="see-also"></a>Siehe auch

[ATL COM+ 1.0-Komponente](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
