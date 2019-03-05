---
title: 'MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
ms.openlocfilehash: b90aa331c289caf827785af2eeba037e70f686ab
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281929"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements

In diesem Artikel wird beschrieben, die ActiveX-Steuerelement gezeichnet werden und wie Sie ändern können, Paint-Code, um den Prozess zu optimieren. (Finden Sie unter [optimieren Steuerelements zeichnen](../mfc/optimizing-control-drawing.md) für Techniken zum Zeichnen zu optimieren, indem Sie einzeln Steuerelemente ohne zuvor ausgewählten GDI-Objekte wiederherstellen. Nachdem alle Steuerelemente gezeichnet wurden, kann die Container automatisch die ursprünglichen Objekte wiederhergestellt werden.)

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Beispiele in diesem Artikel werden von einem Steuerelement, das von der MFC-ActiveX-Steuerelement-Assistenten mit Standardeinstellungen erstellt. Weitere Informationen zum Erstellen von Anwendungen Skelett-Steuerelements mit MFC-ActiveX-Steuerelement-Assistenten finden Sie im Artikel [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md).

Die folgenden Themen werden behandelt:

- [Der Gesamtprozess für das Zeichnen eines Steuerelements und der Code, der von der ActiveX-Steuerelement-Assistent zur Unterstützung der Darstellung erstellt](#_core_the_painting_process_of_an_activex_control)

- [Gewusst wie: Optimieren des zeichnen-Vorgangs](#_core_optimizing_your_paint_code)

- [Gewusst wie: Zeichnen des Steuerelements mit Metadateien](#_core_painting_your_control_using_metafiles)

##  <a name="_core_the_painting_process_of_an_activex_control"></a> Der Zeichnen-Prozess, der ein ActiveX-Steuerelement

Wenn ActiveX-Steuerelemente zuerst angezeigt werden, oder neu gezeichnet werden, folgen sie einen zeichnen-Prozess ähnlich für andere Anwendungen, die entwickelt wurden, verwenden von MFC, mit einem wichtigen Unterschied: ActiveX-Steuerelemente können in einer aktiven oder inaktiven Status sein.

Ein aktives Steuerelement wird in einem ActiveX-Steuerelement-Container von einem untergeordneten Fenster dargestellt. Wie andere Windows ist es selbst zu zeichnen, wenn eine WM_PAINT-Meldung empfangen wird. Basisklasse des Steuerelements [COleControl](../mfc/reference/colecontrol-class.md), behandelt diese Meldung in die `OnPaint` Funktion. Diese Standardimplementierung Ruft die `OnDraw` Funktion des Steuerelements.

Ein Inaktives Steuerelement wird unterschiedlich gezeichnet. Wenn das Steuerelement aktiv ist, ist das Fenster nicht sichtbar oder nicht vorhanden ist, damit es keine zeichennachricht empfangen kann. Stattdessen ruft der Steuerelementcontainer direkt die `OnDraw` Funktion des Steuerelements. Dies unterscheidet sich von Zeichnen-Prozess in, das ein aktives Steuerelement die `OnPaint` Memberfunktion nie aufgerufen wird.

Wie in den vorherigen Absätzen erörtert, hängt wie ein ActiveX-Steuerelement aktualisiert wird, vom Zustand des Steuerelements. Aber da das Framework Ruft die `OnDraw` Memberfunktion in beiden Fällen fügen Sie die meisten den zeichnen-Code in diese Memberfunktion.

Die `OnDraw` Member-Funktion behandelt das Zeichnen von Steuerelementen. Wenn ein Steuerelement nicht aktiv ist, ruft der Steuerelement-Container `OnDraw`, übergeben den Gerätekontext, der dem Steuerelementcontainer und die Koordinaten des rechteckigen Bereichs, der vom Steuerelement beansprucht wird.

Übergeben Sie das Rechteck durch das Framework die `OnDraw` Memberfunktion enthält des Bereichs, der vom Steuerelement. Wenn das Steuerelement aktiv ist, wird die oberen linken Ecke (0, 0) und der Gerätekontext, der übergeben wird, für das untergeordnete Fenster, das das Steuerelement enthält. Wenn das Steuerelement inaktiv ist, die linke obere Koordinate ist nicht unbedingt (0, 0) und der Gerätekontext, der übergeben wird, für den Steuerelementcontainer, die das Steuerelement enthält.

> [!NOTE]
>  Es ist wichtig, Ihre Änderungen an `OnDraw` hängen nicht von des Rechtecks oberen linken Punkts ist gleich (0, 0) und an, dass Sie nur innerhalb des Rechtecks zeichnen `OnDraw`. Es können unerwartete Ergebnisse auftreten, wenn Sie über den Bereich des Rechtecks zeichnen.

Die standardmäßige Implementierung von MFC-ActiveX-Steuerelement-Assistenten in der Implementierungsdatei des Steuerelements (. CPP), dargestellt im folgenden, zeichnet das Rechteck mit einem weißen Pinsel und füllt die Ellipse mit der aktuellen Hintergrundfarbe.

[!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]

> [!NOTE]
>  Beim Zeichnen eines Steuerelements, sollten Sie keine Annahmen über den Zustand des Gerätekontexts, die als übergeben wird, die *Pdc* Parameter, um die `OnDraw` Funktion. Gelegentlich der Gerätekontext wird von der Container-Anwendung bereitgestellt und werden nicht unbedingt auf die Standardwerte initialisiert werden. Insbesondere wählen Sie explizit aus, die Stifte, Pinsel, Farben, Schriftarten und andere Ressourcen, denen Ihr Code zum Zeichnen von abhängig ist.

##  <a name="_core_optimizing_your_paint_code"></a> Optimieren des Zeichencodes

Nachdem das Steuerelement selbst erfolgreich gezeichnet hat, der nächste Schritt ist die Optimierung der `OnDraw` Funktion.

Die standardmäßige Implementierung des ActiveX-Steuerelements zeichnen, zeichnet den gesamte Steuerelement-Bereich. Dies ist ausreichend für einfache Steuerelemente sind in vielen Fällen Neuzeichnen des Steuerelements allerdings schneller, wenn nur der Teil, der Aktualisierung benötigt neu wurde, statt das gesamte Steuerelement gezeichnet wurde.

Die `OnDraw` Funktion bietet eine einfache Methode der Optimierung durch Übergabe *RcInvalid*, den rechteckigen Bereich des Steuerelements, das Neuzeichnen benötigt. Verwenden Sie diesen Bereich, in der Regel kleiner als der gesamte Steuerelement-Bereich, um den zeichnen-Prozess zu beschleunigen.

##  <a name="_core_painting_your_control_using_metafiles"></a> Das Zeichnen des Steuerelements mit Metadateien

In den meisten Fällen die *Pdc* Parameter, um die `OnDraw` Funktion verweist, für einen Bildschirm Gerätekontext (DC). Allerdings ist der Domänencontroller empfangen, für das Rendering bei Bilder des Steuerelements oder während einer Sitzung für die Seitenansicht drucken, eine besondere Art eine "Metadatei DC" aufgerufen. Im Gegensatz zu einem Bildschirm DC, der an sie gesendete Anforderungen sofort zu verarbeitet, speichert eine Metadatei DC Anforderungen zu einem späteren Zeitpunkt wiedergegeben werden. Einige containeranwendungen können auch mit einer Metadatei DC im Designmodus Bild für das Steuerelement zu rendern.

Metadatei Anforderungen zeichnen kann gemacht werden, indem der Container über zwei Funktionen: `IViewObject::Draw` (diese Funktion kann auch für nicht-Metadatei zeichnen aufgerufen werden) und `IDataObject::GetData`. Bei einer Metadatei, DC wird als einer der Parameter übergeben, das MFC-Framework ruft [OnDrawMetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile). Da dies eine virtuelle Memberfunktion ist, überschreiben Sie diese Funktion in der Steuerelementklasse auf spezielle Verarbeitungsschritte ausführen. Das Standardverhalten ruft `COleControl::OnDraw`.

Um sicherzustellen, dass das Steuerelement sowohl Bildschirm- und Metadatei geräteinhalten gezeichnet werden kann, müssen Sie nur die Member-Funktionen verwenden, die in einem Bildschirm und einer Metadatei DC unterstützt werden. Denken Sie daran, dass das Koordinatensystem nicht in Pixel gemessen werden kann.

Da die standardmäßige Implementierung des `OnDrawMetafile` Aufrufe des Steuerelements `OnDraw` funktionieren, verwenden Sie nur Memberfunktionen, die für einen Gerätekontext für den Bildschirm, und einer Metadatei geeignet sind, es sei denn, Sie überschreiben `OnDrawMetafile`. Die folgende Liste enthält die Teilmenge der `CDC` Memberfunktionen, die in einer Metadatei und einen Bildschirm Gerätekontext verwendet werden können. Weitere Informationen zu diesen Funktionen finden Sie unter Klasse [CDC](../mfc/reference/cdc-class.md) in die *MFC-Referenz*.

|Einen Bogen konvertiert.|BibBlt|Chord|
|---------|------------|-----------|
|`Ellipse`|`Escape`|`ExcludeClipRect`|
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|
|`LineTo`|`MoveTo`|`OffsetClipRgn`|
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|
|`Pie`|`Polygon`|`Polyline`|
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|
|`SelectPalette`|`SetBkColor`|`SetBkMode`|
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|
|`StretchBlt`|`TextOut`||

Zusätzlich zu `CDC` Member-Funktionen, es gibt einige andere Funktionen, die in einer Metadatei DC kompatibel sind. Dazu gehören [: CPalette:: AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette), [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect), und drei Memberfunktionen der `CBrush`: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect), [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush), und [CreatePatternBrush](../mfc/reference/cbrush-class.md#createpatternbrush).

Funktionen, die nicht in einer Metadatei aufgezeichnet werden, sind: [DrawFocusRect](../mfc/reference/cdc-class.md#drawfocusrect), [DrawIcon](../mfc/reference/cdc-class.md#drawicon), [DrawText](../mfc/reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn), [FillRect](../mfc/reference/cdc-class.md#fillrect), [FrameRect](../mfc/reference/cdc-class.md#framerect), [GrayString](../mfc/reference/cdc-class.md#graystring), [InvertRect](../mfc/reference/cdc-class.md#invertrect), [ScrollDC](../mfc/reference/cdc-class.md#scrolldc), and [TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout). Da eine Metadatei DC nicht tatsächlich von einem Gerät zugeordnet ist, können nicht Sie SetDIBits GetDIBits und CreateDIBitmap mit einer Metadatei DC verwenden. Sie können mit einer Metadatei DC SetDIBitsToDevice und StretchDIBits als Ziel verwenden. [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](../mfc/reference/cbitmap-class.md#createcompatiblebitmap), und [CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap) sind nicht mit einer Metadatei DC sinnvoll.

Ein weiterer wichtiger Aspekt bei Verwendung einer Metadatei Domänencontroller ist, dass das Koordinatensystem nicht in Pixel gemessen werden kann. Aus diesem Grund alle in Ihrem Code zum Zeichnen angepasst werden, muss damit er in das Rechteck passt an übergeben `OnDraw` in die *RcBounds* Parameter. Dies verhindert versehentliche Zeichnen außerhalb der Kontrolle, da *RcBounds* die Größe der das Fenster des Steuerelements darstellt.

Nachdem Sie die Metadateirendering für das Steuerelement implementiert haben, verwenden Sie zum Testen der Metadatei Testcontainer. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) .

#### <a name="to-test-the-controls-metafile-using-test-container"></a>So testen Sie die Metadatei des Steuerelements mit Test Container

1. Klicken Sie auf den Testcontainer **bearbeiten** Menü klicken Sie auf **neues Steuerelement einfügen**.

1. In der **neues Steuerelement einfügen** Feld, wählen Sie das Steuerelement aus, und klicken Sie auf **OK**.

   Das Steuerelement wird im Test-Container angezeigt.

1. Auf der **Steuerelement** Menü klicken Sie auf **Metadatei**.

   Ein separates Fenster wird angezeigt, in dem die Metadatei angezeigt wird. Sie können ändern, dass die Größe des Fensters, um zu sehen, wie der Skalierung des Steuerelements Metadatei auswirkt. Sie können dieses Fenster jederzeit schließen.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)
