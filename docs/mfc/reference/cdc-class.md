---
title: "CDC-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDC-Klasse"
  - "coordinates in Windows 95/98 [C++]"
  - "device contexts [C++], CDC-Klasse"
  - "screen coordinates in device contexts"
  - "Windows [C++], device contexts"
  - "Windows 95 [C++], Bildschirmkoordinaten"
  - "Windows 98 [C++], Bildschirmkoordinaten"
ms.assetid: 715b3334-cb2b-4c9c-8067-02eb7c66c8b2
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CDC-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definiert eine Klasse Gerätekontextobjekte.  
  
## Syntax  
  
```  
class CDC : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDC::CDC](../Topic/CDC::CDC.md)|Erstellt ein `CDC`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDC::AbortDoc](../Topic/CDC::AbortDoc.md)|Beendet den aktuellen Druckauftrag und löscht alle, welches, die Anwendung auf dem Gerät seit dem letzten Aufruf der Memberfunktion `StartDoc` geschrieben hat.|  
|[CDC::AbortPath](../Topic/CDC::AbortPath.md)|Schließt und verwirft alle Pfade im Gerätekontext.|  
|[CDC::AddMetaFileComment](../Topic/CDC::AddMetaFileComment.md)|Kopiert den Kommentar aus einem Puffer in eine angegebene ErhöhenFormat Metadatei.|  
|[CDC::AlphaBlend](../Topic/CDC::AlphaBlend.md)|Zeigt Bitmaps an, die die transparenten oder halbtransparenten Pixel haben.|  
|[CDC::AngleArc](../Topic/CDC::AngleArc.md)|Zeichnet ein Liniensegment und ein Bogen und verschiebt die aktuelle Position auf den Endpunkt des Bogens.|  
|[CDC::Arc](../Topic/CDC::Arc.md)|Zeichnet einen elliptischen Bogen.|  
|[CDC::ArcTo](../Topic/CDC::ArcTo.md)|Zeichnet einen elliptischen Bogen.  Diese Funktion ist für `Arc` vergleichbar, außer dass die aktuelle Position wird aktualisiert.|  
|[CDC::Attach](../Topic/CDC::Attach.md)|Fügt einen Windows\-Gerätekontext zu diesem `CDC`\-Objekt.|  
|[CDC::BeginPath](../Topic/CDC::BeginPath.md)|Öffnet eine Pfadklammer im Gerätekontext.|  
|[CDC::BitBlt](../Topic/CDC::BitBlt.md)|Kopiert eine Bitmap aus einem angegebenen Gerätekontext.|  
|[CDC::Chord](../Topic/CDC::Chord.md)|Zeichnet eine Sehne \(einen geschlossenen Körper gesprungen durch die Schnittmenge einer Ellipse und des Liniensegments\).|  
|[CDC::CloseFigure](../Topic/CDC::CloseFigure.md)|Schließt eine offene Körper in einem Pfad.|  
|[CDC::CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md)|Erstellt einen Speichergerätekontext, der mit einem anderen Gerätekontext kompatibel ist.  Sie können ihn verwenden, um Bilder in den Arbeitsspeicher vorzubereiten.|  
|[CDC::CreateDC](../Topic/CDC::CreateDC.md)|Erstellt einen Gerätekontext für ein bestimmtes Gerät.|  
|[CDC::CreateIC](../Topic/CDC::CreateIC.md)|Erstellt einen Informationskontext für ein bestimmtes Gerät.  Dies stellt eine schnelle Möglichkeit, Informationen über das Gerät abrufen, ohne einen Gerätekontext zu erstellen.|  
|[CDC::DeleteDC](../Topic/CDC::DeleteDC.md)|Löscht den Windows\-Gerätekontext, der diesem Objekt zugeordnet ist. `CDC`|  
|[CDC::DeleteTempMap](../Topic/CDC::DeleteTempMap.md)|Aufgerufen durch den `CWinApp` Leerlaufhandler, entweder `CDC` temporäres Objekt gelöscht erstellt durch `FromHandle`.  Trennt auch den Gerätekontext.|  
|[CDC::Detach](../Topic/CDC::Detach.md)|Trennt den Windows\-Gerätekontext von diesem `CDC`\-Objekt.|  
|[CDC::DPtoHIMETRIC](../Topic/CDC::DPtoHIMETRIC.md)|Konvertiert Geräteeinheiten in **HIMETRIC** Einheiten.|  
|[CDC::DPtoLP](../Topic/CDC::DPtoLP.md)|Konvertiert Geräteeinheiten in logische Einheiten.|  
|[CDC::Draw3dRect](../Topic/CDC::Draw3dRect.md)|Zeichnet ein dreidimensionales Rechteck.|  
|[CDC::DrawDragRect](../Topic/CDC::DrawDragRect.md)|Löschen und zeichnet ein Rechteck neu, während es gezogen wird.|  
|[CDC::DrawEdge](../Topic/CDC::DrawEdge.md)|Zeichnet die Ränder eines Rechtecks.|  
|[CDC::DrawEscape](../Topic/CDC::DrawEscape.md)|Greift auf Zeichnungsfunktionen einer Videodarstellung zu, die nicht direkt vom GDI \(Graphics Device Interface\) verfügbar sind.|  
|[CDC::DrawFocusRect](../Topic/CDC::DrawFocusRect.md)|Zeichnet ein Rechteck im Format, das verwendet wird, um den Fokus anzugeben.|  
|[CDC::DrawFrameControl](../Topic/CDC::DrawFrameControl.md)|Zeichnen eines Frame\-Steuerelement.|  
|[CDC::DrawIcon](../Topic/CDC::DrawIcon.md)|Zeichnet ein Symbol.|  
|[CDC::DrawState](../Topic/CDC::DrawState.md)|Zeigt ein Bild an und wird ein visueller Auswirkungen, um einen Zustand anzugeben.|  
|[CDC::DrawText](../Topic/CDC::DrawText.md)|Zeichnet formatierten Text im angegebenen Rechteck.|  
|[CDC::DrawTextEx](../Topic/CDC::DrawTextEx.md)|Zeichnet formatierten Text im angegebenen Rechteck über die zusätzlichen Stile.|  
|[CDC::Ellipse](../Topic/CDC::Ellipse.md)|Zeichnet eine Ellipse.|  
|[CDC::EndDoc](../Topic/CDC::EndDoc.md)|Beendet einen Druckauftrag, der von der `StartDoc`\-Memberfunktion gestartet wird.|  
|[CDC::EndPage](../Topic/CDC::EndPage.md)|Informiert den Gerätetreiber, dass eine Seite beendet.|  
|[CDC::EndPath](../Topic/CDC::EndPath.md)|Enthält eine Pfadklammer und wählt den Pfad aus, der durch die Klammer in den Gerätekontext definiert ist.|  
|[CDC::EnumObjects](../Topic/CDC::EnumObjects.md)|Listet die Stifte und Pinsel auf die, die in einem Gerätekontext verfügbar sind.|  
|[CDC::Escape](../Topic/CDC::Escape.md)|Ermöglicht den Zugangsmöglichkeiten Anwendungen, die nicht direkt von einem bestimmten Gerät von GDI verfügbar sind.  Ermöglicht auch Zugriff auf den Windows\-Escapefunktionen.  Die Escapeaufrufe, die von einer Anwendung aufgerufen werden, werden dem Gerätetreiber übersetzt und gesendet.|  
|[CDC::ExcludeClipRect](../Topic/CDC::ExcludeClipRect.md)|Erstellt einen neuen Clippingbereich, der aus dem vorhandenen Clippingbereich abzüglich des angegebenen Rechtecks besteht.|  
|[CDC::ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md)|Verhindert Zeichnen innerhalb der ungültigen Bereiche eines Fensters durch Ausschließen eines aktualisierten Bereichs im Fenster von einem Clippingbereich.|  
|[CDC::ExtFloodFill](../Topic/CDC::ExtFloodFill.md)|Füllt einen Bereich mit dem aktuellen Pinsel aus.  Stellt mehr Flexibilität als die [CDC::FloodFill](../Topic/CDC::FloodFill.md)\-Memberfunktion bereit.|  
|[CDC::ExtTextOut](../Topic/CDC::ExtTextOut.md)|Schreibt eine Zeichenfolge in einem rechteckigen Bereichs mit der aktuell ausgewählten Schriftarten.|  
|[CDC::FillPath](../Topic/CDC::FillPath.md)|Schließt alle geöffneten Abbildungen im aktuellen Pfad und füllt den Innenbereich des Pfades mithilfe des aktuellen Pinsel\- und Polygonfüllungsmodus aus.|  
|[CDC::FillRect](../Topic/CDC::FillRect.md)|Füllt ein bestimmtes Rechteck mithilfe eines bestimmten Pinsels aus.|  
|[CDC::FillRgn](../Topic/CDC::FillRgn.md)|Füllt einen bestimmten Bereich mit dem angegebenen Pinsel aus.|  
|[CDC::FillSolidRect](../Topic/CDC::FillSolidRect.md)|Füllt ein Rechteck mit einer Volltonfarbe aus.|  
|[CDC::FlattenPath](../Topic/CDC::FlattenPath.md)|Transformiert alle Kurven im Pfad, der in den aktuellen Gerätekontext aktiviert ist und stellt jede Kurve zu eine Sequenz von Linien.|  
|[CDC::FloodFill](../Topic/CDC::FloodFill.md)|Füllt einen Bereich mit dem aktuellen Pinsel aus.|  
|[CDC::FrameRect](../Topic/CDC::FrameRect.md)|Zeichnet einen Rahmen um ein Rechteck.|  
|[CDC::FrameRgn](../Topic/CDC::FrameRgn.md)|Zeichnet einen Rahmen um einen bestimmten Bereich mithilfe eines Pinsels.|  
|[CDC::FromHandle](../Topic/CDC::FromHandle.md)|Gibt einen Zeiger auf ein Objekt zurück `CDC`, wenn Sie ein Handle zu einem Gerätekontext angegeben werden.  Wenn ein `CDC`\-Objekt nicht in Anspruch angefügt wird, wird ein temporäres Objekt erstellt und `CDC` angefügt.|  
|[CDC::GetArcDirection](../Topic/CDC::GetArcDirection.md)|Gibt die aktuelle Bogenrichtung für den Gerätekontext zurück.|  
|[CDC::GetAspectRatioFilter](../Topic/CDC::GetAspectRatioFilter.md)|Ruft die Einstellung für den aktuellen Seitenverhältnisfilter ab.|  
|[CDC::GetBkColor](../Topic/CDC::GetBkColor.md)|Ruft die aktuelle Hintergrundfarbe ab.|  
|[CDC::GetBkMode](../Topic/CDC::GetBkMode.md)|Ruft den Hintergrundmodus ab.|  
|[CDC::GetBoundsRect](../Topic/CDC::GetBoundsRect.md)|Gibt das aktuelle akkumulierte umschließende Rechteck für den angegebenen Gerätekontext zurück.|  
|[CDC::GetBrushOrg](../Topic/CDC::GetBrushOrg.md)|Ruft den Ursprung des aktuellen Pinsels ab.|  
|[CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)|Ruft die Breite, in logischen Einheiten, nachgestellten Zeichen in einem angegebenen Bereich von der aktuellen Schriftart ab.|  
|[CDC::GetCharABCWidthsI](../Topic/CDC::GetCharABCWidthsI.md)|Ruft die Breite, in logischen Einheiten, nachfolgenden Symbolindizes in einem angegebenen Bereich von der aktuellen TrueTyp\-Schriftart ab.|  
|[CDC::GetCharacterPlacement](../Topic/CDC::GetCharacterPlacement.md)|Ruft verschiedene Typen von Informationen zu einer Zeichenfolge ab.|  
|[CDC::GetCharWidth](../Topic/CDC::GetCharWidth.md)|Ruft die Bruchen Breiten von nachgestellten Zeichen in einem angegebenen Bereich von der aktuellen Schriftart ab.|  
|[CDC::GetCharWidthI](../Topic/CDC::GetCharWidthI.md)|Ruft die Breite, in logischen Koordinaten, von nachfolgenden Symbolindizes in einem angegebenen Bereich von der aktuellen Schriftart ab.|  
|[CDC::GetClipBox](../Topic/CDC::GetClipBox.md)|Ruft die Abmessungen des festesten umschließenden Rechtecks um die aktuelle Clippinggrenze ab.|  
|[CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)|Ruft die Farbenanpassungswerte für den Gerätekontext ab.|  
|[CDC::GetCurrentBitmap](../Topic/CDC::GetCurrentBitmap.md)|Gibt einen Zeiger auf den aktuell ausgewählten `CBitmap`\-Objekt zurück.|  
|[CDC::GetCurrentBrush](../Topic/CDC::GetCurrentBrush.md)|Gibt einen Zeiger auf den aktuell ausgewählten `CBrush`\-Objekt zurück.|  
|[CDC::GetCurrentFont](../Topic/CDC::GetCurrentFont.md)|Gibt einen Zeiger auf den aktuell ausgewählten `CFont`\-Objekt zurück.|  
|[CDC::GetCurrentPalette](../Topic/CDC::GetCurrentPalette.md)|Gibt einen Zeiger auf den aktuell ausgewählten `CPalette`\-Objekt zurück.|  
|[CDC::GetCurrentPen](../Topic/CDC::GetCurrentPen.md)|Gibt einen Zeiger auf den aktuell ausgewählten `CPen`\-Objekt zurück.|  
|[CDC::GetCurrentPosition](../Topic/CDC::GetCurrentPosition.md)|Ruft die aktuelle Position des Stiftes ab \(in logischen Koordinaten\).|  
|[CDC::GetDCBrushColor](../Topic/CDC::GetDCBrushColor.md)|Ruft die aktuelle Pinselfarbe ab.|  
|[CDC::GetDCPenColor](../Topic/CDC::GetDCPenColor.md)|Ruft die aktuelle Stiftfarbe ab.|  
|[CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md)|Ruft eine bestimmte Art gerätespezifische Informationen über die Funktionen eines angegebenen Anzeigegeräts ab.|  
|[CDC::GetFontData](../Topic/CDC::GetFontData.md)|Ruft metrische Informationen der Schriftarten aus einer Datei der skalierbaren Schriftarten ab.  Die abzurufen Informationen werden identifiziert, indem ein Offset in die Schriftartdatei und in die Länge der Informationen angibt, um zurückzukehren.|  
|[CDC::GetFontLanguageInfo](../Topic/CDC::GetFontLanguageInfo.md)|Gibt Informationen über die momentan ausgewählte Schriftart für den angegebenen Anzeigekontext zurück.|  
|[CDC::GetGlyphOutline](../Topic/CDC::GetGlyphOutline.md)|Ruft die Konturenkurve oder \-Bitmap für ein Konturenzeichen in der aktuellen Schriftart ab.|  
|[CDC::GetGraphicsMode](../Topic/CDC::GetGraphicsMode.md)|Ruft den aktuellen Grafikmodus für den angegebenen Gerätekontext ab.|  
|[CDC::GetHalftoneBrush](../Topic/CDC::GetHalftoneBrush.md)|Ruft einen Halbtonpinsel ab.|  
|[CDC::GetKerningPairs](../Topic/CDC::GetKerningPairs.md)|Ruft die Zeichenkerningpaare für die Schriftart ab, die derzeit im angegebenen Gerätekontext ausgewählt ist.|  
|[CDC::GetLayout](../Topic/CDC::GetLayout.md)|Ruft das Layout eines Gerätekontexts ab \(DC\).  Das Layout kann entweder von links nach rechts sein \(Standard\) oder von rechts nach links \(gespiegelt\).|  
|[CDC::GetMapMode](../Topic/CDC::GetMapMode.md)|Ruft den aktuellen Zuordnungsmodus ab.|  
|[CDC::GetMiterLimit](../Topic/CDC::GetMiterLimit.md)|Gibt die Gehrungsfugengrenze für den Gerätekontext zurück.|  
|[CDC::GetNearestColor](../Topic/CDC::GetNearestColor.md)|Ruft die größte logische Farbe zu einer angegebenen logischen Farbe ab, die das angegebene Gerät darstellen kann.|  
|[CDC::GetOutlineTextMetrics](../Topic/CDC::GetOutlineTextMetrics.md)|Ruft metrische Informationen der Schriftart für TrueType\-Schriftarten ab.|  
|[CDC::GetOutputCharWidth](../Topic/CDC::GetOutputCharWidth.md)|Ruft die Breite von einzelnen Zeichen in einer nachfolgenden Gruppe Zeichen von der aktuellen Schriftart ab, die den Ausgabegerätekontext verwendet.|  
|[CDC::GetOutputTabbedTextExtent](../Topic/CDC::GetOutputTabbedTextExtent.md)|Berechnet die Breite und die Höhe einer Zeichenfolge auf dem Ausgabegerätekontext.|  
|[CDC::GetOutputTextExtent](../Topic/CDC::GetOutputTextExtent.md)|Berechnet die Breite und die Höhe einer Textzeile auf dem Ausgabegerätekontext mit der aktuellen Schriftarten, um die Dimensionen zu bestimmen.|  
|[CDC::GetOutputTextMetrics](../Topic/CDC::GetOutputTextMetrics.md)|Ruft die Metriken für die aktuelle Schriftart vom Ausgabegerätekontext ab.|  
|[CDC::GetPath](../Topic/CDC::GetPath.md)|Ruft die Koordinaten ab, die die Endpunkte von Zeilen definieren und die Steuerpunkte Kurven starten im Pfad, der in den Gerätekontext ausgewählt ist.|  
|[CDC::GetPixel](../Topic/CDC::GetPixel.md)|Ruft den RGB\-Farbwert des Pixels am angegebenen Punkt ab.|  
|[CDC::GetPolyFillMode](../Topic/CDC::GetPolyFillMode.md)|Ruft den aktuellen Polygonfüllungsmodus ab.|  
|[CDC::GetROP2](../Topic/CDC::GetROP2.md)|Ruft den aktuellen Zeichnungsmodus ab.|  
|[CDC::GetSafeHdc](../Topic/CDC::GetSafeHdc.md)|Gibt [CDC::m\_hDC](../Topic/CDC::m_hDC.md), den Ausgabegerätekontext zurück.|  
|[CDC::GetStretchBltMode](../Topic/CDC::GetStretchBltMode.md)|Ruft den aktuellen Bitmapstreckmodus ab.|  
|[CDC::GetTabbedTextExtent](../Topic/CDC::GetTabbedTextExtent.md)|Berechnet die Breite und die Höhe einer Zeichenfolge auf dem Attributgerätekontext.|  
|[CDC::GetTextAlign](../Topic/CDC::GetTextAlign.md)|Ruft die Textausrichtungsflags ab.|  
|[CDC::GetTextCharacterExtra](../Topic/CDC::GetTextCharacterExtra.md)|Ruft die aktuelle Einstellung für die Menge des Zeichenabstands ab.|  
|[CDC::GetTextColor](../Topic/CDC::GetTextColor.md)|Ruft die aktuelle Textfarbe ab.|  
|[CDC::GetTextExtent](../Topic/CDC::GetTextExtent.md)|Berechnet die Breite und die Höhe einer Textzeile auf dem Attributgerätekontext mit der aktuellen Schriftarten, um die Dimensionen zu bestimmen.|  
|[CDC::GetTextExtentExPointI](../Topic/CDC::GetTextExtentExPointI.md)|Ruft die Anzahl der Zeichen in einer angegebenen Zeichenfolge, die innerhalb eines angegebenen Bereichs passt ab und füllt ein Array mit dem Textwertebereich für jedes dieser Zeichen aus.|  
|[CDC::GetTextExtentPointI](../Topic/CDC::GetTextExtentPointI.md)|Ruft die Breite und Höhe des angegebenen Arrays der Symbolindizes ab.|  
|[CDC::GetTextFace](../Topic/CDC::GetTextFace.md)|Kopiert den Schriftartnamen der aktuellen Schriftarten in einen Puffer als auf NULL endende Zeichenfolge.|  
|[CDC::GetTextMetrics](../Topic/CDC::GetTextMetrics.md)|Ruft die Metriken für die aktuelle Schriftart vom Attributgerätekontext ab.|  
|[CDC::GetViewportExt](../Topic/CDC::GetViewportExt.md)|Ruft das die X\- und y\-Wertebereiche des Viewports ab.|  
|[CDC::GetViewportOrg](../Topic/CDC::GetViewportOrg.md)|Ruft die x\- und y\-Koordinaten für Viewportursprungs ab.|  
|[CDC::GetWindow](../Topic/CDC::GetWindow.md)|Gibt das Fenster zurück, das mit dem Anzeigegerätenkontext zugeordnet ist.|  
|[CDC::GetWindowExt](../Topic/CDC::GetWindowExt.md)|Ruft das die X\- und y\-Wertebereiche zugeordneten des Fensters ab.|  
|[CDC::GetWindowOrg](../Topic/CDC::GetWindowOrg.md)|Ruft die x\- und y\-Koordinaten Rand des Fensters zugeordneten ab.|  
|[CDC::GetWorldTransform](../Topic/CDC::GetWorldTransform.md)|Ruft die aktuelle Worldspace\-SeiteLeerzeichen Transformation ab.|  
|[CDC::GradientFill](../Topic/CDC::GradientFill.md)|füllt Rechteck und Dreieckstrukturen mit einer gradating Farbe.|  
|[CDC::GrayString](../Topic/CDC::GrayString.md)|Draws blendete \(abgeblendeten\) Text am angegebenen Speicherort ab.|  
|[CDC::HIMETRICtoDP](../Topic/CDC::HIMETRICtoDP.md)|Konvertiert **HIMETRIC** Einheiten in Geräteeinheiten.|  
|[CDC::HIMETRICtoLP](../Topic/CDC::HIMETRICtoLP.md)|Konvertiert **HIMETRIC** Einheiten in logische Einheiten.|  
|[CDC::IntersectClipRect](../Topic/CDC::IntersectClipRect.md)|Erstellt einen neuen Clippingbereich durch die Modellierung der Schnittmenge des Strombereichs und des Rechtecks.|  
|[CDC::InvertRect](../Topic/CDC::InvertRect.md)|Gibt den Inhalt eines Rechtecks um.|  
|[CDC::InvertRgn](../Topic/CDC::InvertRgn.md)|Gibt die Farben in einem Bereich um.|  
|[CDC::IsPrinting](../Topic/CDC::IsPrinting.md)|Bestimmt, ob der Gerätekontext für das Drucken verwendet wird.|  
|[CDC::LineTo](../Topic/CDC::LineTo.md)|Zeichnet eine Zeile von der aktuellen Position bis, jedoch nicht, einschließlich ein Punkt.|  
|[CDC::LPtoDP](../Topic/CDC::LPtoDP.md)|Konvertiert logische Einheiten in Geräteeinheiten.|  
|[CDC::LPtoHIMETRIC](../Topic/CDC::LPtoHIMETRIC.md)|Konvertiert logische Einheiten in **HIMETRIC** Einheiten.|  
|[CDC::MaskBlt](../Topic/CDC::MaskBlt.md)|Kombiniert die Farbdaten für die Quell\- und Zielbitmaps mithilfe des angegebenen Masken\- und Rastervorgangs.|  
|[CDC::ModifyWorldTransform](../Topic/CDC::ModifyWorldTransform.md)|Ändert die globale Transformation für einen Gerätekontext unter Verwendung des angegebenen Modus.|  
|[CDC::MoveTo](../Topic/CDC::MoveTo.md)|Verschiebt die aktuelle Position.|  
|[CDC::OffsetClipRgn](../Topic/CDC::OffsetClipRgn.md)|Verschiebt den Clippingbereich des angegebenen Gerät.|  
|[CDC::OffsetViewportOrg](../Topic/CDC::OffsetViewportOrg.md)|Ändert den Viewportursprung relativ zu den Koordinaten des aktuellen Viewportursprungs.|  
|[CDC::OffsetWindowOrg](../Topic/CDC::OffsetWindowOrg.md)|Ändert den Fensterursprung relativ zu den Koordinaten des Ursprungs des aktiven Fensters.|  
|[CDC::PaintRgn](../Topic/CDC::PaintRgn.md)|Füllt einen Bereich mit dem ausgewählten Pinsel aus.|  
|[CDC::PatBlt](../Topic/CDC::PatBlt.md)|Erstellt ein Bitmuster.|  
|[CDC::Pie](../Topic/CDC::Pie.md)|Zeichnet einen Kreis\-gestalteten Keil.|  
|[CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md)|Gibt den Inhalt der angegebenen Metadatei auf dem angegebenen Gerät erneut.  Die erweiterte Version von `PlayMetaFile` zeigt das Bild an, das in der angegebenen ErhöhenFormat Metadatei gespeichert wird.  Der Metadatei kann beliebig oft wiederholt werden.|  
|[CDC::PlgBlt](../Topic/CDC::PlgBlt.md)|Führt einen Bitblocktransfer der Bits Farbdaten von aus dem angegebenen Rechteck im Quellgerätekontext zum angegebenen Parallelogramm im angegebenen Gerätekontext aus.|  
|[CDC::PolyBezier](../Topic/CDC::PolyBezier.md)|Zeichnet eine oder mehrere Bézier\-Splines.  Die aktuelle Position wird weder verwendet weiterhin aktualisiert.|  
|[CDC::PolyBezierTo](../Topic/CDC::PolyBezierTo.md)|Zeichnet eine oder mehrere Bézier\-Splines und verschiebt die aktuelle Position auf den Endpunkt der letzten Bézier\-Splines.|  
|[CDC::PolyDraw](../Topic/CDC::PolyDraw.md)|Zeichnet einen Satz Liniensegmente und Bézier\-Splines.  Diese Funktion aktualisiert die aktuelle Position.|  
|[CDC::Polygon](../Topic/CDC::Polygon.md)|Zeichnet ein Polygon vorhandene zwei oder mehr zeigt \(Eckpunkte\) durch Linien verbunden.|  
|[CDC::Polyline](../Topic/CDC::Polyline.md)|Zeichnet einen Satz Liniensegmente, die die angegebenen Punkte herstellen.|  
|[CDC::PolylineTo](../Topic/CDC::PolylineTo.md)|Zeichnet eine oder mehrere geraden und verschiebt die aktuelle Position auf den Endpunkt der letzten Zeile.|  
|[CDC::PolyPolygon](../Topic/CDC::PolyPolygon.md)|Erstellt zwei oder mehr Polygone, die mithilfe des aktuellen Polygonfüllungsmodus gefüllt werden.  Die Polygone sind möglicherweise disjunkt, oder sie überschneiden sich.|  
|[CDC::PolyPolyline](../Topic/CDC::PolyPolyline.md)|Zeichnet eine Reihe von mehrere Segmente der verbundenen Linie.  Die aktuelle Position wird weder von dieser Funktion verwendet weiterhin aktualisiert.|  
|[CDC::PtVisible](../Topic/CDC::PtVisible.md)|Gibt an, ob der angegebene Punkt innerhalb des Clippingbereichs ist.|  
|[CDC::RealizePalette](../Topic/CDC::RealizePalette.md)|Ordnet Paletteneinträge in der aktuellen Logischen Palette zur Systempalette zu.|  
|[CDC::Rectangle](../Topic/CDC::Rectangle.md)|Zeichnet ein Rechteck unter Verwendung des aktuellen Stiftes und füllt ihn mithilfe des aktuellen Pinsels aus.|  
|[CDC::RectVisible](../Topic/CDC::RectVisible.md)|Bestimmt, ob ein Teil des angegebenen Rechtecks innerhalb des Clippingbereichs liegt.|  
|[CDC::ReleaseAttribDC](../Topic/CDC::ReleaseAttribDC.md)|Gibt `m_hAttribDC`, den Attributgerätekontext frei.|  
|[CDC::ReleaseOutputDC](../Topic/CDC::ReleaseOutputDC.md)|Gibt `m_hDC`, den Ausgabegerätekontext frei.|  
|[CDC::ResetDC](../Topic/CDC::ResetDC.md)|Aktualisiert den `m_hAttribDC` Gerätekontext.|  
|[CDC::RestoreDC](../Topic/CDC::RestoreDC.md)|Stellt den Gerätekontext zu einem vorherigen Zustand zurück, der mit `SaveDC` gespeichert wird.|  
|[CDC::RoundRect](../Topic/CDC::RoundRect.md)|Zeichnet ein Rechteck mit abgerundeten Ecken mithilfe des aktuellen Stiftes und unter Verwendung des aktuellen Pinselfarbe gefüllt.|  
|[CDC::SaveDC](../Topic/CDC::SaveDC.md)|Rettet den aktuellen Zustand des Gerätekontexts.|  
|[CDC::ScaleViewportExt](../Topic/CDC::ScaleViewportExt.md)|Ändert die Viewportgröße relativ zum aktuellen Werten.|  
|[CDC::ScaleWindowExt](../Topic/CDC::ScaleWindowExt.md)|Ändert die Fenstergrößen relativ zum aktuellen Werten.|  
|[CDC::ScrollDC](../Topic/CDC::ScrollDC.md)|Führt ein Rechteck von Bits horizontal und vertikal aus.|  
|[CDC::SelectClipPath](../Topic/CDC::SelectClipPath.md)|Wählt den aktuellen Pfad als Clippingbereich für den Gerätekontext aus und kombiniert den neuen Bereich mit dem vorhandenen Clippingbereich mithilfe des angegebenen Modus.|  
|[CDC::SelectClipRgn](../Topic/CDC::SelectClipRgn.md)|Führt den angegebenen Bereich mit dem aktuellen Clippingbereich mithilfe des angegebenen Modus.|  
|[CDC::SelectObject](../Topic/CDC::SelectObject.md)|Wählt ein GDI\-Zeichnungsobjekt wie ein Stift aus.|  
|[CDC::SelectPalette](../Topic/CDC::SelectPalette.md)|Wählt die Logische Palette aus.|  
|[CDC::SelectStockObject](../Topic/CDC::SelectStockObject.md)|Wählt eine der vordefinierten vordefinierten Stifte, der Pinsel oder der Schriftarten, die von Windows bereitgestellt werden.|  
|[CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)|Legt eine vom Programmierer bereitgestellte Rückruffunktion fest, die Windows aufruft, wenn ein Druckauftrag abgebrochen werden muss.|  
|[CDC::SetArcDirection](../Topic/CDC::SetArcDirection.md)|Legt die für Bogen fest verwendet werden Zeichnungsrichtung, und Rechteck funktioniert.|  
|[CDC::SetAttribDC](../Topic/CDC::SetAttribDC.md)|Legt `m_hAttribDC`, den Attributgerätekontext fest.|  
|[CDC::SetBkColor](../Topic/CDC::SetBkColor.md)|Legt die aktuelle Hintergrundfarbe fest.|  
|[CDC::SetBkMode](../Topic/CDC::SetBkMode.md)|Legt den Hintergrundmodus fest.|  
|[CDC::SetBoundsRect](../Topic/CDC::SetBoundsRect.md)|Steuert die Ansammlung von Informationen des umgebenden Rechtecks für den angegebenen Gerätekontext.|  
|[CDC::SetBrushOrg](../Topic/CDC::SetBrushOrg.md)|Gibt den Ursprung für den folgenden Pinsel veranschaulicht, der in einen Gerätekontext ausgewählt ist.|  
|[CDC::SetColorAdjustment](../Topic/CDC::SetColorAdjustment.md)|Legt die Farbenanpassungswerte für den Gerätekontext mithilfe der angegebenen Werte fest.|  
|[CDC::SetDCBrushColor](../Topic/CDC::SetDCBrushColor.md)|Legt die aktuelle Pinselfarbe fest.|  
|[CDC::SetDCPenColor](../Topic/CDC::SetDCPenColor.md)|Legt die aktuelle Stiftfarbe fest.|  
|[CDC::SetGraphicsMode](../Topic/CDC::SetGraphicsMode.md)|Legt den aktuellen Grafikmodus für den angegebenen Gerätekontext fest.|  
|[CDC::SetLayout](../Topic/CDC::SetLayout.md)|Ändert das Layout eines Gerätekontexts \(DC\).|  
|[CDC::SetMapMode](../Topic/CDC::SetMapMode.md)|Legt den aktuellen Zuordnungsmodus fest.|  
|[CDC::SetMapperFlags](../Topic/CDC::SetMapperFlags.md)|Ändert den Algorithmus, der dem Schriftartenmapper verwendet, wenn er logische Schriftarten zu den physischen Schriftarten zuordnet.|  
|[CDC::SetMiterLimit](../Topic/CDC::SetMiterLimit.md)|Setzt die Grenzwert für die Länge Gehrungsfugenjoine für den Gerätekontext fest.|  
|[CDC::SetOutputDC](../Topic/CDC::SetOutputDC.md)|Legt `m_hDC`, den Ausgabegerätekontext fest.|  
|[CDC::SetPixel](../Topic/CDC::SetPixel.md)|Legt das Pixel am angegebenen Punkt zur nächsten Schätzwert der angegebenen Farbe fest.|  
|[CDC::SetPixelV](../Topic/CDC::SetPixelV.md)|Legt das Pixel an angegebenen Koordinaten zur nächsten Schätzwert der angegebenen Farbe fest.  `SetPixelV` ist schneller als `SetPixel`, da es ist nicht erforderlich, um den Farbwert des tatsächlich gezeichneten Punkts zurückzugeben.|  
|[CDC::SetPolyFillMode](../Topic/CDC::SetPolyFillMode.md)|Legt den Polygonfüllungsmodus fest.|  
|[CDC::SetROP2](../Topic/CDC::SetROP2.md)|Legt den aktuellen Zeichnungsmodus fest.|  
|[CDC::SetStretchBltMode](../Topic/CDC::SetStretchBltMode.md)|Legt den Bitmapstreckmodus fest.|  
|[CDC::SetTextAlign](../Topic/CDC::SetTextAlign.md)|Legt die Textausrichtungsflags fest.|  
|[CDC::SetTextCharacterExtra](../Topic/CDC::SetTextCharacterExtra.md)|Legt die Menge des Zeichenabstands fest.|  
|[CDC::SetTextColor](../Topic/CDC::SetTextColor.md)|Legt die Textfarbe fest.|  
|[CDC::SetTextJustification](../Topic/CDC::SetTextJustification.md)|Fügt den Unterstreichung Leerzeichen in einer Zeichenfolge hinzu.|  
|[CDC::SetViewportExt](../Topic/CDC::SetViewportExt.md)|Legt das die X\- und y\-Wertebereiche des Viewports fest.|  
|[CDC::SetViewportOrg](../Topic/CDC::SetViewportOrg.md)|Legt den Viewportursprung fest.|  
|[CDC::SetWindowExt](../Topic/CDC::SetWindowExt.md)|Legt das die X\- und y\-Wertebereiche des zugeordneten Fensters fest.|  
|[CDC::SetWindowOrg](../Topic/CDC::SetWindowOrg.md)|Legt den Fensterursprung des Gerätekontexts fest.|  
|[CDC::SetWorldTransform](../Topic/CDC::SetWorldTransform.md)|Legt die aktuelle Worldspace\-SeiteLeerzeichen Transformation fest.|  
|[CDC::StartDoc](../Topic/CDC::StartDoc.md)|Informiert den Gerätetreiber, dass ein neuer Druckauftrag beginnen soll.|  
|[CDC::StartPage](../Topic/CDC::StartPage.md)|Informiert den Gerätetreiber, dass eine neue Seite beginnen soll.|  
|[CDC::StretchBlt](../Topic/CDC::StretchBlt.md)|Verschiebt eine Bitmap aus einem Quellrechteck und Gerät in ein Zielrechteck und bei Bedarf oder komprimiert wird die Bitmap, um die Dimensionen des Zielrechtecks angepasst.|  
|[CDC::StrokeAndFillPath](../Topic/CDC::StrokeAndFillPath.md)|Schließt alle geöffneten Abbildungen in einem Pfad, Drücken der Konturen des Pfads, mithilfe des aktuellen Stiftes, und füllt den Innenbereich mithilfe des aktuellen Pinsels aus.|  
|[CDC::StrokePath](../Topic/CDC::StrokePath.md)|Rendert den angegebenen Pfad mithilfe des aktuellen Stiftes.|  
|[CDC::TabbedTextOut](../Topic/CDC::TabbedTextOut.md)|Schreibt eine Zeichenfolge an einer angegebenen Position und erweitert Registerkarten zu den Werten, die in einem Array Tabulationspositionen angegeben werden.|  
|[CDC::TextOut](../Topic/CDC::TextOut.md)|Schreibt eine Zeichenfolge an einer angegebenen Position mithilfe der aktuell ausgewählten Schriftarten.|  
|[CDC::TransparentBlt](../Topic/CDC::TransparentBlt.md)|Überträgt einen Bitblock Farbdaten aus dem angegebenen Quellgerätekontext in einen Zielgerätekontext und gibt eine angegebene Farbe transparent in der Übertragung.|  
|[CDC::UpdateColors](../Topic/CDC::UpdateColors.md)|Aktualisiert den Clientbereich des Gerätekontexts durch die Anpassung der aktuellen Farben im Clientbereich an die Systempalette auf einer Pixel\-durchPixel Basis.|  
|[CDC::WidenPath](../Topic/CDC::WidenPath.md)|Definiert den aktuellen Pfad als der Bereich der neu gezeichnet wird, wenn der Pfad mithilfe des Stiftes gestrichelt wurden, der gerade in den Gerätekontext ausgewählt wurde.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDC::operator HDC](../Topic/CDC::operator%20HDC.md)|Ruft das Handle des Gerätekontexts ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDC::m\_hAttribDC](../Topic/CDC::m_hAttribDC.md)|Der Attributgerätekontext verwendet `CDC` von diesem Objekt.|  
|[CDC::m\_hDC](../Topic/CDC::m_hDC.md)|Der Ausgabegerätekontext verwendet `CDC` von diesem Objekt.|  
  
## Hinweise  
 Das Objekt stellt `CDC`\-Memberfunktionen für das Arbeiten mit einem Gerätekontext, wie einer Anzeige oder ein Drucker Member sowie für das Arbeiten mit einem Anzeigekontext, der mit dem Innenbereich eines Fensters zugeordnet ist.  
  
 Führen Sie alle Zeichnung durch die Memberfunktion eines Objekts `CDC`.  Die Klasse stellt die Memberfunktionen für Gerätekontextvorgänge bereit und funktioniert mit Ziehwerkzeugen, typsicherer Objekt\-Auswahl des GDI \(Graphics Device Interface\), und arbeitet mit Farben und Paletten.  Sie stellt außerdem Memberfunktionen zum Abrufen und Festlegen von Zeichnungsattributen, Zuordnung und funktioniert mit dem Viewport und funktioniert mit der Fenstergröße und konvertiert die Koordinaten und funktioniert, Clipping mit Bereichen, zeichnet Zeichnungen und einfache Formen der Zeichnung, Ellipsen und Polygone.  Memberfunktionen werden auch zum Zeichnen von Text bereitgestellt und verwenden Schriftarten, mit der Druckerescapen, des Bildlaufs und des Wiedergebens von Metadateien.  
  
 Um ein `CDC`\-Objekt zu verwenden, erstellen Sie es und rufen Sie dann die Memberfunktionen für die parallele Windows\-Funktionen die Gerätekontexte verwenden.  
  
> [!NOTE]
>  Unter Windows 95\/98 werden alle Bildschirmkoordinaten in 16 Bits beschränkt.  Daher muss `int`, das einer `CDC`\-Memberfunktion übergeben wird, im Bereich liegen \- 32768 bis 32767.  
  
 Für bestimmte Verwendungsmöglichkeiten stellt Microsoft Foundation Class\-Bibliothek mehrere Klassen, die von `CDC` abgeleitet werden.  `CPaintDC` kapselt Aufrufe `BeginPaint` und zu `EndPaint`.  `CClientDC` verwaltet einen Anzeigekontext, der mit dem Innenbereich eines Fensters zugeordnet ist.  `CWindowDC` verwaltet einen Anzeigekontext, der einem gesamten Fenster, einschließlich der Frames und Steuerelemente zugeordnet ist.  `CMetaFileDC` ordnet einem Gerätekontext mit einer Metadatei zu.  
  
 `CDC` stellt zwei Memberfunktionen bereit, [GetLayout](../Topic/CDC::GetLayout.md) und [SetLayout](../Topic/CDC::SetLayout.md), für die Umkehrung des Layouts eines Gerätekontexts bereit, der nicht das Layout von einem Fenster erbt.  Solche Ausrichtung von rechts nach links ist für Anwendungen erforderlich, die für Kulturen, wie Arabisch oder Hebräisch geschrieben werden, wo das Zeichenlayout nicht der europäische Standardwert ist.  
  
 `CDC` enthält zwei Gerätekontexte, [m\_hDC](../Topic/CDC::m_hDC.md) und [m\_hAttribDC](../Topic/CDC::m_hAttribDC.md), die, auf `CDC` Erstellung eines Objekts, das gleiche Gerät verweisen.  `CDC` verweist alles, GDI\-Aufrufe auf `m_hDC` und die meisten Aufrufe des Attributs auf `m_hAttribDC` GDI auszugeben.  \(Ein Beispiel eines Attributaufrufs ist `GetTextColor`, während `SetTextColor` ein Ausgabeaufruf ist.\)  
  
 Zum Beispiel verwendet das Framework diese beiden Gerätekontexte, um ein `CMetaFileDC`\-Objekt zu implementieren, die Ausgabe in eine Metadatei sendet, die beim Lesen von einem physischen Gerät zugeordnet.  Seitenansicht wird im Framework auf ähnliche Weise implementiert.  Sie können die zwei Gerätekontexte auf ähnliche Weise im anwendungsspezifischen auch Code verwenden.  
  
 Es gibt vorkommen, dass Sie möglicherweise TextMetrik Informationen aus den `m_hDC` und `m_hAttribDC` Gerätekontexten erfordern.  Die folgenden Paare von Funktionen bieten diese Funktion:  
  
|Wird m\_hAttribDC|Wird m\_hDC|  
|-----------------------|-----------------|  
|[GetTextExtent](../Topic/CDC::GetTextExtent.md)|[GetOutputTextExtent](../Topic/CDC::GetOutputTextExtent.md)|  
|[GetTabbedTextExtent](../Topic/CDC::GetTabbedTextExtent.md)|[GetOutputTabbedTextExtent](../Topic/CDC::GetOutputTabbedTextExtent.md)|  
|[GetTextMetrics](../Topic/CDC::GetTextMetrics.md)|[GetOutputTextMetrics](../Topic/CDC::GetOutputTextMetrics.md)|  
|[GetCharWidth](../Topic/CDC::GetCharWidth.md)|[GetOutputCharWidth](../Topic/CDC::GetOutputCharWidth.md)|  
  
 Weitere Informationen zu `CDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDC`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPaintDC Class](../../mfc/reference/cpaintdc-class.md)   
 [CWindowDC Class](../../mfc/reference/cwindowdc-class.md)   
 [CClientDC Class](../../mfc/reference/cclientdc-class.md)   
 [CMetaFileDC Class](../../mfc/reference/cmetafiledc-class.md)