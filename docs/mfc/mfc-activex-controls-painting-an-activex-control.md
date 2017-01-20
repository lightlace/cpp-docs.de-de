---
title: "MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelemente, Optimieren"
  - "MFC-ActiveX-Steuerelemente, Zeichnen"
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt das ActiveX\-Steuerelement\-Zeichnen und wie Sie Farbcode ändern können, um den Prozess zu optimieren. \(Siehe [Optimieren der Steuerzeichnung](../mfc/optimizing-control-drawing.md) für Verfahren auf, wie Zeichnen indem Sie können Steuerelementen einzeln zuvor ausgewählte GDI\-Objekte nicht wiederherstellen optimiert.  Nachdem alle Steuerelemente gezeichnet wurden, kann der Container die ursprünglichen Objekte automatisch wiederhergestellt.\)  
  
 Beispiele in diesem Artikel sind von einem Steuerelement, das aus dem MFC\-ActiveX\-Steuerelement\-Assistenten mit Standardeinstellungen erstellt wird.  Weitere Informationen zum Erstellen einer Skelettsteuer\-Anwendung mit dem MFC\-ActiveX\-Steuerelement\-Assistenten, finden Sie im Artikel [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md).  
  
 Die folgenden Themen werden behandelt:  
  
-   [Der Prozess für das Zeichnen eines Steuerelements und Code erstellt, um vom ActiveX\-Steuerelement\-Assistenten Zeichnen zu unterstützen](#_core_the_painting_process_of_an_activex_control)  
  
-   [Wie Sie das Zeichnen optimiert](#_core_optimizing_your_paint_code)  
  
-   [Wie Sie das Steuerelement mithilfe von Metadateien zeichnet](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> Das Zeichnen eines ActiveX\-Steuerelements  
 Wenn ActiveX\-Steuerelemente zuerst angezeigt oder neu gezeichnet werden, um sie einem Zeichnen, das anderen Anwendungen vergleichbar ist, die mit MFC, mit einem wichtigen Unterschied entwickelt wurden: ActiveX\-Steuerelemente können in einem aktiven oder inaktiv sein.  
  
 Ein aktives Steuerelement wird in einen ActiveX\-Steuerelementcontainer durch ein untergeordnetes Fenster dargestellt.  Wie andere Fenster ist es für das Zeichnen zuständig, wenn `WM_PAINT` eine Meldung empfängt.  Die Basisklasse des Steuerelements, [COleControl](../mfc/reference/colecontrol-class.md), behandelt sie in ihrer `OnPaint`\-Funktion.  Die Standardimplementierung ruft die `OnDraw`\-Funktion des Steuerelements.  
  
 Ein Präprozessordirektiven Steuerelement ist anders gezeichnet.  Wenn das Steuerelement inaktiv ist, ist das Fenster entweder nicht sichtbar oder nicht vorhanden, sodass es eine paint\-Meldung nicht erhalten.  Stattdessen ruft der Steuerelementcontainer Funktion direkt die `OnDraw` des Steuerelements.  Dies weicht Zeichnen eines vom aktiven Steuerelements darin, dass die `OnPaint`\-Memberfunktion nicht aufgerufen wird.  
  
 Wie in den vorherigen Abschnitten erläutert, wie ein ActiveX\-Steuerelement aktualisiert wird, hängt vom Status des Steuerelements ab.  Da das Framework die `OnDraw`\-Memberfunktion in beiden Fällen aufrufen, fügen Sie den Großteil des außerdem in dieser Memberfunktion hinzu.  
  
 Die `OnDraw`\-Memberfunktionshandles steuern Zeichnen.  Wenn ein Steuerelement inaktiv ist, ruft der Steuerelementcontainer `OnDraw` auf und den Gerätekontext des Steuerelementcontainers und die Koordinaten des rechteckigen Bereichs, der vom Steuerelement gefüllt wird.  
  
 Das Rechteck, das durch das Framework die `OnDraw`\-Memberfunktion übergeben wird, enthält den Bereich, der vom Steuerelement gefüllt wird.  Wenn das Steuerelement aktiv ist, ist die obere linke Ecke \(0, 0\) und der übergebene Gerätekontext ist für das untergeordnete Fenster, das das Steuerelement enthält.  Wenn das Steuerelement inaktiv ist, ist die Koordinate nicht unbedingt \(0, 0\) und der Gerätekontext, der übergeben wird, ist für den Steuerelementcontainer, der das Steuerelement enthält.  
  
> [!NOTE]
>  Es ist wichtig, dass die Änderungen in `OnDraw`  nicht vom oberen linkspunkt des Rechtecks abhängen, der gleich ist \(0, 0\) und dass Sie nur innerhalb des Rechtecks zeichnen, das an `OnDraw` übergeben wird.  Unerwartete Ergebnisse können auftreten, wenn Sie über den Bereich des Rechtecks hinaus zeichnen.  
  
 Die Standardimplementierung, die aus dem MFC\-ActiveX\-Steuerelement\-Assistenten in der Steuerimplementierungsdatei \(.CPP\) bereitgestellt, wird unten angezeigt, erfasst das Rechteck mit einem weißen Pinsel und die Ellipse mit der aktuellen Hintergrundfarbe.  
  
 [!CODE [NVC_MFC_AxUI#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#1)]  
  
> [!NOTE]
>  Wenn Sie ein Steuerelement gezeichnet, sollten Sie Annahmen über den Zustand des Gerätekontexts nicht umwandeln, der als der *pdc*\-Parameter der `OnDraw`\-Funktion übergeben wird.  Gelegentlich wird der Gerätekontext über die Containeranwendung angegeben und nicht unbedingt dem Standardzustand initialisiert werden.  Insbesondere, wählen Sie explizit die Pinsel, Stifte, die die Farben, Schriftarten und anderen Ressourcen, aus denen der Zeichencode nach abhängt.  
  
##  <a name="_core_optimizing_your_paint_code"></a> Optimieren des Farben\-Codes  
 Nachdem das Steuerelement sich erfolgreich zeichnet, ist der nächste Schritt darin, die Funktion `OnDraw` zu optimieren.  
  
 Die Standardimplementierung des ActiveX\-Steuerelements Farben der gesamte Steuerelementbereich gezeichnet.  Dies ist für einfache Steuerelemente ausreichend, jedoch, in vielen Fällen das Steuerelement würde neu zeichnet wenn nur der Teil, den das erforderliche Aktualisieren neu gestrichelt wurde, statt des gesamten Steuerelements schneller sein.  
  
 Die `OnDraw`\-Funktion stellt eine einfache Methode der Optimierung verhindern von `rcInvalid`, der rechteckige Bereich des Steuerelements bereit, das das Neuzeichnen erfordert.  Verwenden Sie in diesem Bereich, normalerweise kleiner als der gesamte Steuerelementbereich, das Zeichnen beschleunigen.  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> Zeichnen des Steuerelements mithilfe von Metadateien  
 In den meisten Fällen wird der `pdc` an die Funktion Parameter `OnDraw` auf einem Bildschirm\-Gerätekontext \(DC\).  Wenn es Bilder des Steuerelements oder während einer Seitenansichtssitzung gibt, ist das Domänencontroller, das für das Rendern empfangen wird, ein spezieller Typ, der einen "Metadatei\-DC".  Anders als ein Bildschirm Domänencontroller das sofort behandelt, dass Anforderungen zu ihm, Metadatei\-DC\-Speicher anfordert, die wiedergegeben werden zu einem späteren Zeitpunkt.  Einige Containeranwendungen wählen kann auch, um das Steuerbild mithilfe eines Metadatei\-DC zu rendern wenn im Entwurfsmodus.  
  
 Metadateizeichnungsanforderungen können von dem Container über zwei Benutzeroberflächenfeatures gemacht werden: **IViewObject::Draw** \(Diese Funktion kann für NichtMetadateizeichnung ebenfalls aufgerufen werden\) und **IDataObject::GetData**.  Wenn ein Metadatei\-DC als einen der Parameter übergeben wird, macht das MFC\-Framework [COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md) einen Aufruf.  Da dies eine virtuelle Memberfunktion ist, überschreiben Sie diese Funktion in der Steuerelementklasse, um das zur speziellen Verarbeitung durchzuführen.  Das Standardverhalten ruft `COleControl::OnDraw` auf.  
  
 So verschieben des Steuerelements sicherzustellen kann im Bildschirm gezeichnet werden und Metadateigerätekontexte, müssen Sie Nur Memberfunktionen verwenden die in einen Bildschirm und in einen Metadatei\-DC unterstützt werden.  Beachten Sie, dass das Koordinatensystem möglicherweise nicht in Pixel gemessen wird.  
  
 Da die Standardimplementierung von `OnDrawMetafile` die `OnDraw`\-Funktion des Steuerelements aufruft, verwenden Sie nur Memberfunktionen, die für eine Metadatei und einen Bildschirm\-Gerätekontext geeignet sind, es sei denn, Sie `OnDrawMetafile` überschreiben.  Im Folgenden sind die Teilmenge von `CDC`\-Memberfunktionen auf, die in einer Metadatei und in einem Bildschirm\-Gerätekontext verwendet werden können.  Weitere Informationen zu diesen Funktionen, Klasse finden Sie unter [CDC](../mfc/reference/cdc-class.md) in der *MFC\-Referenz*.  
  
|Bögen|BibBlt|Sehne|  
|-----------|------------|-----------|  
|**Ellipse**|**Escape**|`ExcludeClipRect`|  
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|  
|`LineTo`|`MoveTo`|`OffsetClipRgn`|  
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|  
|`Pie`|**Polygon**|`Polyline`|  
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|  
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|  
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|  
|`SelectPalette`|`SetBkColor`|`SetBkMode`|  
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|  
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|  
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|  
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|  
|`StretchBlt`|`TextOut`||  
  
 Neben `CDC`\-Memberfunktionen gibt es einige andere Funktionen, die in einem Metadatei\-DC kompatibel sind.  Dazu gehören [CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md), [CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md) und dreiköpfige Funktionen von `CBrush` ein: [CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md), [CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md) und [CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md).  
  
 Funktionen, die nicht in einer Metadatei aufgezeichnet werden, sind: [DrawFocusRect](../Topic/CDC::DrawFocusRect.md), [DrawIcon](../Topic/CDC::DrawIcon.md), [DrawText](../Topic/CDC::DrawText.md), [ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md), [FillRect](../Topic/CDC::FillRect.md), [FrameRect](../Topic/CDC::FrameRect.md), [GrayString](../Topic/CDC::GrayString.md), [InvertRect](../Topic/CDC::InvertRect.md), [ScrollDC](../Topic/CDC::ScrollDC.md) und [TabbedTextOut](../Topic/CDC::TabbedTextOut.md).  Da ein Metadatei\-DC nicht tatsächlich mit einem Gerät zugeordnet ist, können Sie SetDIBits, GetDIBits und CreateDIBitmap mit einem Metadatei\-DC nicht verwenden.  Sie können SetDIBitsToDevice und StretchDIBits mit einem Metadatei\-DC als Ziel verwenden.  [CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md), [CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md) und [CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md) sind nicht mit einem Metadatei\-DC sinnvoll.  
  
 Ein weiterer Punkt, zu beachten, wann, einen Metadatei\-DC zu verwenden, dass das Koordinatensystem möglicherweise nicht in Pixel gemessen wird.  Aus diesem Grund sollte das gesamte Zeichnungscode auf Schaltfläche in das Rechteck angepasst werden, die `OnDraw`  im `rcBounds`\-Parameter übergeben wird.  Dadurch wird ein versehentliches Zeichnen außerhalb des Steuerelements, da `rcBounds` die Größe des Fensters des Steuerelements darstellt.  
  
 Nachdem Sie Metadateirendering für das Steuerelement implementiert haben, dem Testcontainer, um der Metadatei zu testen.  Informationen zum Zugreifen auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md).  
  
#### So wie die Metadatei des Steuerelements mithilfe des Testcontainers testen  
  
1.  Klicken Sie im Menü  **Bearbeiten** des Testcontainers auf **Neues Steuerelement einfügen**.  
  
2.  Im Feld **Neues Steuerelement einfügen**  wählen Sie das Steuerelement aus und klicken auf **OK**.  
  
     Das Steuerelement wird im Testcontainer.  
  
3.  Klicken Sie im Menü **Steuerelement**  auf **Metadatei zeichnen**.  
  
     Ein separates Fenster wird angezeigt, in welchem die Metadatei angezeigt wird.  Sie können die Größe des Fensters ändern, um die Größenanpassung zu sehen, wie die Metadatei des Steuerelements auswirkt.  Sie können dieses Fenster zu schließen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)