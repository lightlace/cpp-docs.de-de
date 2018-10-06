---
title: Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2) | Microsoft-Dokumentation
ms.custom: get-started-article
ms.date: 09/26/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d4918887e36e405c5efb0d5280cea5976f14bb9
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821280"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2)

In diesem Schritt fügen Sie Ihrem Projekt ein Steuerelement hinzu, erstellen es und testen es auf einer Webseite.

## <a name="procedures"></a>Verfahren

### <a name="to-add-an-object-to-an-atl-project"></a>So fügen Sie einem ATL-Projekt ein Objekt hinzu

1. In **Projektmappen-Explorer**, mit der rechten Maustaste die `Polygon` Projekt.

1. Zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **neues Element** im Untermenü.

    Das Dialogfeld **Neues Element hinzufügen** wird angezeigt. Die verschiedenen Objektkategorien werden in der Struktur links aufgeführt.

1. Klicken Sie auf die **ATL** Ordner.

1. Wählen Sie aus der Liste der Vorlagen auf der rechten Seite, **ATL-Steuerelement**. Klicken Sie auf **Hinzufügen**. Die **ATL-Steuerelement** -Assistent wird geöffnet, und Sie können das Steuerelement konfigurieren.

1. Typ `PolyCtl` als kurz ein, und beachten Sie, dass die anderen Felder automatisch vervollständigt werden. Klicken Sie nicht auf **Fertig stellen** noch installieren müssen, denn Sie einige Änderungen vornehmen müssen.

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

Sie müssen einige zusätzliche Einstellungen in der **ATL-Steuerelement** Assistenten.

### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>So aktivieren Sie die Unterstützung für aussagekräftige Fehlerinformationen und Verbindungspunkte

1. Klicken Sie auf **Optionen** zum Öffnen der **Optionen** Seite.

1. Wählen Sie die **Verbindungspunkte** Kontrollkästchen. Dadurch wird die Unterstützung einer Ausgangsschnittstelle in der IDL-Datei erstellt.

Sie können auch Schnittstellen zum Erweitern die Funktionalität des Steuerelements hinzufügen.

### <a name="to-extend-the-controls-functionality"></a>Um die Funktionalität des Steuerelements zu erweitern.

1. Klicken Sie auf **Schnittstellen** zum Öffnen der **Schnittstellen** Seite.

1. Wählen Sie `IProvideClassInfo2` , und klicken Sie auf die **einrichten** Pfeil zu verschieben der **unterstützte** Liste.

1. Wählen Sie `ISpecifyPropertyPages` , und klicken Sie auf die **einrichten** Pfeil zu verschieben der **unterstützte** Liste.

Sie können das Steuerelement auch einfügbar machen. Das heißt, es kann in Anwendungen eingebettet werden, die eingebettete Objekten unterstützen, wie z. B. Excel oder Word.

### <a name="to-make-the-control-insertable"></a>So machen Sie das Steuerelement einfügbar

1. Klicken Sie auf **Darstellung** zum Öffnen der **Darstellung** Seite.

1. Wählen Sie die **Insertable** Kontrollkästchen.

Das Polygon, das durch das Objekt angezeigt wird, verfügt über einfarbige Füllung. Deshalb müssen Sie eine `Fill Color`-Basiseigenschaft hinzufügen.

### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>So fügen Sie eine Füllfarben-Basiseigenschaft hinzu und erstellen das Steuerelement

1. Klicken Sie auf **Basiseigenschaften** zum Öffnen der **Basiseigenschaften** Seite.

1. Klicken Sie unter **nicht unterstützt**, führen Sie einen Bildlauf nach unten in der Liste möglicher Basiseigenschaften. Wählen Sie `Fill Color` , und klicken Sie auf die **einrichten** Pfeil zu verschieben der **unterstützte** Liste.

1. Dies vervollständigt die Optionen für das Steuerelement. Klicken Sie auf **Fertig stellen**.

Während der Assistent das Steuerelement erstellte, wurden mehrere Codeänderungen und Dateihinzufügungen ausgeführt. Die folgenden Dateien wurden erstellt:

|Datei|Beschreibung|
|----------|-----------------|
|PolyCtl.h|Sie enthält den größten Teil der Implementierung der C++-Klasse `CPolyCtl`.|
|PolyCtl.cpp|Sie enthält die verbleibenden Teile von `CPolyCtl`.|
|PolyCtl.rgs|Eine Textdatei, die das Registrierungsskript enthält, das verwendet wird, um das Steuerelement zu registrieren.|
|PolyCtl.htm|Eine Webseite, die einen Verweis auf das neu erstellte Steuerelement enthält.|

Der Assistent führt auch die folgenden Codeänderungen aus:

- Er fügte den Dateien "stdafx.h" und "stdafx.cpp" eine `#include`-Anweisung hinzu, um die zur Unterstützung von Steuerelementen erforderlichen ATL-Dateien einzuschließen.

- Er änderte Polygon.idl, um Details des neuen Steuerelements einzuschließen.

- Er fügte das neue Steuerelement zur Objektzuordnung in Polygon.cpp hinzu.

Jetzt können Sie das Steuerelement erstellen, um es in Aktion zu sehen.

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

### <a name="to-build-and-test-the-control"></a>So erstellen Sie das Steuerelement und testen es

1. Auf der **erstellen** Menü klicken Sie auf **Polygon erstellen**.

    Wenn das Steuerelement erstellen abgeschlossen ist, mit der rechten Maustaste PolyCtl.htm in **Projektmappen-Explorer** , und wählen Sie **in Browser anzeigen**. Die HTML-Webseite, die das Steuerelement enthält, wird angezeigt. Daraufhin sollte eine Seite mit dem Titel "ATL 8.0-Testseite für Objekt PolyCtl" und der Text PolyCtl. Dies ist Ihr Steuerelement.

> [!NOTE]
> Wenn das Steuerelement nicht sichtbar ist, wissen Sie, dass es sich bei einigen Browsern Einstellungen Anpassungen ActiveX-Steuerelemente ausführen müssen. Finden Sie im Browser auf die Dokumentation zum Aktivieren von ActiveX-Steuerelemente.

> [!NOTE]
> Wenn Sie beim Abschließen dieses Lernprogramms eine Fehlermeldung erhalten, dass die DLL-Datei nicht erstellt werden kann, schließen Sie die Datei "PolyCtl.htm" und den Testcontainer für ActiveX-Steuerelemente und erstellen Sie die Projektmappe erneut. Wenn Sie die DLL immer noch nicht erstellen können, starten Sie den Computer neu oder melden Sie sich ab (wenn Sie die Terminaldienste verwenden).

Als Nächstes fügen Sie dem Steuerelement eine benutzerdefinierte Eigenschaft hinzu.

[Zurück zu Schritt 1](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [weiter zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
