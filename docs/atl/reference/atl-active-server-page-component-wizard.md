---
title: ATL-Assistent für Active Server Page-Komponenten
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.overview
helpviewer_keywords:
- ASP components, creating in ATL
- ATL Active Server Page Component Wizard
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
ms.openlocfilehash: 80d7eefaa4b12d5aab8970f4b3c81fc644226e07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510863"
---
# <a name="atl-active-server-page-component-wizard"></a>ATL-Assistent für Active Server Page-Komponenten

Dieser Assistent fügt dem Projekt eine Komponente für Active Server Pages (ASP). Microsoft Internet Information Services (IIS) verwendet die ASP-Komponenten als Teil der erweiterten Webseite Development-Architektur.

Mithilfe dieses Assistenten können Sie angeben, dass die Komponente threading-Modell und die aggregationsunterstützung der. Sie können auch Unterstützung für die Informationen fehlerschnittstelle, Verbindungspunkte und das Marshalling von Freethreadobjekten angeben.

> [!WARNING]
> Ab Version 15.9 von Visual Studio 2017 ist dieser Codeassistent veraltet. Er wird in einer zukünftigen Version von Visual Studio entfernt. Dieser Assistent wird nur selten verwendet. Die Entfernung dieses Assistenten wirkt sich nicht auf die allgemeine Unterstützung für Active Template Library (ATL) und Microsoft Foundation Classes (MFC) aus. In [dieser Umfrage](https://www.surveymonkey.com/r/QDWKKCN) können Sie Ihr Feedback zu dieser Veraltung mitteilen. Ihr Feedback ist uns wichtig.

## <a name="remarks"></a>Hinweise

Ab Visual Studio 2008 wird von diesem Assistenten erstellte Registrierungsskript seine COM-Komponenten unter registriert **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **registerkomponenten für alle Benutzer** des ATL-Assistenten die Option.

## <a name="names"></a>Namen

Geben Sie die Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle anderen Felder bearbeitet werden können, unabhängig von den anderen. Wenn Sie den Text für ändern **Kurznamen**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen.

Wenn Sie ändern die **Co-Klasse** Name in der COM-Abschnitt die Änderung wirkt sich die **Typ** und **ProgID** Dialogfelder, aber die **Schnittstelle** Name wird nicht geändert. Diese Namenssystem ist so ausgelegt, alle Namen leicht identifizierbaren für Sie, wie Sie das Steuerelement entwickeln.

### <a name="c"></a>C++

Enthält Informationen für die C++-Klasse, die für das Objekt erstellt wurde.

- **Kurzname**

   Legt den Stammnamen für das Objekt. Der Name, den Sie angeben, bestimmt die `Class` und **Co-Klasse** Namen, die **cpp-Datei** und **.h-Datei** Namen, die **Schnittstelle**Namen, den **Typ** Namen, und die **ProgID**, es sei denn, Sie diese Felder einzeln ändern.

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

   Wenn Sie diese Option für ein ATL-Projekt, die nicht unterstützen Attribut verfügt auswählen, fordert der Assistent Sie angeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.

   Wird für nicht attributierte Projekte standardmäßig alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributiert festgelegt werden (das Kontrollkästchen ist aktiviert). Sie können festlegen, löschen Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die keine Attribute verwendet.

   Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.

### <a name="com"></a>COM

Enthält Informationen über die COM-Funktionalität für das Objekt.

- **Co-Klasse**

   Legt den Namen der Komponentenklasse, die eine Liste der Schnittstellen, die vom Objekt unterstützten enthält. Das Projekt oder dieses Objekt Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist das **Co-Klasse** Attribut.

- **Type**

   Legt fest, die Beschreibung des Objekts, die in der Registrierung für die Co-Klasse angezeigt wird.

- **Interface**

   Legt die Schnittstelle, die Sie für Ihr Objekt zu erstellen. Diese Schnittstelle enthält die benutzerdefinierten Methoden.

- **ProgID**

   Legt den Namen, den Container anstatt der CLSID des Objekts verwenden können.

## <a name="see-also"></a>Siehe auch

[ATL Active Server Page-Komponente](../../atl/reference/adding-an-atl-active-server-page-component.md)
