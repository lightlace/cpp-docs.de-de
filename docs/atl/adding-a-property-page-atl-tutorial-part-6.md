---
title: Hinzufügen einer Eigenschaftenseite (ATL-Lernprogramm, Teil 6)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
ms.openlocfilehash: 9287b7a15e3653212ed6a5428cdfe5a530ececc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198509"
---
# <a name="adding-a-property-page-atl-tutorial-part-6"></a>Hinzufügen einer Eigenschaftenseite (ATL-Lernprogramm, Teil 6)

Eigenschaftenseiten werden als getrennten COM-Objekte implementiert, die sie bei Bedarf gemeinsam genutzt werden können. In diesem Schritt tun Sie zum Hinzufügen einer Eigenschaftenseite für das Steuerelement die folgenden Aufgaben:

- Erstellen die Eigenschaftenseitenressource

- Hinzufügen von Code zum Erstellen und verwalten die Eigenschaftenseite

- Die Eigenschaftenseite hinzufügen für das Steuerelement

## <a name="creating-the-property-page-resource"></a>Erstellen die Eigenschaftenseitenressource

Um eine Eigenschaftenseite zu Ihrem Steuerelement hinzuzufügen, verwenden Sie die ATL-Eigenschaftenseite-Vorlage.

### <a name="to-add-a-property-page"></a>Hinzufügen einer Eigenschaftenseite

1. In **Projektmappen-Explorer**, mit der rechten Maustaste `Polygon`.

1. Klicken Sie im Kontextmenü auf **hinzufügen** > **neues Element**.

1. Wählen Sie aus der Liste der Vorlagen, **ATL** > **ATL-Eigenschaftenseite** , und klicken Sie auf **hinzufügen**.

1. Wenn die **ATL-Eigenschaftenseiten-Assistent** angezeigt wird, geben Sie *PolyProp* als die **kurze** Name.

1. Klicken Sie auf **Zeichenfolgen** zum Öffnen der **Zeichenfolgen** Seite, und geben Sie **& Polygon** als die **Titel**.

   Die **Titel** Seite ist die Eigenschaft die Zeichenfolge, die auf der Registerkarte für diese Seite wird angezeigt. Die **Dokumentzeichenfolge** finden Sie eine Beschreibung, die ein eigenschaftenrahmens verwendet, in einen Status oder eine QuickInfo zu platzieren. Beachten Sie, dass der Standardeigenschaft Frame dieser Zeichenfolge derzeit nicht verwendet, sodass Sie es mit den Standardinhalt lassen können. Generieren Sie keine **Hilfedatei** im Moment so löschen Sie den Eintrag in dieses Textfeld.

1. Klicken Sie auf **Fertig stellen**, und die Eigenschaft-Page-Objekt erstellt werden.

Die folgenden drei Dateien werden erstellt:

|Datei|Beschreibung|
|----------|-----------------|
|PolyProp.h|Enthält die C++-Klasse `CPolyProp`, die die Eigenschaftenseite implementiert.|
|PolyProp.cpp|Enthält die PolyProp.h-Datei.|
|PolyProp.rgs|Die Registrierungsskript, das die Eigenschaft-Page-Objekt registriert.|

Die folgenden codeänderungen werden auch vorgenommen:

- Die neue Eigenschaftenseite wird der Eintrag objektzuordnung in Polygon.cpp hinzu hinzugefügt.

- Die `PolyProp` Klasse der Polygon.idl-Datei hinzugefügt wird.

- Die Projektressource wird die neue Registrierungsskriptdatei PolyProp.rgs hinzugefügt.

- Die Projektressource für die Eigenschaftenseite wird eine Dialogfeldvorlage hinzugefügt.

- Die Zeichenfolgen von Eigenschaften, die Sie angegeben, werden die Ressourcen-Zeichenfolgentabelle hinzugefügt.

Fügen Sie nun die Felder, die auf der Eigenschaftenseite angezeigt werden sollen.

### <a name="to-add-fields-to-the-property-page"></a>Um Felder hinzuzufügen, klicken Sie auf der Eigenschaftenseite

1. In **Projektmappen-Explorer**, doppelklicken Sie auf die Ressourcendatei Polygon.rc. Dadurch wird geöffnet, **Ressourcenansicht**.

1. In **Ressourcenansicht**, erweitern Sie die `Dialog` Knoten, und doppelklicken Sie auf `IDD_POLYPROP`. Beachten Sie, dass das Dialogfeld wird angezeigt, bis auf eine Bezeichnung leer, der anzeigt ist, können Sie Ihre Steuerelemente hier einfügen.

1. Wählen Sie diese Bezeichnung, und ändern sie die Zeichenfolge `Sides:` durch Ändern der **Beschriftung** Text in die **Eigenschaften** Fenster.

1. Ändern der Größe des Bezeichnungsfelds, damit sie die Größe des Texts passt.

1. Ziehen Sie ein **Bearbeitungssteuerelement** aus der **Toolbox** rechts neben der Bezeichnung.

1. Ändern Sie schließlich die **ID** des Bearbeitungssteuerelements zum `IDC_SIDES` mithilfe der **Eigenschaften** Fenster.

Dies schließt den Prozess der Erstellung der Eigenschaftenseitenressource ab.

## <a name="adding-code-to-create-and-manage-the-property-page"></a>Hinzufügen von Code zum Erstellen und verwalten die Eigenschaftenseite

Nun, dass Sie die Eigenschaftenseitenressource erstellt haben, müssen Sie den Implementierungscode schreiben.

Aktivieren Sie zunächst die `CPolyProp` Klasse, um die Anzahl der Seiten in Ihrem Objekt bei der **übernehmen** gedrückt wird.

### <a name="to-modify-the-apply-function-to-set-the-number-of-sides"></a>So ändern Sie die Funktion "Übernehmen" zum Festlegen der Anzahl der Seiten

1. Ersetzen Sie die `Apply` in PolyProp.h-Funktion mit den folgenden Code:

    [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_1.h)]

Eine Eigenschaftenseite kann mehr als einen Client zu einem Zeitpunkt angefügt haben also die `Apply` Funktion führt eine Schleife und ruft `put_Sides` auf jedem Client mit dem Wert, der aus das Bearbeitungsfeld abgerufen. Sie verwenden die [CComQIPtr](../atl/reference/ccomqiptr-class.md) -Klasse, die führt die `QueryInterface` für jedes Objekt Abrufen der `IPolyCtl` -Schnittstelle aus der `IUnknown` Schnittstelle (in gespeicherten der `m_ppUnk` Array).

Der Code überprüft nun die Einstellung der `Sides` Eigenschaft, die tatsächlich geklappt hat. Wenn ein Fehler auftritt, wird der Code zeigt ein Meldungsfeld anzeigen von Fehlerdetails aus der `IErrorInfo` Schnittstelle. In der Regel fragt ein Container ein Objekt für die `ISupportErrorInfo` -Schnittstelle und ruft `InterfaceSupportsErrorInfo` zuerst, um festzustellen, ob das Objekt festlegen von Fehlerinformationen unterstützt. Sie können diese Aufgabe überspringen.

[CComPtr](../atl/reference/ccomptr-class.md) unterstützt Sie beim automatisch behandeln die verweiszählung, sodass Sie nicht aufrufen, müssen `Release` auf der Schnittstelle. `CComBSTR` BSTR zu verarbeiten, hilft Ihnen, sodass Sie nicht zum Ausführen des letzten `SysFreeString` aufrufen. Sie gehen auch die verschiedenen Klassen für die zeichenfolgenkonvertierung, damit Sie das BSTR, bei Bedarf konvertieren können (Dies ist das Makro USES_CONVERSION am Anfang der Funktion).

Sie müssen auch legen Sie die Eigenschaftenseite dirty-Flag gibt an, dass die **übernehmen** Schaltfläche aktiviert werden soll. Dies tritt auf, wenn der Benutzer den Wert in ändert die **Seiten** "Bearbeiten".

### <a name="to-handle-the-apply-button"></a>Verarbeiten Sie die Schaltfläche "anwenden"

1. In **Klassenansicht**, mit der rechten Maustaste `CPolyProp` , und klicken Sie auf **Eigenschaften** im Kontextmenü auf.

1. In der **Eigenschaften** Fenster, klicken Sie auf die **Ereignisse** Symbol.

1. Erweitern Sie die `IDC_SIDES` Knoten in der Ereignisliste.

1. Wählen Sie `EN_CHANGE`, und klicken Sie im Dropdown-Menü auf der rechten Seite auf  **\<hinzufügen > OnEnChangeSides**. Die `OnEnChangeSides` Handlerdeklaration wird Polyprop.h und die Implementierung des Handlers PolyProp.cpp hinzugefügt werden.

Als Nächstes ändern Sie den Handler.

### <a name="to-modify-the-onenchangesides-method"></a>So ändern Sie die OnEnChangeSides-Methode

1. Fügen Sie den folgenden Code in Polyprop.cpp, um die `OnEnChangeSides` Methode (jeglicher Code, der vom Assistenten löschen):

    [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_2.cpp)]

`OnEnChangeSides` wird aufgerufen, wenn eine `WM_COMMAND` Nachricht wird gesendet, mit der `EN_CHANGE` Benachrichtigung für die `IDC_SIDES` Steuerelement. `OnEnChangeSides` Ruft dann `SetDirty` und übergibt "true", um anzugeben, dass die Eigenschaftenseite jetzt geändert und die **übernehmen** Schaltfläche aktiviert werden soll.

## <a name="adding-the-property-page-to-the-control"></a>Die Eigenschaftenseite hinzufügen für das Steuerelement

Der ATL-Eigenschaftenseite-Vorlage und den Assistenten fügen auf der Seite der zu Ihrem Steuerelement für Sie automatisch, Sie nicht, da es möglicherweise mehrere Steuerelemente in Ihrem Projekt. Sie müssen einen Eintrag in der eigenschaftenzuordnung des Steuerelements hinzufügen.

### <a name="to-add-the-property-page"></a>Um die Eigenschaftenseite hinzufügen

1. Öffnen Sie PolyCtl.h hinzu, und fügen Sie die folgenden Zeilen auf die eigenschaftszuordnung:

    [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_3.h)]

Eigenschaftenzuordnung des Steuerelements sieht nun folgendermaßen aus:

[!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/cpp/adding-a-property-page-atl-tutorial-part-6_4.h)]

Konnten Sie hinzugefügt haben eine `PROP_PAGE` Makro, mit der CLSID Ihr Eigenschaftenseite, wenn Sie jedoch die `PROP_ENTRY` Makro wie dargestellt, die `Sides` Eigenschaftswert wird auch gespeichert werden, wenn das Steuerelement gespeichert wird.

Die drei Parameter für das Makro gibt der Beschreibung der Eigenschaft die DISPID der Eigenschaft und die CLSID der Eigenschaftenseite, die die Eigenschaft enthält. Dies ist nützlich, wenn Sie z. B. laden das Steuerelement in Visual Basic und die Anzahl der Seiten zur Entwurfszeit festgelegt. Da die Anzahl der Seiten, gespeichert wird Wenn Sie Visual Basic-Projekt erneut laden, wird die Anzahl der Seiten wiederhergestellt werden.

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

Nun erstellen Sie das Steuerelement, und in Testcontainer für ActiveX-Steuerelement einfügen. In **Testcontainer**auf die **bearbeiten** Menü klicken Sie auf **PolyCtl Klassenobjekt**. Die Eigenschaftenseite angezeigt wird, mit den Informationen, die, den Sie hinzugefügt haben.

Die **übernehmen** Schaltfläche ist zunächst deaktiviert. Geben Sie einen Wert in der **Seiten** Feld und die **übernehmen** Schaltfläche aktiviert wird. Nachdem Sie den Wert eingegeben haben, klicken Sie auf die **übernehmen** Schaltfläche. Die Steuerelement-Anzeige geändert wird, und die **übernehmen** Schaltfläche wieder deaktiviert. Versuchen Sie, einen ungültigen Wert. Daraufhin wird ein Meldungsfeld mit die fehlerbeschreibung, die Sie festlegen, aus der `put_Sides` Funktion.

Als Nächstes werden Sie das Steuerelement auf einer Webseite einfügen.

[Zurück zu Schritt 5](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [mit Schritt 7 fort](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
