---
title: Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
ms.openlocfilehash: 53f38d63a44328bf014f04635a24989a875ddf1e
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344329"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2)

In diesem Schritt haben Sie Hinzufügen eines Steuerelements zu Ihrem Projekt erstellen und testen es auf einer Webseite.

## <a name="procedures"></a>Verfahren

### <a name="to-add-an-object-to-an-atl-project"></a>So fügen Sie einem ATL-Projekt ein Objekt hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt `Polygon`.

1. Zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **neues Element** im Untermenü.

    Das Dialogfeld **Neues Element hinzufügen** wird angezeigt. Die verschiedenen Objektkategorien werden in der Struktur links aufgeführt.

1. Klicken Sie auf die **ATL** Ordner.

1. Wählen Sie aus der Liste der Vorlagen auf der rechten Seite, **ATL-Steuerelement**. Klicken Sie auf **Hinzufügen**. Die **ATL-Steuerelement** -Assistent wird geöffnet, und Sie können das Steuerelement konfigurieren.

1. Typ `PolyCtl` als kurz ein, und beachten Sie, dass die anderen Felder automatisch vervollständigt werden. Klicken Sie nicht **Fertig stellen** noch installieren müssen, da Sie einige weitere Änderungen vornehmen müssen.

Die **ATL-Steuerelement** des Assistenten **Namen** Seite enthält die folgenden Felder:

|Feld|Inhalt|
|-----------|--------------|
|**Kurzname**|Der Name, den Sie für das Steuerelement eingegeben haben.|
|**Klasse**|Der C++-Klassenname, der erstellt wurde, um das Steuerelement zu implementieren.|
|**H-Datei**|Die Datei, die erstellt wurde, um die Definition der C++-Klasse zu enthalten.|
|**CPP-Datei**|Die Datei, die erstellt wurde, um die Implementierung der C++-Klasse zu enthalten.|
|**Co-Klasse**|Der Name der Komponentenklasse für dieses Steuerelement.|
|**Interface**|Der Name der Schnittstelle, auf der das Steuerelement die benutzerdefinierten Methoden und Eigenschaften implementiert.|
|**Type**|Eine Beschreibung für das Steuerelement.|
|**ProgID**|Der lesbare Name, der verwendet werden kann, um die CLSID des Steuerelements zu suchen.|

Finden Sie einige zusätzliche Einstellungen geändert werden müssen, der **ATL-Steuerelement** Assistenten.

### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>So aktivieren Sie die Unterstützung für aussagekräftige Fehlerinformationen und Verbindungspunkte

1. Klicken Sie auf **Optionen** zum Öffnen der **Optionen** Seite.

1. Wählen Sie die **Verbindungspunkte** Kontrollkästchen. Dieser Option wird die Unterstützung einer Ausgangsschnittstelle in der IDL-Datei erstellt.

Sie können auch Schnittstellen zum Erweitern die Funktionalität des Steuerelements hinzufügen.

### <a name="to-extend-the-controls-functionality"></a>Um die Funktionalität des Steuerelements zu erweitern.

1. Klicken Sie auf **Schnittstellen** zum Öffnen der **Schnittstellen** Seite.

1. Wählen Sie `IProvideClassInfo2` , und klicken Sie auf die **einrichten** Pfeil zu verschieben der **unterstützte** Liste.

1. Wählen Sie `ISpecifyPropertyPages` , und klicken Sie auf die **einrichten** Pfeil zu verschieben der **unterstützte** Liste.

Sie können auch das Steuerelement, *einfügbar*, was bedeutet, dass in Anwendungen mit Unterstützung für eingebettete Objekte, z. B. Excel oder Word kann eingebettet ist.

### <a name="to-make-the-control-insertable"></a>So machen Sie das Steuerelement einfügbar

1. Klicken Sie auf **Darstellung** zum Öffnen der **Darstellung** Seite.

1. Wählen Sie die **Insertable** Kontrollkästchen.

Das Polygon, das durch das Objekt angezeigt wird, verfügt über einfarbige Füllung. Deshalb müssen Sie eine `Fill Color`-Basiseigenschaft hinzufügen.

### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>So fügen Sie eine Füllfarben-Basiseigenschaft hinzu und erstellen das Steuerelement

1. Klicken Sie auf **Basiseigenschaften** zum Öffnen der **Basiseigenschaften** Seite.

1. Klicken Sie unter **nicht unterstützt**, führen Sie einen Bildlauf nach unten in der Liste möglicher Basiseigenschaften. Wählen Sie `Fill Color` , und klicken Sie auf die **einrichten** Pfeil zu verschieben der **unterstützte** Liste.

1. Klicken Sie auf **Fertig stellen**.

Der Assistent das Steuerelement erstellt wird, treten auf mehrere codeänderungen und dateihinzufügungen. Die folgenden Dateien werden erstellt:

|Datei|Beschreibung|
|----------|-----------------|
|PolyCtl.h|Sie enthält den größten Teil der Implementierung der C++-Klasse `CPolyCtl`.|
|PolyCtl.cpp|Sie enthält die verbleibenden Teile von `CPolyCtl`.|
|PolyCtl.rgs|Eine Textdatei, die das Registrierungsskript enthält, das verwendet wird, um das Steuerelement zu registrieren.|
|PolyCtl.htm|Eine Webseite, die einen Verweis auf das neu erstellte Steuerelement enthält.|

Der Assistent stellt auch die folgenden codeänderungen vor:

- Fügt eine `#include` Anweisung, um die Dateien "stdafx.h" und "stdafx.cpp" sollen die ATL-Dateien zur Unterstützung von Steuerelementen erforderlich.

- Ändert die Polygon.idl, um die Details des neuen Steuerelements einzuschließen.

- Fügt das neue Steuerelement zur objektzuordnung in Polygon.cpp hinzu.

Jetzt können Sie das Steuerelement erstellen, um es in Aktion zu sehen.

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

### <a name="to-build-and-test-the-control"></a>So erstellen Sie das Steuerelement und testen es

1. Auf der **erstellen** Menü klicken Sie auf **Polygon erstellen**.

    Wenn das Steuerelement erstellen abgeschlossen ist, mit der rechten Maustaste PolyCtl.htm in **Projektmappen-Explorer** , und wählen Sie **in Browser anzeigen**. Die HTML-Webseite mit dem Steuerelement wird angezeigt. Daraufhin sollte eine Seite mit dem Titel "ATL 8.0 Testseite für Objekt PolyCtl" sowie das Steuerelement den Text PolyCtl.

> [!NOTE]
> Wenn das Steuerelement nicht sichtbar ist, wissen Sie, dass es sich bei einigen Browsern Einstellungen Anpassungen ActiveX-Steuerelemente ausführen müssen. Lesen Sie im Browser auf die Dokumentation zum Aktivieren von ActiveX-Steuerelemente.

> [!NOTE]
> Beim Abschließen dieses Lernprogramms eine Fehlermeldung erhalten, dass die DLL-Datei kann nicht erstellt werden, schließen Sie die Datei "PolyCtl.htm" und den Testcontainer für ActiveX-Steuerelement, und erstellen Sie die Projektmappe erneut. Wenn Sie noch die DLL zu erstellen, starten Sie den Computer neu, oder melden Sie sich bei Verwendung von "Terminal Services".

Als Nächstes fügen Sie eine benutzerdefinierte Eigenschaft für das Steuerelement.

[Zurück zu Schritt 1](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [weiter zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
