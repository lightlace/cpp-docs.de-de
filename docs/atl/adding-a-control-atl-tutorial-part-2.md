---
title: Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
ms.openlocfilehash: b7952f42b24c4211a2c44ea71fd17e4f65c3421a
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630710"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2)

In diesem Schritt fügen Sie dem Projekt ein-Steuerelement hinzu, erstellen es und testen es auf einer Webseite.

## <a name="procedures"></a>Verfahren

### <a name="to-add-an-object-to-an-atl-project"></a>So fügen Sie einem ATL-Projekt ein Objekt hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt `Polygon`.

1. Zeigen Sie im Kontextmenü auf **Hinzufügen** , und klicken Sie im Untermenü auf **Neues Element** .

    Das Dialogfeld **Neues Element hinzufügen** wird angezeigt. Die verschiedenen Objektkategorien werden in der Struktur links aufgeführt.

1. Klicken Sie auf den Ordner **ATL** .

1. Wählen Sie in der Liste der Vorlagen auf der rechten Seite **ATL-Steuer**Element aus. Klicken Sie auf **Hinzufügen**. Der **ATL-Steuer** Element-Assistent wird geöffnet, und Sie können das Steuerelement konfigurieren.

1. Geben `PolyCtl` Sie als Kurzname ein, und beachten Sie, dass die anderen Felder automatisch abgeschlossen werden. Klicken Sie noch nicht auf **Fertig** stellen, da Sie einige Änderungen vornehmen müssen.

Die **namens** Seite des **ATL-Steuer** Element-Assistenten enthält die folgenden Felder:

|Feld|Inhalt|
|-----------|--------------|
|**Kurzname**|Der Name, den Sie für das Steuerelement eingegeben haben.|
|**Klasse**|Der C++-Klassenname, der erstellt wurde, um das Steuerelement zu implementieren.|
|**H-Datei**|Die Datei, die erstellt wurde, um die Definition der C++-Klasse zu enthalten.|
|**CPP-Datei**|Die Datei, die erstellt wurde, um die Implementierung der C++-Klasse zu enthalten.|
|**Co-Klasse**|Der Name der Komponentenklasse für dieses Steuerelement.|
|**Interface**|Der Name der Schnittstelle, auf der das Steuerelement die benutzerdefinierten Methoden und Eigenschaften implementiert.|
|**Typ**|Eine Beschreibung für das Steuerelement.|
|**ProgID**|Der lesbare Name, der verwendet werden kann, um die CLSID des Steuerelements zu suchen.|

Im **ATL-Steuer** Element-Assistenten müssen mehrere zusätzliche Einstellungen geändert werden.

### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>So aktivieren Sie die Unterstützung für aussagekräftige Fehlerinformationen und Verbindungspunkte

1. Klicken Sie auf **Optionen** , um die Seite **Optionen** zu öffnen.

1. Aktivieren Sie das Kontrollkästchen **Verbindungspunkte** . Diese Option erstellt die Unterstützung für eine ausgehende Schnittstelle in der IDL-Datei.

Sie können auch Schnittstellen hinzufügen, um die Funktionalität des Steuer Elements zu erweitern.

### <a name="to-extend-the-controls-functionality"></a>So erweitern Sie die Funktionalität des Steuer Elements

1. Klicken Sie zum Öffnen der **Schnittstellen** Seite auf **Schnittstellen** .

1. Wählen `IProvideClassInfo2` Sie den Pfeil nach **oben** aus, und klicken Sie darauf, um ihn in die Liste **unterstützte**

1. Wählen `ISpecifyPropertyPages` Sie den Pfeil nach **oben** aus, und klicken Sie darauf, um ihn in die Liste **unterstützte**

Sie können auch das Steuerelementeinbetten, d. h. es kann in Anwendungen eingebettet werden, die eingebettete Objekte unterstützen, wie z. b. Excel oder Word.

### <a name="to-make-the-control-insertable"></a>So machen Sie das Steuerelement einfügbar

1. Klicken Sie auf Darstellung, um die Seite Darstellung zu öffnen.

1. Aktivieren Sie das Kontrollkästchen **Insertable** .

Das Polygon, das durch das Objekt angezeigt wird, verfügt über einfarbige Füllung. Deshalb müssen Sie eine `Fill Color`-Basiseigenschaft hinzufügen.

### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>So fügen Sie eine Füllfarben-Basiseigenschaft hinzu und erstellen das Steuerelement

1. Klicken Sie auf **Eigenschaften** , um die Seite mit den vordefinierten **Eigenschaften** zu öffnen.

1. Scrollen Sie unter **nicht unterstützt**die Liste der möglichen vordefinierten Eigenschaften in der Liste nach unten. Wählen `Fill Color` Sie den Pfeil nach **oben** aus, und klicken Sie darauf, um ihn in die Liste **unterstützte**

1. Klicken Sie auf **Fertig stellen**.

Wenn der Assistent das Steuerelement erstellt, treten mehrere Codeänderungen und Datei Ergänzungen auf. Die folgenden Dateien werden erstellt:

|Datei|Beschreibung|
|----------|-----------------|
|PolyCtl.h|Sie enthält den größten Teil der Implementierung der C++-Klasse `CPolyCtl`.|
|PolyCtl.cpp|Sie enthält die verbleibenden Teile von `CPolyCtl`.|
|PolyCtl.rgs|Eine Textdatei, die das Registrierungsskript enthält, das verwendet wird, um das Steuerelement zu registrieren.|
|PolyCtl.htm|Eine Webseite, die einen Verweis auf das neu erstellte Steuerelement enthält.|

Der Assistent führt auch die folgenden Codeänderungen durch:

- Fügt den `#include` vorkompilierten Header Dateien eine-Anweisung hinzu, um die zum unterstützen von Steuerelementen erforderlichen ATL-Dateien einzuschließen.

- Ändert Polygon. idl, um Details zum neuen Steuerelement einzuschließen.

- Fügt der Objekt Zuordnung in Polygon. cpp das neue-Steuerelement hinzu.

Jetzt können Sie das Steuerelement erstellen, um es in Aktion zu sehen.

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

### <a name="to-build-and-test-the-control"></a>So erstellen Sie das Steuerelement und testen es

1. Klicken Sie im Menü **Erstellen** auf **Polygon erstellen**.

    Klicken Sie nach Abschluss der Erstellung des Steuer Elements in **Projektmappen-Explorer** mit der rechten Maustaste auf PolyCtl. htm, und wählen Sie **in Browser anzeigen aus**. Die HTML-Webseite, die das Steuerelement enthält, wird angezeigt. Es sollte eine Seite mit dem Titel "ATL 8,0 TestPage für das Objekt PolyCtl" und Ihrem Steuerelement als Text PolyCtl angezeigt werden.

> [!NOTE]
> Wenn das Steuerelement nicht sichtbar ist, wissen Sie, dass einige Browser Einstellungs Anpassungen erfordern, um ActiveX-Steuerelemente auszuführen. Informationen zum Aktivieren von ActiveX-Steuerelementen finden Sie in der Dokumentation des Browsers.

> [!NOTE]
> Wenn Sie beim Abschließen dieses Tutorials eine Fehlermeldung erhalten, dass die DLL-Datei nicht erstellt werden kann, schließen Sie die Datei PolyCtl. htm und den Test Container des ActiveX-Steuer Elements, und erstellen Sie die Projekt Mappe erneut. Wenn Sie die dll immer noch nicht erstellen können, starten Sie den Computer neu, oder melden Sie sich ab, wenn Sie terminaldienstedienste verwenden.

Als Nächstes fügen Sie dem Steuerelement eine benutzerdefinierte Eigenschaft hinzu.

[Zurück zu Schritt 1](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [In Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
