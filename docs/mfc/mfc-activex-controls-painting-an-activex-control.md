---
title: 'MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], painting
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de12a21c4b411f3cd1fe25d7d6badd8d26318351
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929811"
---
# <a name="mfc-activex-controls-painting-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements
Dieser Artikel beschreibt die ActiveX-Steuerelement-Zeichenprozess und wie Sie ändern können, Paint-Code, um den Prozess zu optimieren. (Finden Sie unter [optimieren Steuerelement zeichnen](../mfc/optimizing-control-drawing.md) für Techniken zum Zeichnen zu optimieren, indem Sie einzeln Steuerelemente ohne zuvor ausgewählten GDI-Objekte wiederhergestellt werden. Nachdem alle Steuerelemente gezeichnet wurden, kann die Container automatisch die ursprünglichen Objekte wiederherstellen.)  
  
 Beispiele in diesem Artikel werden von einem Steuerelement vom MFC-ActiveX-Steuerelement-Assistenten mit Standardeinstellungen erstellt. Weitere Informationen zum Erstellen einer MFC-ActiveX-Steuerelement-Assistenten verwenden das Gerüst eines Steuerelements-Anwendung finden Sie im Artikel [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md).  
  
 In den folgenden Themen werden behandelt:  
  
-   [Der Gesamtprozess für das Zeichnen eines Steuerelements und der Code erstellt, indem ActiveX-Steuerelement-Assistent zur Unterstützung von Paint-Ereignisse](#_core_the_painting_process_of_an_activex_control)  
  
-   [Zum Optimieren der Zeichenprozess](#_core_optimizing_your_paint_code)  
  
-   [Gewusst wie: Zeichnen Sie das Steuerelement über Metadateien](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> Der Zeichenprozess eines ActiveX-Steuerelements  
 Wenn ActiveX-Steuerelemente zunächst angezeigt werden oder neu gezeichnet werden, sie entsprechen einem Zeichenprozess ähnlich für andere Anwendungen entwickelt wurde, mithilfe von MFC, mit einem wichtigen Unterschied: ActiveX-Steuerelemente in einer aktiven oder inaktiven Status werden können.  
  
 Ein aktives Steuerelement wird in einem ActiveX-Steuerelementcontainer durch ein untergeordnetes Fenster dargestellt. Wie andere Windows ist es selbst zeichnen, wenn eine WM_PAINT-Meldung empfangen wird. Basisklasse für das Steuerelement, [COleControl](../mfc/reference/colecontrol-class.md), verarbeitet diese Nachricht in seiner `OnPaint` Funktion. Diese Standardimplementierung Ruft die `OnDraw` -Funktion des Steuerelements.  
  
 Ein Inaktives Steuerelement wird unterschiedlich gezeichnet. Wenn das Steuerelement aktiv ist, wird das Fenster entweder ausgeblendet oder nicht vorhanden ist, damit keine Paint-Meldung empfangen können. Stattdessen ruft die Steuerelementcontainer direkt die `OnDraw` -Funktion des Steuerelements. Dies unterscheidet sich von Zeichenprozess in, das ein aktives Steuerelement die `OnPaint` Memberfunktion wird nie aufgerufen.  
  
 Wie in den vorherigen Abschnitten erläutert, hängt wie ein ActiveX-Steuerelement aktualisiert wird, vom Zustand des Steuerelements. Jedoch, da das Framework Ruft die `OnDraw` Memberfunktion in beiden Fällen fügen Sie den Großteil des Codes Paint-Ereignisse in dieser Memberfunktion.  
  
 Die `OnDraw` Memberfunktion Zeichnen von Steuerelementen zuständig. Wenn ein Steuerelement inaktiv ist, der Steuerelementcontainer ruft `OnDraw`, übergeben Sie den Gerätekontext, der dem Steuerelementcontainer und die Koordinaten des rechteckigen Bereichs, der vom Steuerelement belegt.  
  
 Übergeben Sie das Rechteck durch das Framework die `OnDraw` Memberfunktion enthält den Bereich des Steuerelements. Wenn das Steuerelement aktiv ist, wird die oberen linken Ecke (0, 0) und der Gerätekontext, der übergeben wird, für das untergeordnete Fenster, die das Steuerelement enthält. Wenn das Steuerelement aktiv ist, die linke obere Koordinate ist nicht notwendigerweise (0, 0) und der Gerätekontext, der übergeben wird, für den Steuerelementcontainer, die das Steuerelement enthält.  
  
> [!NOTE]
>  Es ist wichtig, Ihre Änderungen an `OnDraw` hängen nicht davon oberen linken zeigen das Rechteck wird gleich (0, 0) und an, dass Sie nur innerhalb des Rechtecks zeichnen `OnDraw`. Es können unerwartete Ergebnisse auftreten, wenn Sie über den Bereich des Rechtecks zeichnen.  
  
 Die standardmäßige Implementierung von MFC-ActiveX-Steuerelement-Assistenten in der Implementierungsdatei des Steuerelements bereitgestellt (. CPP) gezeigt unten Zeichnet das Rechteck mit einem weißen Pinsel und füllt Sie mit der aktuellen Hintergrundfarbe Ellipse.  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/cpp/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  Beim Zeichnen eines Steuerelements, sollten Sie keine Annahmen über den Zustand des Gerätekontexts, die als übergeben vornehmen der *Pdc* Parameter an die `OnDraw` Funktion. Gelegentlich der Gerätekontext wird von der containeranwendung bereitgestellt und werden nicht unbedingt auf den Standardstatus initialisiert werden. Insbesondere wählen Sie explizit aus, die Stifte, Pinsel, Farben, Schriftarten und andere Ressourcen, denen Ihre Zeichencode abhängt.  
  
##  <a name="_core_optimizing_your_paint_code"></a> Optimieren des Zeichencodes  
 Nachdem das Steuerelement selbst erfolgreich gezeichnet wird, ist der nächste Schritt zur Optimierung der `OnDraw` Funktion.  
  
 Die standardmäßige Implementierung des ActiveX-Steuerelement zeichnen Zeichnet das gesamte Steuerelement-Bereich. Dies ist ausreichend für einfache Steuerelemente, aber in vielen Fällen Neuzeichnen des Steuerelements wäre schneller, wenn nur der Teil, der Aktualisierung benötigt, anstatt das gesamte Steuerelement gezeichnet wurde.  
  
 Die `OnDraw` -Funktion bietet eine einfache Methode, mit der Optimierung durch Übergabe *RcInvalid*, den rechteckigen Bereich des Steuerelements, das durch das Neuzeichnen erhalten benötigt. Verwenden Sie diesen Bereich, in der Regel kleiner als der gesamte Steuerelementbereich, den Zeichenprozess zu beschleunigen.  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> Zeichnen des Steuerelements mit Metadateien  
 In den meisten Fällen die *Pdc* Parameter an die `OnDraw` Funktion verweist, zu einem Bildschirm Gerätekontext (DC). Allerdings ist der Domänencontroller für das Rendering empfangen beim Drucken von Bildern des Steuerelements oder während einer Sitzung für die Seitenansicht eine Sonderform "Metadatei DC" aufgerufen. Im Gegensatz zu einem Bildschirm Domänencontroller, der an sie gesendete Anforderungen sofort verarbeitet, speichert eine Metadatei DC Anforderungen zu einem späteren Zeitpunkt wiedergegeben werden. Einige containeranwendungen können auch mit einem Metadatei-DC im Entwurfsmodus das Steuerelementbild rendert.  
  
 Metadatei zeichnen Anforderungen kann vom Container über zwei Funktionen der Benutzeroberfläche vorgenommen werden: `IViewObject::Draw` (diese Funktion kann auch für nicht-Metadatei zeichnen aufgerufen werden) und `IDataObject::GetData`. Wenn eine Metadatei DC als einer der Parameter übergeben wird, macht das MFC-Framework einen Aufruf von [OnDrawMetafile](../mfc/reference/colecontrol-class.md#ondrawmetafile). Da dies eine virtuelle Memberfunktion ist, überschreiben Sie diese Funktion in der Control-Klasse, um spezielle Verarbeitungsschritte ausführen. Das Standardverhalten ruft `COleControl::OnDraw`.  
  
 Stellen Sie sicher, dass das Steuerelement im Bildschirm und Metadateifarben Gerätekontexte gezeichnet werden kann, müssen Sie nur Member-Funktionen verwenden, die in einem Bildschirm und einem Metadatei-DC unterstützt werden. Denken Sie daran, dass das Koordinatensystem nicht in Pixel gemessen werden kann.  
  
 Da die standardmäßige Implementierung des `OnDrawMetafile` Ruft das Steuerelement `OnDraw` funktionieren, verwenden Sie nur für eine Metadatei und einen Gerätekontext Bildschirm geeignet sind, es sei denn, Sie überschreiben Memberfunktionen `OnDrawMetafile`. Die folgende Liste enthält die Teilmenge der `CDC` Memberfunktionen, die in einer Metadatei und einem Bildschirm Gerätekontext verwendet werden können. Weitere Informationen zu diesen Funktionen finden Sie in der Klasse [CDC](../mfc/reference/cdc-class.md) in der *MFC-Referenz*.  
  
|Bogen|BibBlt|Die Sehne|  
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
  
 Zusätzlich zu `CDC` Memberfunktionen, es gibt einige andere Funktionen, die in einem Metadatei-DC kompatibel sind. Dazu gehören [: CPalette:: AnimatePalette](../mfc/reference/cpalette-class.md#animatepalette), [CFont::CreateFontIndirect](../mfc/reference/cfont-class.md#createfontindirect), und drei Memberfunktionen der `CBrush`: [CreateBrushIndirect](../mfc/reference/cbrush-class.md#createbrushindirect), [CreateDIBPatternBrush](../mfc/reference/cbrush-class.md#createdibpatternbrush), und [CreatePatternBrush](../mfc/reference/cbrush-class.md#createpatternbrush).  
  
 Funktionen, die nicht in einer Metadatei aufgezeichnet werden, sind: [DrawFocusRect](../mfc/reference/cdc-class.md#drawfocusrect), [DrawIcon](../mfc/reference/cdc-class.md#drawicon), [DrawText](../mfc/reference/cdc-class.md#drawtext), [ExcludeUpdateRgn](../mfc/reference/cdc-class.md#excludeupdatergn), [FillRect](../mfc/reference/cdc-class.md#fillrect), [FrameRect](../mfc/reference/cdc-class.md#framerect), [GrayString](../mfc/reference/cdc-class.md#graystring), [InvertRect](../mfc/reference/cdc-class.md#invertrect), [ScrollDC](../mfc/reference/cdc-class.md#scrolldc), und [TabbedTextOut](../mfc/reference/cdc-class.md#tabbedtextout). Da eine Metadatei DC nicht tatsächlich von einem Gerät zugeordnet ist, können nicht Sie SetDIBits, GetDIBits und CreateDIBitmap mit einem Metadatei-DC verwenden. Sie können mit einem Metadatei-DC SetDIBitsToDevice und StretchDIBits als Ziel verwenden. [CreateCompatibleDC](../mfc/reference/cdc-class.md#createcompatibledc), [CreateCompatibleBitmap](../mfc/reference/cbitmap-class.md#createcompatiblebitmap), und [CreateDiscardableBitmap](../mfc/reference/cbitmap-class.md#creatediscardablebitmap) sind nicht mit einem Metadatei-DC aussagekräftig.  
  
 Ein weiterer wichtiger Aspekt bei Verwendung einer Metadatei DC ist, dass das Koordinatensystem nicht in Pixel gemessen werden kann. Aus diesem Grund alle zeichnen Code angepasst werden, sollte indem Sie in das Rechteck passt an übergeben `OnDraw` in der *RcBounds* Parameter. Dies verhindert versehentliche Paint-Ereignisse außerhalb der Kontrolle, da *RcBounds* die Größe des Fensters für das Steuerelement darstellt.  
  
 Nachdem Sie die Metadateirendering für das Steuerelement implementiert haben, verwenden Sie den Testcontainer So testen Sie die Metadatei. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) .  
  
#### <a name="to-test-the-controls-metafile-using-test-container"></a>So testen Sie das Steuerelement-Metadatei, die mit dem Testcontainer  
  
1.  Klicken Sie auf den Testcontainer **bearbeiten** Menü klicken Sie auf **neues Steuerelement einfügen**.  
  
2.  In der **neues Steuerelement einfügen** Feld, wählen Sie das Steuerelement, und klicken Sie auf **OK**.  
  
     Das Steuerelement wird im Testcontainer angezeigt.  
  
3.  Auf der **Steuerelement** Menü klicken Sie auf **Metadatei**.  
  
     Ein separates Fenster angezeigt wird, in dem die Metadatei angezeigt wird. Sie können die Größe der in diesem Fenster zu sehen, wie das Steuerelement Metadatei auswirkt Skalierung ändern. Sie können dieses Fenster jederzeit schließen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

