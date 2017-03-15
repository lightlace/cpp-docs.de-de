---
title: CDC-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDC
dev_langs:
- C++
helpviewer_keywords:
- Windows [C++], device contexts
- Windows 95 [C++], screen coordinates
- device contexts [C++], CDC class
- screen coordinates in device contexts
- coordinates in Windows 95/98 [C++]
- Windows 98 [C++], screen coordinates
- CDC class
ms.assetid: 715b3334-cb2b-4c9c-8067-02eb7c66c8b2
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 80ccd3f8bed6bd74e22d4db5e176ee50528d3187
ms.lasthandoff: 02/24/2017

---
# <a name="cdc-class"></a>CDC-Klasse
Definiert eine Klasse von Gerätekontextobjekten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDC : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDC::CDC](#cdc)|Erstellt ein `CDC`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDC::AbortDoc](#abortdoc)|Beendet den aktuellen Auftrag, löschen Alles, was die Anwendung wurde seit dem letzten Aufruf von an das Gerät geschrieben der `StartDoc` Member-Funktion.|  
|[CDC::AbortPath](#abortpath)|Schließt und verwirft alle Pfade in den Gerätekontext.|  
|[CDC::AddMetaFileComment](#addmetafilecomment)|Den Kommentar kopiert aus einem Puffer in einer angegebenen EMF-Datei.|  
|[CDC::AlphaBlend](#alphablend)|Zeigt die Bitmaps, die transparent oder halbtransparent Pixel haben.|  
|[CDC::AngleArc](#anglearc)|Ein Liniensegment zeichnet einen Bogen, und die aktuelle Position bis zum Endpunkt des Bogens verschiebt.|  
|[CDC::ARC](#arc)|Zeichnet einen elliptischen Bogen.|  
|[CDC::ArcTo](#arcto)|Zeichnet einen elliptischen Bogen. Diese Funktion ist vergleichbar mit `Arc`, außer dass die aktuelle Position aktualisiert wird.|  
|[CDC::Attach](#attach)|Fügt einen Windows-Gerätekontext zu diesem `CDC` Objekt.|  
|[CDC:: beginpath](#beginpath)|Öffnet eine Klammer Pfad im Device Context.|  
|[CDC::BitBlt](#bitblt)|Kopiert eine Bitmap aus einem angegebenen Gerätekontext.|  
|[CDC::Chord](#chord)|Zeichnet ein Band (eine geschlossene begrenzt durch die Schnittmenge einer Ellipse und einem Liniensegment).|  
|[CDC::CloseFigure](#closefigure)|Schließt eine offene Figur in einem Pfad.|  
|[CDC::CreateCompatibleDC](#createcompatibledc)|Erstellt einen Speicher-Gerätekontext, der mit einem anderen Gerätekontext kompatibel ist. Sie können es um im Speicher zu erstellen.|  
|[CDC::CreateDC](#createdc)|Erstellt einen Gerätekontext für ein bestimmtes Gerät.|  
|[CDC::CreateIC](#createic)|Erstellt einen Informationskontext für ein bestimmtes Gerät. Dies bietet eine schnelle Möglichkeit, Informationen über das Gerät zu erhalten, ohne einen Gerätekontext zu erstellen.|  
|[CDC::DeleteDC](#deletedc)|Löscht die zugeordnete Windows-Gerätekontext `CDC` Objekt.|  
|[CDC::DeleteTempMap](#deletetempmap)|Aufgerufen, indem die `CWinApp` Zeit im Leerlauf Handler So löschen Sie alle temporären `CDC` von erstellte Objekt `FromHandle`. Außerdem trennt den Gerätekontext.|  
|[CDC::Detach](#detach)|Trennt den Windows-Gerätekontext aus diesem `CDC` Objekt.|  
|[CDC::DPtoHIMETRIC](#dptohimetric)|Konvertiert Geräteeinheiten in **HIMETRIC** Einheiten.|  
|[CDC::DPtoLP](#dptolp)|Geräteeinheiten konvertiert in logischen Einheiten.|  
|[CDC::Draw3dRect](#draw3drect)|Zeichnet eine dreidimensionale Rechteck.|  
|[CDC::DrawDragRect](#drawdragrect)|Löscht und zeichnet ein Rechteck, wie es gezogen wird.|  
|[CDC::DrawEdge](#drawedge)|Zeichnet die Ränder eines Rechtecks an.|  
|[CDC::DrawEscape](#drawescape)|Greift auf Zeichnen Funktionen einer Videoanzeige, die nicht direkt über die Graphics Device Interface (GDI) verfügbar sind.|  
|[CDC::DrawFocusRect](#drawfocusrect)|Zeichnet ein Rechteck in den Stil verwendet, um den Fokus anzugeben.|  
|[CDC::DrawFrameControl](#drawframecontrol)|Zeichnen Sie einen Frame-Steuerelement.|  
|[CDC::DrawIcon](#drawicon)|Zeichnet ein Symbol an.|  
|[CDC::DrawState](#drawstate)|Zeigt ein Bild an und wendet einen visuellen Effekt, um einen Zustand anzugeben.|  
|[CDC:: DrawText](#drawtext)|Zeichnet formatierten Text im angegebenen Rechteck.|  
|[CDC::DrawTextEx](#drawtextex)|Zeichnet formatierten Text im angegebenen Rechteck mit zusätzliche Formate.|  
|[CDC::Ellipse](#ellipse)|Zeichnet eine Ellipse.|  
|[CDC::EndDoc](#enddoc)|Beendet einen Druckauftrag gestartet, indem die `StartDoc` -Memberfunktion.|  
|[CDC::EndPage](#endpage)|Informiert den Treiber, den eine Seite beendet wird.|  
|[CDC::EndPath](#endpath)|Schließt eine Klammer Pfad, und wählt den Pfad, der die schließende Klammer im Gerätekontext definiert.|  
|[CDC:: EnumObjects](#enumobjects)|Listet die Stifte und Pinsel in einem Gerätekontext verfügbar.|  
|[CDC::Escape](#escape)|Ist die Anwendung auf Funktionen zuzugreifen, die nicht direkt von einem bestimmten Gerät über GDI verfügbar sind. Darüber hinaus können den Zugriff auf Windows-Escape-Funktionen. Escape-Aufrufe, die von einer Anwendung werden übersetzt und an den Gerätetreiber gesendet.|  
|[CDC::ExcludeClipRect](#excludecliprect)|Erstellt einen neuen Ausschneidebereich, der aus den vorhandenen Ausschneidebereich abzüglich des angegebenen Rechtecks besteht.|  
|[CDC::ExcludeUpdateRgn](#excludeupdatergn)|Verhindert, dass ungültige Bereiche eines Fensters zeichnen einen aktualisierten Bereich im Fenster einen Ausschneidebereich ausgeschlossen.|  
|[CDC::ExtFloodFill](#extfloodfill)|Füllt einen Bereich mit dem aktuellen Pinsel. Bietet mehr Flexibilität als die [CDC::FloodFill](#floodfill) Member-Funktion.|  
|[CDC::ExtTextOut](#exttextout)|Schreibt eine Zeichenfolge in einen rechteckigen Bereich mit der aktuell ausgewählten Schriftart.|  
|[CDC::FillPath](#fillpath)|Schließt alle geöffneten Figuren im aktuellen Pfad und den Pfad innere mithilfe des aktuellen Pinsel und Polygon-Füllmodus füllt.|  
|[CDC::fillRect](#fillrect)|Füllt ein angegebenes Rechteck mit einem bestimmten Pinsel.|  
|[CDC::FillRgn](#fillrgn)|Füllt einen bestimmten Bereich mit dem angegebenen Pinsel.|  
|[CDC::FillSolidRect](#fillsolidrect)|Füllt ein Rechteck mit einer Volltonfarbe aus.|  
|[CDC::FlattenPath](#flattenpath)|Wandelt alle Kurven in den aktuellen Gerätekontext ausgewählten Pfad umwandelt und jede Kurve in eine Sequenz von Zeilen.|  
|[CDC::FloodFill](#floodfill)|Füllt einen Bereich mit dem aktuellen Pinsel.|  
|[CDC:: FrameRect](#framerect)|Zeichnet einen Rahmen um ein Rechteck.|  
|[CDC::FrameRgn](#framergn)|Zeichnet einen Rahmen auf einen bestimmten Bereich eines Pinsels.|  
|[CDC::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CDC` Objekt, wenn ein Handle für einen Gerätekontext angegeben. Wenn ein `CDC`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CDC`-Objekt erstellt und angefügt.|  
|[CDC::GetArcDirection](#getarcdirection)|Gibt den aktuellen Bogen Richtung für den Gerätekontext zurück.|  
|[CDC::GetAspectRatioFilter](#getaspectratiofilter)|Ruft die Einstellung für den aktuellen Seitenverhältnis Filter ab.|  
|[CDC::GetBkColor](#getbkcolor)|Ruft die aktuelle Hintergrundfarbe ab.|  
|[CDC::GetBkMode](#getbkmode)|Ruft das Hintergrund ab.|  
|[CDC::GetBoundsRect](#getboundsrect)|Gibt das aktuelle kumulierte umschließende Rechteck für den angegebenen Gerätekontext zurück.|  
|[CDC::GetBrushOrg](#getbrushorg)|Ruft den Ursprung des aktuellen Pinsels ab.|  
|[CDC::GetCharABCWidths](#getcharabcwidths)|Ruft die Breite in logischen Einheiten von aufeinander folgenden Zeichen in einem angegebenen Bereich aus der aktuellen Schriftart ab.|  
|[CDC::GetCharABCWidthsI](#getcharabcwidthsi)|Ruft die Breite in logischen Einheiten von aufeinander folgenden Glyph-Indizes in einem angegebenen Bereich aus der aktuellen TrueType-Schriftart ab.|  
|[CDC::GetCharacterPlacement](#getcharacterplacement)|Ruft verschiedene Typen von Informationen zu einer Zeichenfolge ab.|  
|[CDC::GetCharWidth](#getcharwidth)|Ruft die hohe Auflösung von aufeinander folgenden Zeichen in einem angegebenen Bereich aus der aktuellen Schriftart ab.|  
|[CDC::GetCharWidthI](#getcharwidthi)|Ruft die Breite in logischen Koordinaten der aufeinander folgenden Glyph-Indizes in einem angegebenen Bereich aus der aktuellen Schriftart ab.|  
|[CDC::GetClipBox](#getclipbox)|Ruft die Dimensionen des tightest umschließenden Rechtecks um den aktuellen Clipping Grenze ab.|  
|[CDC::GetColorAdjustment](#getcoloradjustment)|Ruft die Farbe Anpassungswerte für den Gerätekontext ab.|  
|[CDC::GetCurrentBitmap](#getcurrentbitmap)|Gibt einen Zeiger auf das derzeit ausgewählte `CBitmap` Objekt.|  
|[CDC::GetCurrentBrush](#getcurrentbrush)|Gibt einen Zeiger auf das derzeit ausgewählte `CBrush` Objekt.|  
|[CDC::GetCurrentFont](#getcurrentfont)|Gibt einen Zeiger auf das derzeit ausgewählte `CFont` Objekt.|  
|[CDC::GetCurrentPalette](#getcurrentpalette)|Gibt einen Zeiger auf das derzeit ausgewählte `CPalette` Objekt.|  
|[CDC::GetCurrentPen](#getcurrentpen)|Gibt einen Zeiger auf das derzeit ausgewählte `CPen` Objekt.|  
|[CDC::GetCurrentPosition](#getcurrentposition)|Ruft die aktuelle Position des Stifts (in logischen Koordinaten) ab.|  
|[CDC::GetDCBrushColor](#getdcbrushcolor)|Ruft die aktuelle Pinselfarbe ab.|  
|[CDC::GetDCPenColor](#getdcpencolor)|Ruft die aktuelle Stiftfarbe ab.|  
|[GetDeviceCaps](#getdevicecaps)|Ruft eine angegebene Art von gerätespezifischen Informationen zu einem bestimmten Anzeigegerät Funktionen ab.|  
|[CDC::GetFontData](#getfontdata)|Ruft die Metrik Schriftartinformationen aus einer Datei skalierbare Schriftart ab. Die Informationen abgerufen werden sollen, wird durch Angeben eines Offsets in der Schriftartdatei und die Länge der zurückzugebenden Informationen identifiziert.|  
|[CDC::GetFontLanguageInfo](#getfontlanguageinfo)|Gibt Informationen über die aktuell ausgewählte Schriftart für das angegebene Kontext zurück.|  
|[CDC::GetGlyphOutline](#getglyphoutline)|Ruft die Gliederung Kurve oder eine Bitmap für eine Gliederung Zeichen in der aktuellen Schriftart ab.|  
|[CDC::GetGraphicsMode](#getgraphicsmode)|Ruft den aktuellen Grafikmodus für den angegebenen Gerätekontext.|  
|[CDC::GetHalftoneBrush](#gethalftonebrush)|Ruft einen Pinsel Halbton.|  
|[CDC::GetKerningPairs](#getkerningpairs)|Ruft das Zeichen, kerning-Paare für die Schriftart, die in den angegebenen Gerätekontext markiert ist.|  
|[CDC::GetLayout](#getlayout)|Ruft das Layout für einen Gerätekontext (DC) ab. Das Layout kann werden entweder von links nach rechts (Standard) oder von rechts nach links (gespiegelt).|  
|[CDC::GetMapMode](#getmapmode)|Ruft den aktuellen Zuordnungsmodus ab.|  
|[CDC::GetMiterLimit](#getmiterlimit)|Gibt die Gehrungsgrenze für den Gerätekontext zurück.|  
|[CDC::GetNearestColor](#getnearestcolor)|Ruft die logische nächstgelegene Farbe in der angegebenen logischen Farbe, die das angegebene Gerät darstellen kann.|  
|[CDC::GetOutlineTextMetrics](#getoutlinetextmetrics)|Ruft die Metrik Schriftartinformationen TrueType-Schriftarten.|  
|[CDC::GetOutputCharWidth](#getoutputcharwidth)|Ruft die Breite der einzelnen Zeichen in eine Gruppe aufeinander folgender Zeichen aus der aktuellen Schriftart, die mit der Ausgabe-Gerätekontext ab.|  
|[CDC::GetOutputTabbedTextExtent](#getoutputtabbedtextextent)|Berechnet die Breite und Höhe des Gerätekontexts Ausgabe einer Zeichenfolge.|  
|[CDC::GetOutputTextExtent](#getoutputtextextent)|Berechnet die Breite und Höhe einer Textzeile im Gerätekontext Ausgabe mit der aktuellen Schriftart um die Dimensionen zu ermitteln.|  
|[CDC::GetOutputTextMetrics](#getoutputtextmetrics)|Ruft die Metriken für die aktuelle Schriftart aus der Ausgabe-Gerätekontext ab.|  
|[CDC::getPath](#getpath)|Ruft die Koordinaten definieren die Endpunkte der Linien und die Steuerpunkte der Kurven finden Sie in den Pfad, der in den Gerätekontext ausgewählt ist.|  
|[CDC::getPixel](#getpixel)|Ruft den RGB-Farbwert des Pixels an der angegebenen Position ab.|  
|[CDC::GetPolyFillMode](#getpolyfillmode)|Ruft den aktuellen Polygon Füllmodus ab.|  
|[CDC::GetROP2](#getrop2)|Ruft den Zeichnungsmodus des aktuellen ab.|  
|[CDC::GetSafeHdc](#getsafehdc)|Gibt [CDC::m_hDC](#m_hdc), den Ausgabe-Gerätekontext.|  
|[CDC::GetStretchBltMode](#getstretchbltmode)|Ruft den aktuellen Dehnen von Bitmap-Modus ab.|  
|[CDC::GetTabbedTextExtent](#gettabbedtextextent)|Berechnet die Breite und Höhe einer Zeichenfolge auf den Gerätekontext Attribut.|  
|[CDC::GetTextAlign](#gettextalign)|Ruft die Ausrichtung Flags ab.|  
|[CDC::GetTextCharacterExtra](#gettextcharacterextra)|Ruft die aktuelle Einstellung für den Zeichenabstands ab.|  
|[CDC::GetTextColor](#gettextcolor)|Ruft die Textfarbe ab.|  
|[CDC::getTextExtent](#gettextextent)|Berechnet die Breite und Höhe einer Textzeile im Gerätekontext Attribut mit der aktuellen Schriftart um die Dimensionen zu ermitteln.|  
|[CDC::GetTextExtentExPointI](#gettextextentexpointi)|Ruft die Anzahl der Zeichen in einer angegebenen Zeichenfolge, die in einem angegebenen Bereich passt, und füllt ein Bytearray mit dem Text-Block für jedes dieser Zeichen ab.|  
|[CDC::GetTextExtentPointI](#gettextextentpointi)|Ruft die Breite und Höhe des angegebenen Arrays von Glyph-Indizes.|  
|[CDC::GetTextFace](#gettextface)|Kopiert den Namen der aktuellen Schriftart in einen Puffer als eine auf Null endende Zeichenfolge.|  
|[CDC::GetTextMetrics](#gettextmetrics)|Ruft die Metrik für die aktuelle Schriftart aus dem Gerätekontext Attribut ab.|  
|[CDC::GetViewportExt](#getviewportext)|Ruft die x und y-Blöcke des Viewports ab.|  
|[CDC::GetViewportOrg](#getviewportorg)|Ruft die x- und y-Koordinaten des Ursprungs Viewport ab.|  
|[CDC::GetWindow](#getwindow)|Gibt das Fenster der Anzeige-Gerätekontext zugeordnet.|  
|[CDC::GetWindowExt](#getwindowext)|Ruft die x und y-Blöcke von zugeordnete Fenster ab.|  
|[CDC::GetWindowOrg](#getwindoworg)|Ruft die x- und y-Koordinaten des Ursprungs der das zugeordnete Fenster ab.|  
|[CDC::GetWorldTransform](#getworldtransform)|Ruft den aktuellen World Speicherplatz für Seite-Space-Transformation ab.|  
|[CDC::GradientFill](#gradientfill)|Füllt Rechteck und Dreieck Strukturen mit einer gradating aus.|  
|[CDC:: graystring](#graystring)|Zeichnet abgeblendet (grau) Text an der angegebenen Position.|  
|[CDC::HIMETRICtoDP](#himetrictodp)|Konvertiert **HIMETRIC** Einheiten in Geräteeinheiten.|  
|[CDC::HIMETRICtoLP](#himetrictolp)|Konvertiert **HIMETRIC** Einheiten in logischen Einheiten.|  
|[CDC::IntersectClipRect](#intersectcliprect)|Erstellt einen neuen Ausschneidebereich durch die Schnittmenge des aktuellen Bereichs und ein Rechteck bilden.|  
|[CDC::InvertRect](#invertrect)|Kehrt den Inhalt eines Rechtecks an.|  
|[CDC::InvertRgn](#invertrgn)|Kehrt die Farben in einer Region.|  
|[CDC::IsPrinting](#isprinting)|Bestimmt, ob es sich bei der Gerätekontext für das Drucken verwendet wird.|  
|[CDC::LineTo](#lineto)|Zeichnet eine Linie von der aktuellen Position bis zum, aber nicht einschließlich, einen Punkt.|  
|[CDC::LPtoDP](#lptodp)|Logische Einheiten konvertiert in Geräteeinheiten.|  
|[CDC::LPtoHIMETRIC](#lptohimetric)|Konvertiert die logische Einheiten in **HIMETRIC** Einheiten.|  
|[CDC::MaskBlt](#maskblt)|Kombiniert die Farbdaten für die Quell- und Ziel-Bitmaps, die unter Verwendung der angegebenen Maske und Raster des Vorgangs.|  
|[CDC::ModifyWorldTransform](#modifyworldtransform)|Ändert die globale Transformation für einen Gerätekontext, der mit dem angegebenen Modus.|  
|[CDC::MoveTo](#moveto)|Verschiebt die aktuelle Position.|  
|[CDC::OffsetClipRgn](#offsetcliprgn)|Verschiebt den Ausschneidebereich für das angegebene Gerät.|  
|[CDC::OffsetViewportOrg](#offsetviewportorg)|Ändert den Ursprung des Ausschnitts relativ zu den Koordinaten des Ursprungs des aktuellen Viewports an.|  
|[CDC::OffsetWindowOrg](#offsetwindoworg)|Ändert den Fensterursprung relativ zu den Koordinaten des Ursprungs des aktuellen Fensters.|  
|[CDC::PaintRgn](#paintrgn)|Füllt einen Bereich mit den ausgewählten Pinsel aus.|  
|[CDC::PatBlt](#patblt)|Erstellt ein Bitmuster.|  
|[CDC::PIE](#pie)|Zeichnet einen kreisförmigen Keil.|  
|[CDC::PlayMetaFile](#playmetafile)|Gibt den Inhalt der angegebenen Metadatei das angegebene Gerät. Die erweiterte Version des `PlayMetaFile` zeigt das Bild in der angegebenen EMF-Datei gespeichert. Die Metadatei kann oft wiedergegeben werden.|  
|[CDC::PlgBlt](#plgblt)|Führt einen Bitblocktransfer der Farbdaten-Bits auf das angegebene Rechteck in den Quellgerätekontext an der angegebenen Parallelogramm unter den angegebenen Gerätekontext.|  
|[CDC::PolyBezier](#polybezier)|Zeichnet eine oder mehrere Bzier Splines. Die aktuelle Position ist weder verwendet noch aktualisiert.|  
|[CDC::PolyBezierTo](#polybezierto)|Zeichnet eine oder mehrere Bzier Splines, und die aktuelle Position bis zum Endpunkt des letzten Bzier Splines bewegt.|  
|[CDC::PolyDraw](#polydraw)|Zeichnet eine Reihe von Liniensegmenten und Bzier Splines. Diese Funktion aktualisiert die aktuelle Position.|  
|[CDC::Polygon](#polygon)|Zeichnet ein Vieleck, bestehend aus zwei oder mehr Punkten (Scheitelpunkte) durch Linien verbunden sind.|  
|[CDC::Polyline](#polyline)|Zeichnet eine Reihe von Liniensegmenten, die zwischen den angegebenen Punkten.|  
|[CDC::PolylineTo](#polylineto)|Zeichnet eine oder mehrere gerade Linien und verschiebt die aktuelle Position zum Endpunkt der letzten Zeile.|  
|[CDC::PolyPolygon](#polypolygon)|Erstellt zwei oder mehreren Polygonen, die mit den aktuellen Polygon Füllmodus aufgefüllt werden. Die Polygone können sein, oder möglicherweise überlappen.|  
|[CDC::PolyPolyline](#polypolyline)|Zeichnet mehrere Reihe verbundener Liniensegmente. Die aktuelle Position ist weder verwendet noch von dieser Funktion aktualisiert.|  
|[CDC::PtVisible](#ptvisible)|Gibt an, ob der angegebene Punkt innerhalb des Clippingbereichs.|  
|[CDC::RealizePalette](#realizepalette)|Ordnet Paletteneinträge in der aktuellen logischen Palette der Systempalette.|  
|[CDC::Rectangle](#rectangle)|Zeichnet ein Rechteck mit dem aktuellen Stift, und mit dem aktuellen Pinsel gefüllt.|  
|[CDC::RectVisible](#rectvisible)|Bestimmt, ob der Ausschneidebereich einen beliebigen Teil des angegebenen Rechtecks liegt.|  
|[CDC::ReleaseAttribDC](#releaseattribdc)|Versionen `m_hAttribDC`, den Gerätekontext Attribut.|  
|[CDC::ReleaseOutputDC](#releaseoutputdc)|Versionen `m_hDC`, den Ausgabe-Gerätekontext.|  
|[CDC::ResetDC](#resetdc)|Updates der `m_hAttribDC` Gerätekontext.|  
|[CDC::RestoreDC](#restoredc)|Stellt den Gerätekontext in einen früheren Zustand gespeichert, die mit `SaveDC`.|  
|[CDC::RoundRect](#roundrect)|Zeichnet ein Rechteck mit abgerundeten Ecken den aktuellen Stift verwenden und mit dem aktuellen Pinsel gefüllt.|  
|[CDC::SaveDC](#savedc)|Speichert den aktuellen Zustand des Gerätekontexts.|  
|[CDC::ScaleViewportExt](#scaleviewportext)|Ändert das Ausmaß der Viewport relativ zum aktuellen Werte.|  
|[CDC::ScaleWindowExt](#scalewindowext)|Ändert die Blöcke im Fenster relativ zum aktuellen Werte.|  
|[CDC::ScrollDC](#scrolldc)|Führt einen Bildlauf ein Rechtecks mit Bits, horizontal und vertikal.|  
|[CDC::SelectClipPath](#selectclippath)|Wählt den aktuellen Pfad als einen Ausschneidebereich für den Gerätekontext, der neue Region mit alle vorhandenen Ausschneidebereich kombinieren, mit dem angegebenen Modus.|  
|[CDC::SelectClipRgn](#selectcliprgn)|Kombiniert den angegebenen Bereich mit den aktuellen Ausschneidebereich unter Verwendung des angegebenen Modus.|  
|[CDC::SelectObject](#selectobject)|Wählt ein GDI-Zeichnungsobjekt wie z. B. einen Stift.|  
|[CDC::SelectPalette](#selectpalette)|Wählt die logische Palette an.|  
|[CDC::SelectStockObject](#selectstockobject)|Wählt eine der vordefinierten stock Stifte, Pinsel oder Schriftarten, die von Windows bereitgestellt wird.|  
|[CDC:: setabortproc](#setabortproc)|Legt eine vom Programmierer bereitgestellte Rückruffunktion, die Windows aufruft, wenn ein Druckauftrag abgebrochen werden muss.|  
|[CDC::SetArcDirection](#setarcdirection)|Richtung für das Zeichnen für Bogen und Rechteck Funktionen verwendet werden.|  
|[CDC::SetAttribDC](#setattribdc)|Legt `m_hAttribDC`, den Gerätekontext Attribut.|  
|[CDC::SetBkColor](#setbkcolor)|Die aktuelle Hintergrundfarbe festgelegt.|  
|[CDC::SetBkMode](#setbkmode)|Der Hintergrundmodus festgelegt.|  
|[CDC::SetBoundsRect](#setboundsrect)|Steuert die Akkumulation des umschließenden Rechtecks Informationen für den angegebenen Gerätekontext.|  
|[CDC::SetBrushOrg](#setbrushorg)|Gibt den Ursprung für den nächsten Pinsel einen Gerätekontext ausgewählt.|  
|[CDC::SetColorAdjustment](#setcoloradjustment)|Legt die Farbe Anpassungswerte für den Gerätekontext, der mit den angegebenen Werten.|  
|[CDC::SetDCBrushColor](#setdcbrushcolor)|Legt die aktuelle Pinselfarbe.|  
|[CDC::SetDCPenColor](#setdcpencolor)|Legt die aktuelle Stiftfarbe.|  
|[CDC::SetGraphicsMode](#setgraphicsmode)|Legt den aktuellen Grafikmodus für den angegebenen Gerätekontext.|  
|[CDC::SetLayout](#setlayout)|Ändert das Layout für einen Gerätekontext (DC).|  
|[CDC::SetMapMode](#setmapmode)|Legt den Zuordnungsmodus der aktuellen.|  
|[CDC::SetMapperFlags](#setmapperflags)|Ändert den Algorithmus, den Font Mapper verwendet, wenn sie logische Schriftarten physischen Schriftarten zugeordnet wird.|  
|[CDC::SetMiterLimit](#setmiterlimit)|Legt das Limit für die Länge der Gehrung Joins für den Gerätekontext.|  
|[CDC::SetOutputDC](#setoutputdc)|Legt `m_hDC`, den Ausgabe-Gerätekontext.|  
|[CDC::SetPixel](#setpixel)|Legt die Pixel auf den angegebenen Punkt auf der nächsten Näherung der angegebenen Farbe.|  
|[CDC::SetPixelV](#setpixelv)|Legt das Pixel an den angegebenen Koordinaten auf der nächsten Näherung der angegebenen Farbe fest. `SetPixelV`ist schneller als `SetPixel` , da er nicht den Farbwert des Punkts tatsächlich gezeichnet zurückgeben muss.|  
|[CDC::SetPolyFillMode](#setpolyfillmode)|Legt den Modus Polygon füllen.|  
|[CDC::SetROP2](#setrop2)|Legt den aktuellen Zeichnungsmodus fest.|  
|[CDC::SetStretchBltMode](#setstretchbltmode)|Legt den Dehnen von Bitmap-Modus.|  
|[CDC::SetTextAlign](#settextalign)|Legt die Ausrichtung Flags.|  
|[CDC::SetTextCharacterExtra](#settextcharacterextra)|Legt die Menge des Zeichenabstands fest.|  
|[CDC::SetTextColor](#settextcolor)|Legt die Textfarbe fest.|  
|[CDC::SetTextJustification](#settextjustification)|Die Break-Zeichen in einer Zeichenfolge hinzugefügt Leerzeichen.|  
|[CDC::SetViewportExt](#setviewportext)|Legt die x und y-Blöcke des Viewports an.|  
|[CDC::SetViewportOrg](#setviewportorg)|Legt fest, der Ursprung des Ausschnitts.|  
|[CDC::SetWindowExt](#setwindowext)|Legt die x und y-Blöcke im zugehörigen Fenster.|  
|[CDC::SetWindowOrg](#setwindoworg)|Legt den Fensterursprung im des Gerätekontexts.|  
|[CDC::SetWorldTransform](#setworldtransform)|Legt den aktuellen World-Speicherplatz für Seite-Space-Transformation fest.|  
|[CDC::StartDoc](#startdoc)|Informiert den Treiber, den ein neuer Druckauftrag gestartet wird.|  
|[CDC::StartPage](#startpage)|Informiert den Treiber, den eine neue Seite gestartet wird.|  
|[CDC::StretchBlt](#stretchblt)|Verschiebt eine Bitmap aus einem Quellrechteck und das Gerät in ein Zielrechteck, gestreckt oder komprimiert die Bitmap, soweit erforderlich, um den Maßen des Zielrechtecks zu passen.|  
|[CDC::StrokeAndFillPath](#strokeandfillpath)|Schließt alle geöffneten Figuren in einem Pfad, den Umriss des Pfads mit dem aktuellen Stift eintritt und füllt mit dem aktuellen Pinsel inneren.|  
|[CDC::StrokePath](#strokepath)|Rendert den angegebenen Pfad mit dem aktuellen Stift.|  
|[CDC::TabbedTextOut](#tabbedtextout)|Schreibt eine Zeichenfolge an einer angegebenen Position, erweitern Registerkarten für die Werte in einem Array von Tabstopp Positionen.|  
|[TextOut](#textout)|Schreibt eine Zeichenfolge an einer angegebenen Position mit der aktuell ausgewählten Schriftart.|  
|[CDC::TransparentBlt](#transparentblt)|Überträgt einen Bit-Datenblock Farbe aus der angegebenen Quellgerätekontext einen Gerätekontext Ziel zum Rendern einer bestimmten Farbe transparent in die Übertragung.|  
|[CDC::UpdateColors](#updatecolors)|Updates Farben der Clientbereich des Gerätekontexts durch Abgleichen den aktuellen im Clientbereich für die Systempalette auf x-Pixel-Basis.|  
|[CDC::WidenPath](#widenpath)|Definiert den aktuellen Pfad als der Bereich, der gezeichnet werden würde, wenn der Pfad mit dem aktuell ausgewählten im Gerätekontext Stift gezeichnet wurden.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDC::Operator HDC](#operator_hdc)|Ruft das Handle für den Gerätekontext ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDC::m_hAttribDC](#m_hattribdc)|Die Attribut-Gerätekontext verwendete `CDC` Objekt.|  
|[CDC::m_hDC](#m_hdc)|Die Ausgabe-Gerätekontext verwendete `CDC` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Das `CDC` Objekt stellt Memberfunktionen zum Arbeiten mit einem Gerätekontext, z. B. eine Anzeige oder Drucker sowie Mitglieder für die Arbeit mit einer Anzeigekontext Clientbereich eines Fensters.  
  
 Führen Sie alle Zeichnung durch das Element Funktionen von einem `CDC` Objekt. Die Klasse bietet Memberfunktionen für Gerätekontext Vorgänge, arbeiten mit den Zeichentools, typsichere Grafiken Device Interface (GDI)-Objektauswahl und Arbeiten mit Farben und Paletten. Darüber hinaus werden Memberfunktionen für das Abrufen und festlegen Zeichnungsattribute, Zuordnung, die Arbeit mit den Viewport arbeiten mit den Wertebereich Fenster konvertieren Koordinaten, arbeiten mit Bereichen, Zuschneiden, Zeichnen von Linien und Zeichnen von einfachen Formen, Ellipsen und Vielecken. Member-Funktionen werden ebenfalls für das Zeichnen von Text, arbeiten mit Schriftarten, Drucker Escapezeichen verwenden, Bildlauf und Wiedergeben von Metadateien bereitgestellt.  
  
 Verwenden einer `CDC` Objekt, erstellen es und dann seine Memberfunktionen aufrufen, die Windows-Funktionen, mit denen Gerätekontexte für parallele.  
  
> [!NOTE]
>  Unter Windows 95/98 sind alle Bildschirmkoordinaten 16 Bits beschränkt. Daher ein `int` übergeben, um eine `CDC` Member-Funktion muss im Bereich von-32768 bis 32767 liegen.  
  
 Für bestimmte Verwendungszwecke bietet die Microsoft Foundation Class-Bibliothek mehrere Klassen, die von abgeleiteten `CDC` . `CPaintDC`Aufrufe kapselt, `BeginPaint` und `EndPaint`. `CClientDC`verwaltet einen Clientbereich des Fensters zugeordneten Anzeigekontext. `CWindowDC`verwaltet einen Anzeigekontext ein ganzes Fenster, einschließlich Rahmen und Steuerelementen zugeordnet. `CMetaFileDC`Ordnet eine Metadatei einen Gerätekontext.  
  
 `CDC`stellt zwei Memberfunktionen [GetLayout](#getlayout) und [SetLayout](#setlayout), für die Umkehrung des Layouts für einen Gerätekontext, der nicht das Layout in einem Fenster erbt. Solche rechts-nach-links-Ausrichtung ist für Anwendungen für Kulturen, wie z. B. Arabisch oder Hebräisch, in denen das Zeichen Layout nicht die Europäische Norm ist erforderlich.  
  
 `CDC`enthält zwei Gerätekontexte [M_hDC](#m_hdc) und [M_hAttribDC](#m_hattribdc), das bei der Erstellung einer `CDC` -Objekt, beziehen sich auf dem gleichen Gerät. `CDC`leitet alle Ausgabe GDI-Aufrufe an `m_hDC` und die meisten Attribut GDI-Aufrufe von `m_hAttribDC`. (Ein Beispiel für ein Attributaufruf ist `GetTextColor`, während `SetTextColor` ist ein Aufruf der Ausgabe.)  
  
 Beispielsweise verwendet das Framework diese zwei Gerätekontexte implementieren ein `CMetaFileDC` Objekt, die Ausgabe an eine Metadatei beim Lesen von Attributen aus einem physischen Gerät sendet. Die Seitenansicht ist in das Framework auf ähnliche Weise implementiert. Sie können auch die beiden Kontexte in ähnlicher Weise in den anwendungsspezifischen Code verwenden.  
  
 Manchmal Wenn benötigen Sie möglicherweise Text Metrik Informationen aus der `m_hDC` und `m_hAttribDC` Gerätekontexte. Die folgenden Paare von Funktionen bieten diese Funktion:  
  
|M_hAttribDC verwendet|M_hDC verwendet|  
|-----------------------|-----------------|  
|[GetTextExtent](#gettextextent)|[GetOutputTextExtent](#getoutputtextextent)|  
|[GetTabbedTextExtent](#gettabbedtextextent)|[GetOutputTabbedTextExtent](#getoutputtabbedtextextent)|  
|[GetTextMetrics](#gettextmetrics)|[GetOutputTextMetrics](#getoutputtextmetrics)|  
|[GetCharWidth](#getcharwidth)|[GetOutputCharWidth](#getoutputcharwidth)|  
  
 Weitere Informationen zu `CDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-nameabortdoca--cdcabortdoc"></a><a name="abortdoc"></a>CDC::AbortDoc  
 Beendet den aktuellen Auftrag und löscht Sie alles, was die Anwendung an das Gerät, seit dem letzten Aufruf von geschrieben hat der [StartDoc](#startdoc) Member-Funktion.  
  
```  
int AbortDoc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert größer als oder gleich 0, wenn erfolgreich, oder einen negativen Wert, wenn ein Fehler aufgetreten ist. Die folgende Liste enthält allgemeine Fehlerwerte und ihre Bedeutung:  
  
- **SP_ERROR** allgemeiner Fehler.  
  
- **SP_OUTOFDISK** nicht genügend Speicherplatz auf dem Datenträger steht zurzeit zum Spoolen und keinen Speicherplatz mehr zur Verfügung stehen.  
  
- **SP_OUTOFMEMORY** ist nicht genügend Arbeitsspeicher zum Spoolen verfügbar.  
  
- **SP_USERABORT** wurde vom Benutzer beendet des Auftrags über den Druck-Manager.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ersetzt die `ABORTDOC` Druckerescape.  
  
 **AbortDoc** sollte verwendet werden, um Folgendes zu beenden:  
  
-   Druck-Vorgänge, die keine Abort-Funktion mit angeben [SetAbortProc](#setabortproc).  
  
-   Druck-Vorgänge, die ihre erste noch nicht erreicht haben **NEWFRAME** oder **NEXTBAND** Aufruf mit Escapezeichen versehen.  
  
 Wenn eine Anwendung eines Druckfehlers oder einen abgebrochenen Druckvorgang auftritt, darf es nicht versuchen, den Vorgang zu beenden, indem Sie entweder die [EndDoc](#enddoc) oder **AbortDoc** Memberfunktionen der Klasse `CDC`. GDI wird automatisch den Vorgang vor dem Zurückgeben des Fehlerwert beendet.  
  
 Wenn die Anwendung dem Benutzer ermöglichen, den Druckvorgang abbrechen ein Dialogfeld angezeigt wird, müssen sie aufrufen **AbortDoc** vor dem Zerstören des Dialogfelds.  
  
 Druck-Manager verwendet wurde, um den Auftrag zu starten, wird durch Aufrufen **AbortDoc** löscht den gesamten Spool-Auftrag – erhält der Drucker nichts. Wenn der Druck-Manager nicht verwendet wurde, um den Auftrag zu starten, die Daten möglicherweise gesendet wurden an den Drucker vor **AbortDoc** aufgerufen wurde. In diesem Fall der Druckertreiber würde den Drucker (wenn möglich) zurückgesetzt und den Druckauftrag geschlossen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC::StartDoc](#startdoc).  
  
##  <a name="a-nameabortpatha--cdcabortpath"></a><a name="abortpath"></a>CDC::AbortPath  
 Schließt und verwirft alle Pfade in den Gerätekontext.  
  
```  
BOOL AbortPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Befindet sich eine Klammer offenen Pfad in den Gerätekontext, die Pfad Klammer wird geschlossen, und der Pfad wird verworfen. Wenn in den Gerätekontext ein geschlossener Pfad vorhanden ist, wird der Pfad verworfen.  
  
##  <a name="a-nameaddmetafilecommenta--cdcaddmetafilecomment"></a><a name="addmetafilecomment"></a>CDC::AddMetaFileComment  
 Den Kommentar kopiert aus einem Puffer in einer angegebenen EMF-Datei.  
  
```  
BOOL AddMetaFileComment(
    UINT nDataSize,  
    const BYTE* pCommentData);
```  
  
### <a name="parameters"></a>Parameter  
 *nDataSize*  
 Gibt die Länge des Puffers Kommentar, in Bytes.  
  
 *pCommentData*  
 Verweist auf den Puffer, der den Kommentar enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Ein Kommentar kann private Informationen enthalten, z. B. die Quelle des Bilds und das Datum sie erstellt wurde. Ein Kommentar sollte mit einer Anwendungssignatur, gefolgt von den Daten beginnen. Kommentare sollten keine Position-spezifische Daten enthalten. Position-spezifische Daten gibt den Speicherort eines Datensatzes, und es sollte nicht eingeschlossen werden, da eine Metadatei in einem anderen Metadatei eingebettet werden kann. Diese Funktion kann nur mit Metadateien verwendet werden.  
  
##  <a name="a-namealphablenda--cdcalphablend"></a><a name="alphablend"></a>CDC::AlphaBlend  
 Rufen Sie diese Memberfunktion zum Anzeigen von Bitmaps, die transparent oder halbtransparent Pixel haben.  
  
```  
BOOL AlphaBlend(
    int xDest,  
    int yDest,  
    int nDestWidth,  
    int nDestHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nSrcWidth,  
    int nSrcHeight,  
    BLENDFUNCTION blend);
```  
  
### <a name="parameters"></a>Parameter  
 `xDest`  
 Gibt die X-Koordinate, in logischen Einheiten von der linken oberen Ecke des Zielrechtecks.  
  
 `yDest`  
 Gibt die y-Koordinate, in logischen Einheiten von der linken oberen Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Gibt die Breite in logischen Einheiten des Zielrechtecks an.  
  
 `nDestHeight`  
 Gibt die Höhe in logischen Einheiten des Zielrechtecks an.  
  
 `pSrcDC`  
 Ein Zeiger auf den Quellgerätekontext.  
  
 `xSrc`  
 Gibt die X-Koordinate, in logischen Einheiten von der linken oberen Ecke des Quellrechtecks.  
  
 `ySrc`  
 Gibt die y-Koordinate, in logischen Einheiten von der linken oberen Ecke des Quellrechtecks.  
  
 `nSrcWidth`  
 Gibt die Breite in logischen Einheiten des Quellrechtecks an.  
  
 `nSrcHeight`  
 Gibt die Höhe in logischen Einheiten des Quellrechtecks an.  
  
 *in Blend*  
 Gibt eine [BLENDFUNCTION](http://msdn.microsoft.com/library/windows/desktop/dd183393) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
##  <a name="a-nameanglearca--cdcanglearc"></a><a name="anglearc"></a>CDC::AngleArc  
 Zeichnet ein Liniensegment und einen Bogen.  
  
```  
BOOL AngleArc(
    int x,  
    int y,  
    int nRadius,  
    float fStartAngle,  
    float fSweepAngle);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate für den Mittelpunkt des Kreises.  
  
 *y*  
 Gibt die logische y-Koordinate für den Mittelpunkt des Kreises.  
  
 *nRadius*  
 Gibt den Radius des Kreises in logischen Einheiten an. Dieser Wert muss positiv sein.  
  
 *fStartAngle*  
 Gibt den Anfangswinkel in Grad relativ zur x-Achse.  
  
 *fSweepAngle*  
 Der Pfeilwinkel angibt in Grad relativ zu den Startwinkel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Liniensegment wird von der aktuellen Position an den Anfang des Bogens gezeichnet. Der Bogen wird entlang der Umfang eines Kreises mit dem angegebenen Radius und Center gezeichnet. Die Länge des Bogens wird durch die angegebenen Start- und Sweep Winkel definiert.  
  
 `AngleArc`Verschiebt die aktuelle Position auf dem Endpunkt des Bogens. Der Bogen gezeichnet wird, die von dieser Funktion möglicherweise elliptischen, abhängig von der aktuellen Transformation und Zuordnung. Vor dem Zeichnen des Winkels, zeichnet diese Funktion von der aktuellen Position Liniensegment an den Anfang des Bogens an. Der Bogen wird durch das Erstellen eines imaginären Kreises mit der angegebenen Radius angegebenen Mittelpunkt gezeichnet. Der Anfangspunkt des Bogens wird bestimmt, indem von der x-Achse des Kreises entgegen dem Uhrzeigersinn die Gradzahl im Startwinkel gemessen. Der Endpunkt befindet sich auf ähnliche Weise vom Ausgangspunkt durch die Anzahl der in der Pfeilwinkel Grad gegen den Uhrzeigersinn gemessen.  
  
 Wenn der Pfeilwinkel von 360 Grad übersteigt ist der Bogen mehrmals überflüssig. Diese Funktion zeichnet Linien mit dem aktuellen Stift. In der Abbildung wurde nicht ausgefüllt.  
  
##  <a name="a-namearca--cdcarc"></a><a name="arc"></a>CDC::ARC  
 Zeichnet einen elliptischen Bogen.  
  
```  
BOOL Arc(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL Arc(
    LPCRECT lpRect,  
    POINT ptStart,  
    POINT ptEnd);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 *x3*  
 Gibt an, dass die X-Koordinate des Punktes, der den Bogen definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `y3`  
 Gibt die y-Koordinate des Punktes, der den Bogen definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `x4`  
 Gibt die X-Koordinate des Punktes, der den Bogen-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `y4`  
 Gibt die y-Koordinate des Punktes, der den Bogen-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `lpRect`  
 Gibt das umschließende Rechteck (in logischen Einheiten). Übergeben Sie entweder ein `LPRECT` oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
 `ptStart`  
 Gibt an, dass die x- und y-Koordinaten des Punkts, der den Bogen definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf den Bogen liegen. Übergeben Sie entweder ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt für diesen Parameter.  
  
 `ptEnd`  
 Gibt die x- und y-Koordinaten des Punkts, der den Bogen-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf den Bogen liegen. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Bogen gezeichnet wird, mithilfe der Funktion ist ein Segment der Ellipse, die durch das angegebene umschließende Rechteck definiert ist.  
  
 Die tatsächliche Anfangspunkt des Bogens ist der Punkt, an dem ein Strahl von der Mitte des umschließenden Rechtecks durch den angegebenen Anfangspunkt die Ellipse schneidet. Der tatsächliche Endpunkt des Bogens ist der Punkt, an dem ein Strahl von der Mitte des umschließenden Rechtecks über den angegebenen Endpunkt Ellipse schneidet. Der Bogen wird gegen den Uhrzeigersinn gezeichnet. Da ein Bogen keine geschlossene Form ist, wird es nicht ausgefüllt. Die Breite und die Höhe des Rechtecks müssen größer als 2 Einheiten und weniger als 32.767 Einheiten sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#29;](../../mfc/codesnippet/cpp/cdc-class_1.cpp)]  
  
##  <a name="a-namearctoa--cdcarcto"></a><a name="arcto"></a>CDC::ArcTo  
 Zeichnet einen elliptischen Bogen.  
  
```  
BOOL ArcTo(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL ArcTo(
    LPCRECT lpRect,  
    POINT ptStart,  
    POINT ptEnd);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 *x3*  
 Gibt an, dass die X-Koordinate des Punktes, der den Bogen definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `y3`  
 Gibt die y-Koordinate des Punktes, der den Bogen definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `x4`  
 Gibt die X-Koordinate des Punktes, der den Bogen-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `y4`  
 Gibt die y-Koordinate des Punktes, der den Bogen-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `lpRect`  
 Gibt das umschließende Rechteck (in logischen Einheiten). Sie können entweder einen Zeiger zu übergeben einer [RECT](../../mfc/reference/rect-structure1.md) Datenstruktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
 `ptStart`  
 Gibt an, dass die x- und y-Koordinaten des Punkts, der den Bogen definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf den Bogen liegen. Übergeben Sie entweder ein [Punkt](../../mfc/reference/point-structure1.md) Datenstruktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt für diesen Parameter.  
  
 `ptEnd`  
 Gibt die x- und y-Koordinaten des Punkts, der den Bogen-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf den Bogen liegen. Übergeben Sie entweder ein **Punkt** Datenstruktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist vergleichbar mit `CDC::Arc`, außer dass die aktuelle Position aktualisiert wird. Die Punkte ( `x1`, `y1`) und ( `x2`, `y2`) geben das umschließende Rechteck. Eine Ellipse, die durch das angegebene umschließende Rechteck gebildet wird die Kurve des Bogens definiert. Der Bogen erweitert (die Richtung der Standard-Bogen) gegen den Uhrzeigersinn ab dem Punkt, an dem sie die radiale Linie von der Mitte des umschließenden Rechtecks, schneidet ( *X3*, `y3`). Der Bogen enden, an dem sie die radiale Linie von der Mitte des umschließenden Rechtecks, schneidet ( `x4`, `y4`). Wenn Sie den Anfangs- und Endpunkt identisch sind, wird eine vollständige Ellipse gezeichnet.  
  
 Eine Linie wird von der aktuellen Position mit dem Anfangspunkt des Bogens gezeichnet. Wenn kein Fehler auftritt, wird die aktuelle Position bis zum Endpunkt des Bogens festgelegt. Der Bogen wird mit dem aktuellen Stift gezeichnet. Es wird nicht ausgefüllt.  
  
##  <a name="a-nameattacha--cdcattach"></a><a name="attach"></a>CDC::Attach  
 Mithilfe dieser Memberfunktion an einer `hDC` an die `CDC` Objekt.  
  
```  
BOOL Attach(HDC hDC);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Einen Windows-Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die `hDC` befindet sich in beide `m_hDC`, den Gerätekontext Ausgabe und `m_hAttribDC`, den Gerätekontext Attribut.  
  
##  <a name="a-namebeginpatha--cdcbeginpath"></a><a name="beginpath"></a>CDC:: beginpath  
 Öffnet eine Klammer Pfad im Device Context.  
  
```  
BOOL BeginPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Nachdem eine Klammer Pfad geöffnet ist, kann eine Anwendung Aufrufen der GDI-Zeichenbefehle Funktionen zum Definieren der gelegene Punkte im Pfad beginnen. Eine Anwendung kann eine Klammer offenen Pfad schließen, durch Aufrufen der `EndPath` Member-Funktion. Wenn eine Anwendung ruft `BeginPath`, alle vorherigen Pfade werden verworfen.  
  
 Finden Sie unter [BeginPath](http://msdn.microsoft.com/library/windows/desktop/dd183363) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der Funktionen zum Zeichnen, die Punkte in einem Pfad zu definieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#30;](../../mfc/codesnippet/cpp/cdc-class_2.cpp)]  
  
##  <a name="a-namebitblta--cdcbitblt"></a><a name="bitblt"></a>CDC::BitBlt  
 Kopiert eine Bitmap aus dem Quell-Gerätekontext zum aktuellen Gerätekontext.  
  
```  
BOOL BitBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 *y*  
 Gibt die logische y-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 `nWidth`  
 Gibt die Breite der Bitmap für die Ziel-Rechteck und Quelle (in logischen Einheiten).  
  
 `nHeight`  
 Gibt die Höhe der Bitmap für die Ziel-Rechteck und Quelle (in logischen Einheiten).  
  
 `pSrcDC`  
 Zeiger auf ein `CDC` Objekt, das den Gerätekontext identifiziert, von dem die Bitmap kopiert werden. Es muss **NULL** Wenn *DwRop* gibt einen rastervorgang, der nicht mit eine Datenquelle enthält.  
  
 `xSrc`  
 Gibt die logische X-Koordinate der oberen linken Ecke des Quellbitmap.  
  
 `ySrc`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Quellbitmap.  
  
 *dwRop*  
 Gibt das Raster des auszuführenden Vorgangs an. Raster-Operationscodes definieren, wie GDI Farben in Ausgabevorgängen kombiniert, an denen ein aktueller Pinsel, eine mögliche Quellbitmap und eine Zielbitmap beteiligt sind. Finden Sie unter [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der für die Raster-Operationscodes *DwRop* und deren Beschreibung  
  
 Eine vollständige Liste der Raster-Operationscodes, finden Sie unter [zu Rastervorgangscode](http://msdn.microsoft.com/library/windows/desktop/dd162892) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung kann ausrichten, Windows oder Client-Bereichen auf Byte-Grenzen, um sicherzustellen, dass die `BitBlt` erfolgen auf Rechtecke Bytes ausgerichtet. (Legen Sie die **CS_BYTEALIGNWINDOW** oder **CS_BYTEALIGNCLIENT** kennzeichnet, wenn Sie die Fensterklassen registrieren.)  
  
 `BitBlt`Vorgänge auf Rechtecke Bytes ausgerichtet sind wesentlich schneller als `BitBlt` Vorgänge auf Rechtecke, die nicht-Byte-ausgerichtet sind. Wenn Sie die Klasse Formate wie z. B. Byte-Ausrichtung für Ihre eigenen Gerätekontext angeben möchten, müssen Sie eine Fensterklasse registrieren statt auf die Microsoft Foundation Classes durchführen. Verwenden Sie die globale Funktion [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass).  
  
 GDI transformiert `nWidth` und `nHeight`einmal mithilfe der Zielgerätekontext und einmal mit dem Quellgerätekontext. Wenn die resultierende Blöcke nicht übereinstimmen, GDI verwendet Windows `StretchBlt` Funktion komprimiert oder dehnen die Quell-Bitmap nach Bedarf.  
  
 Wenn das Ziel, die Quelle und die musterbitmaps nicht dasselbe Farbformat haben die `BitBlt` -Funktion konvertiert die Quelle und die musterbitmaps entsprechend das Ziel. Die Vordergrund- und Hintergrundfarben des Ziel-Bitmap werden bei der Konvertierung verwendet.  
  
 Wenn die `BitBlt` -Funktion konvertiert eine monochrome Bitmap in Farbe, legt Sie weiße Bits (1), die Hintergrundfarbe und schwarze Bits (0) für die Vordergrundfarbe. Die Vordergrund- und Hintergrundfarben des Zielgerätekontexts werden verwendet. Farbe in Monochrom, konvertieren `BitBlt` legt Pixel, die die Farbe des Hintergrunds weiß übereinstimmen und alle anderen Pixel auf Schwarz. `BitBlt`verwendet die Vordergrund- und Hintergrundfarben des Gerätekontexts Farbe von Farbe in Monochrom zu konvertieren.  
  
 Beachten Sie, die nicht alle Gerätekontexte unterstützen `BitBlt`. Überprüft, ob ein bestimmtes Gerätekontext unterstützt `BitBlt`, verwenden die `GetDeviceCaps` Member-Funktion, und geben Sie die **RASTERCAPS** Index.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC::CreateCompatibleDC](#createcompatibledc).  
  
##  <a name="a-namecdca--cdccdc"></a><a name="cdc"></a>CDC::CDC  
 Erstellt ein `CDC`-Objekt.  
  
```  
CDC();
```  
  
##  <a name="a-namechorda--cdcchord"></a><a name="chord"></a>CDC::Chord  
 Zeichnet ein Band (eine geschlossene begrenzt durch die Schnittmenge einer Ellipse und einem Liniensegment).  
  
```  
BOOL Chord(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL Chord(
    LPCRECT lpRect,  
    POINT ptStart,  
    POINT ptEnd);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt an, dass die X-Koordinate der oberen linken Ecke des Bandes umschließenden Rechtecks (in logischen Einheiten).  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des Bandes umschließenden Rechtecks (in logischen Einheiten).  
  
 `x2`  
 Gibt an, dass die X-Koordinate der unteren rechten Ecke des Bandes umschließenden Rechtecks (in logischen Einheiten).  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des Bandes umschließenden Rechtecks (in logischen Einheiten).  
  
 *x3*  
 Gibt an, dass die X-Koordinate des Punktes, der die Sehne definiert (in logischen Einheiten) Anfangspunkt des.  
  
 `y3`  
 Gibt die y-Koordinate des Punktes, der die Sehne definiert (in logischen Einheiten) Anfangspunkt des.  
  
 `x4`  
 Gibt die X-Koordinate des Punktes, der die Sehne Endpunkt (in logischen Einheiten) definiert.  
  
 `y4`  
 Gibt die y-Koordinate des Punktes, der die Sehne Endpunkt (in logischen Einheiten) definiert.  
  
 `lpRect`  
 Gibt das umschließende Rechteck (in logischen Einheiten). Übergeben Sie entweder ein `LPRECT` oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
 `ptStart`  
 Gibt an, dass die x- und y-Koordinaten des Punkts, der die Sehne definiert (in logischen Einheiten) Anfangspunkt des. Dieser Punkt muss nicht genau auf die Sehne liegen. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
 `ptEnd`  
 Gibt die x- und y-Koordinaten des Punkts, der die Sehne-Endpunkt (in logischen Einheiten) definiert. Dieser Punkt muss nicht genau auf die Sehne liegen. Übergeben Sie entweder ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der ( `x1`, `y1`) und ( `x2`, `y2`) Parameter angeben, der oberen linken und rechten unteren Ecken eines Rechtecks, das die Ellipse, die Teil des Bandes umgebenden. Der ( *X3*, `y3`) und ( `x4`, `y4`) Parameter geben die Endpunkte einer Linie, die die Ellipse überschneidet. Das Band ist mit dem ausgewählten Stift gezeichnet und mithilfe des ausgewählten Pinsels gefüllt.  
  
 In der Abbildung gezeichnet werden, indem Sie die `Chord` Funktion bis zu erweitert, aber umfasst nicht die rechten und unteren Koordinaten. Dies bedeutet, dass die Höhe der Abbildung `y2` – `y1` und die Breite der Abbildung ist `x2` – `x1`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#31;](../../mfc/codesnippet/cpp/cdc-class_3.cpp)]  
  
##  <a name="a-nameclosefigurea--cdcclosefigure"></a><a name="closefigure"></a>CDC::CloseFigure  
 Schließt eine offene Figur in einem Pfad.  
  
```  
BOOL CloseFigure();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion schließt in der Abbildung durch eine Linie von der aktuellen Position und dem ersten Punkt der Abbildung (in der Regel, die durch den letzten Aufruf von angegebenen Punkt der `MoveTo` Member-Funktion) und die Zeilen mithilfe der Linienverbindungsstil verbindet. Wenn eine Abbildung, mithilfe geschlossen wird der `LineTo` Memberfunktion anstelle der `CloseFigure`, Linienenden werden verwendet, um die Ecke, anstatt eine Verknüpfung zu erstellen. `CloseFigure`sollte nur aufgerufen werden, wenn eine Klammer offenen Pfad in den Gerätekontext besteht.  
  
 Abbildung in einem Pfad ist geöffnet, es sei denn, sie mithilfe dieser Funktion explizit geschlossen wird. (Abbildung kann öffnen, selbst wenn der aktuelle Punkt und der Ausgangspunkt der Abbildung identisch sind.) Alle Linien- oder der Pfad nach hinzugefügt `CloseFigure` beginnt eine neue.  
  
##  <a name="a-namecreatecompatibledca--cdccreatecompatibledc"></a><a name="createcompatibledc"></a>CDC::CreateCompatibleDC  
 Erstellt einen Speicher-Gerätekontext, der mit dem angegebenen Gerät kompatibel ist `pDC`.  
  
```  
BOOL CreateCompatibleDC(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger zu einem Gerätekontext. Wenn `pDC` ist **NULL**, erstellt die Funktion einen Speicher-Gerätekontext, der mit dem System kompatibel ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Ein Speicher-Gerätekontext ist ein Speicherblock, der eine Anzeigeoberfläche darstellt. Hiermit können Sie Bilder im Speicher vorbereiten, bevor sie in der tatsächlichen Geräteoberfläche kompatibles Gerät kopiert.  
  
 Wenn ein Speicher-Gerätekontext erstellt wird, wählt GDI automatisch eine monochrome stock 1 x 1-Bitmap für sie. GDI-Ausgabe-Funktionen können mit einem Speicher-Gerätekontext verwendet werden, nur dann, wenn eine Bitmap erstellt und in diesem Kontext ausgewählt wurde.  
  
 Diese Funktion kann nur verwendet werden, kompatible Gerätekontexte für Geräte erstellen, Rasteroperationen zu unterstützen. Finden Sie unter der [CDC::BitBlt](#bitblt) Informationen zu Bit-Block überträgt Gerätekontexte-Memberfunktion. Bestimmt, ob für ein Gerätekontext Rasteroperationen unterstützt, finden Sie unter der **RC_BITBLT** Raster-Funktion in der Memberfunktion `CDC::GetDeviceCaps`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#32;](../../mfc/codesnippet/cpp/cdc-class_4.cpp)]  
  
##  <a name="a-namecreatedca--cdccreatedc"></a><a name="createdc"></a>CDC::CreateDC  
 Erstellt einen Gerätekontext für das angegebene Gerät.  
  
```  
BOOL CreateDC(
    LPCTSTR lpszDriverName,  
    LPCTSTR lpszDeviceName,  
    LPCTSTR lpszOutput,  
    const void* lpInitData);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDriverName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Dateinamen (ohne Erweiterung) des Gerätetreibers (z. B. "EPSON") angibt. Sie können auch übergeben ein `CString` -Objekt für diesen Parameter.  
  
 `lpszDeviceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen des speziellen Geräts unterstützt werden (z. B. "EPSON FX-80") angibt. Die `lpszDeviceName` Parameter wird verwendet, wenn das Modul über mehrere Geräte unterstützt. Sie können auch übergeben ein `CString` -Objekt für diesen Parameter.  
  
 `lpszOutput`  
 Zeigt auf eine auf Null endende Zeichenfolge, die Namen der Datei bzw. das Gerät für das physikalische Ausgabemedium (Datei oder Ausgabe-Port) angibt. Sie können auch übergeben ein `CString` -Objekt für diesen Parameter.  
  
 `lpInitData`  
 Verweist auf eine `DEVMODE` -Struktur, die gerätespezifische Initialisierungsdaten für den Gerätetreiber enthält. Windows **DocumentProperties** Funktion ruft diese Struktur für ein bestimmtes Gerät ausgefüllt. Die `lpInitData` Parameter muss **NULL** , wenn der Gerätetreiber ist die Verwendung die standardinitialisierung (sofern vorhanden), durch den Benutzer über die Systemsteuerung angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Ausgabe. H-Headerdatei ist erforderlich, wenn die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Struktur verwendet wird.  
  
 Gerätenamen diesen Konventionen: ein Enddatum Doppelpunkt (:) wird empfohlen, aber dies ist optional. Windows entfernt die abschließenden Doppelpunkt, damit ein Gerät mit einem Doppelpunkt endet an denselben Port als derselbe Name ohne Doppelpunkt zugeordnet ist. Die Treiber und Anschluss Namen darf keine führende oder nachgestellte Leerzeichen enthalten. GDI-Ausgabefunktionen können mit Informationen Kontexten verwendet werden.  
  
##  <a name="a-namecreateica--cdccreateic"></a><a name="createic"></a>CDC::CreateIC  
 Erstellt einen Informationskontext für das angegebene Gerät.  
  
```  
BOOL CreateIC(
    LPCTSTR lpszDriverName,  
    LPCTSTR lpszDeviceName,  
    LPCTSTR lpszOutput,  
    const void* lpInitData);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDriverName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Dateinamen (ohne Erweiterung) des Gerätetreibers (z. B. "EPSON") angibt. Sie können übergeben ein `CString` -Objekt für diesen Parameter.  
  
 `lpszDeviceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen des speziellen Geräts unterstützt werden (z. B. "EPSON FX-80") angibt. Die `lpszDeviceName` Parameter wird verwendet, wenn das Modul über mehrere Geräte unterstützt. Sie können übergeben ein `CString` -Objekt für diesen Parameter.  
  
 `lpszOutput`  
 Zeigt auf eine auf Null endende Zeichenfolge, die Namen der Datei bzw. das Gerät für das physikalische Ausgabemedium ("Datei" oder "Port") angibt. Sie können übergeben ein `CString` -Objekt für diesen Parameter.  
  
 `lpInitData`  
 Verweist auf gerätespezifische Initialisierungsdaten für den Gerätetreiber. Die `lpInitData` Parameter muss **NULL** , wenn der Gerätetreiber ist die Verwendung die standardinitialisierung (sofern vorhanden), durch den Benutzer über die Systemsteuerung angegeben. Finden Sie unter `CreateDC` für das Datenformat für die gerätespezifischen Initialisierung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Der Informationskontext bietet eine schnelle Möglichkeit, Informationen über das Gerät zu erhalten, ohne einen Gerätekontext zu erstellen.  
  
 Gerätenamen diesen Konventionen: ein Enddatum Doppelpunkt (:) wird empfohlen, aber dies ist optional. Windows entfernt die abschließenden Doppelpunkt, damit ein Gerät mit einem Doppelpunkt endet an denselben Port als derselbe Name ohne Doppelpunkt zugeordnet ist. Die Treiber und Anschluss Namen darf keine führende oder nachgestellte Leerzeichen enthalten. GDI-Ausgabefunktionen können mit Informationen Kontexten verwendet werden.  
  
##  <a name="a-namedeletedca--cdcdeletedc"></a><a name="deletedc"></a>CDC::DeleteDC  
 In der Regel rufen Sie diese Funktion nicht. der Destruktor wird es für Sie tun.  
  
```  
BOOL DeleteDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `DeleteDC` Memberfunktion löscht die Windows-Gerätekontexte, die zugeordnet `m_hDC` in der aktuellen `CDC` Objekt. Wenn dieses `CDC` -Objekt ist die letzte aktive Gerätekontext für ein bestimmtes Gerät, das Gerät wird benachrichtigt, und alle vom Gerät verwendete Speicher- und Ressourcen werden freigegeben.  
  
 Eine Anwendung sollte nicht aufrufen, `DeleteDC` , wenn Objekte in den Gerätekontext ausgewählt wurde. Objekte müssen zuerst aus den Gerätekontext ausgewählt werden, bevor es gelöscht wird.  
  
 Eine Anwendung muss einen Gerätekontext, dessen Handle durch Aufrufen von abgerufen wurde, nicht gelöscht [CWnd::GetDC](../../mfc/reference/cwnd-class.md#getdc). Stattdessen müssen sie aufrufen [CWnd::ReleaseDC](../../mfc/reference/cwnd-class.md#releasedc) auf den Gerätekontext frei. Die [CClientDC](../../mfc/reference/cclientdc-class.md) und [CWindowDC](../../mfc/reference/cwindowdc-class.md) Klassen werden bereitgestellt, um diese Funktionalität zu umschließen.  
  
 Die `DeleteDC` Funktion wird im Allgemeinen zum Löschen mit erstellten Gerätekontexte [CreateDC](#createdc), [CreateIC](#createic), oder [CreateCompatibleDC](#createcompatibledc).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetPrinterDC](../../mfc/reference/cprintdialog-class.md#getprinterdc).  
  
##  <a name="a-namedeletetempmapa--cdcdeletetempmap"></a><a name="deletetempmap"></a>CDC::DeleteTempMap  
 Automatisch aufgerufen, die `CWinApp` Zeit im Leerlauf-Handler `DeleteTempMap` löscht alle temporären `CDC` von erstellten Objekte `FromHandle`, jedoch nicht die Kontexthandles Gerät gelöscht wird ( `hDC`s) vorübergehend zugeordnet der `CDC` Objekte.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
##  <a name="a-namedetacha--cdcdetach"></a><a name="detach"></a>CDC::Detach  
 Rufen Sie diese Funktion trennen `m_hDC` (Gerätekontext Ausgabe) aus der `CDC` Objekt, und legen Sie beide `m_hDC` und `m_hAttribDC` auf **NULL**.  
  
```  
HDC Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Windows-Gerätekontext.  
  
##  <a name="a-namedptohimetrica--cdcdptohimetric"></a><a name="dptohimetric"></a>CDC::DPtoHIMETRIC  
 Verwenden Sie diese Funktion erhalten Sie, wenn **HIMETRIC** Größen OLE, konvertieren Pixel, um die **HIMETRIC**.  
  
```  
void DPtoHIMETRIC(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpSize`  
 Verweist auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zuordnung der Gerätekontextobjekt ist `MM_LOENGLISH`, `MM_HIENGLISH`, `MM_LOMETRIC`, oder `MM_HIMETRIC`, und klicken Sie dann die Konvertierung auf die Anzahl der Pixel pro Zoll physischen basiert. Wenn der Zuordnungsmodus eines anderen Modus nicht beschränkt ist (z. B. `MM_TEXT`), und klicken Sie dann die Konvertierung auf die Anzahl der Pixel pro Zoll logische basiert.  
  
##  <a name="a-namedptolpa--cdcdptolp"></a><a name="dptolp"></a>CDC::DPtoLP  
 Geräteeinheiten konvertiert in logischen Einheiten.  
  
```  
void DPtoLP(
    LPPOINT lpPoints,  
    int nCount = 1) const;  
  
void DPtoLP(LPRECT lpRect) const;
void DPtoLP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von [Punkt](../../mfc/reference/point-structure1.md) Strukturen oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekte.  
  
 `nCount`  
 Die Anzahl der Punkte im Array.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt. Dieser Parameter wird für einfache Fälle der Konvertierung von einem Rechteck von geräteverwaltungspunkte in logische Punkte verwendet.  
  
 `lpSize`  
 Verweist auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die-Funktion ordnet die Koordinaten für jeden Punkt oder eine Größe von Koordinatensystem des Geräts in logischen Koordinatensystem GDI Dimension. Die Konvertierung hängt von der aktuellen Zuordnungsmodus und die Einstellungen der Ursprünge und Wertebereiche für Fenster und Darstellungsbereich des Geräts ab.  
  
##  <a name="a-namedraw3drecta--cdcdraw3drect"></a><a name="draw3drect"></a>CDC::Draw3dRect  
 Rufen Sie diese Memberfunktion ein dreidimensionales Rechteck.  
  
```  
void Draw3dRect(
    LPCRECT lpRect,  
    COLORREF clrTopLeft,  
    COLORREF clrBottomRight);

 
void Draw3dRect(
    int x,  
    int y,  
    int cx,  
    int cy,  
    COLORREF clrTopLeft,  
    COLORREF clrBottomRight);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Gibt das umschließende Rechteck (in logischen Einheiten). Sie können entweder einen Zeiger zu übergeben einer [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
 *clrTopLeft*  
 Gibt die Farbe von der oberen und linken Rand des dreidimensionalen Rechtecks.  
  
 `clrBottomRight`  
 Gibt die Farbe des unteren und rechten Rand des dreidimensionalen Rechtecks.  
  
 *x*  
 Gibt die logische X-Koordinate der oberen linken Ecke des dreidimensionalen Rechtecks an.  
  
 *y*  
 Gibt die logische y-Koordinate der oberen linken Ecke des dreidimensionalen Rechtecks an.  
  
 CX  
 Gibt die Breite des dreidimensionalen Rechtecks.  
  
 CY  
 Gibt die Höhe des Rechtecks dreidimensionalen.  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck mit der oberen und linken Rand in der angegebenen Farbe gezeichnet werden *ClrTopLeft* und die unteren und rechten Seiten in der angegebenen Farbe `clrBottomRight`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&33;](../../mfc/codesnippet/cpp/cdc-class_5.cpp)]  
  
##  <a name="a-namedrawdragrecta--cdcdrawdragrect"></a><a name="drawdragrect"></a>CDC::DrawDragRect  
 Rufen Sie diese Memberfunktion wiederholt, um einem Rechteck neu zu zeichnen.  
  
```  
void DrawDragRect(
    LPCRECT lpRect,  
    SIZE size,  
    LPCRECT lpRectLast,  
    SIZE sizeLast,  
    CBrush* pBrush = NULL,  
    CBrush* pBrushLast = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die logischen Koordinaten eines Rechtecks gibt – in diesem Fall wird die Endposition des Rechtecks neu gezeichnet wird.  
  
 `size`  
 Gibt die Verschiebung von der oberen linken Ecke des äußeren Rahmens in die linke obere Ecke des den inneren Rahmen (d. h. die Stärke des Rahmens) eines Rechtecks an.  
  
 `lpRectLast`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die logischen Koordinaten der Position eines Rechtecks gibt – in diesem Fall wird die ursprüngliche Position des Rechtecks neu gezeichnet wird.  
  
 *sizeLast*  
 Gibt die Verschiebung von der oberen linken Ecke des äußeren Rahmens der linken oberen Ecke des den inneren Rahmen (d. h. die Stärke des Rahmens) das ursprüngliche Rechteck neu gezeichnet wird.  
  
 `pBrush`  
 Ein Zeiger auf ein Brush-Objekt. Legen Sie auf **NULL** den Standardeinstellung Halbton Pinsel verwenden.  
  
 *pBrushLast*  
 Ein Zeiger auf das letzte Brush-Objekt verwendet. Legen Sie auf **NULL** den Standardeinstellung Halbton Pinsel verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Nennen Sie es in einer Schleife, wie Sie die Position des Mauszeigers, Beispieldaten, um visuelles Feedback anzuzeigen. Beim Aufruf von `DrawDragRect`, des vorherigen Rechtecks wird gelöscht und eine neue gezeichnet wird. Als der Benutzer zieht Sie z. B. ein Rechteck auf dem Bildschirm `DrawDragRect` wird das ursprüngliche Rechteck löschen und neu gezeichnet werden an der neuen Position einen neuen. In der Standardeinstellung `DrawDragRect` zeichnet das Rechteck mit einem Halbton-Pinsel, um Flackern zu vermeiden und die Darstellung eines Rechtecks reibungslos verschieben zu erstellen.  
  
 Beim ersten Aufruf `DrawDragRect`, `lpRectLast` liegen **NULL**.  
  
##  <a name="a-namedrawedgea--cdcdrawedge"></a><a name="drawedge"></a>CDC::DrawEdge  
 Rufen Sie diese Memberfunktion zum Zeichnen der Ränder eines Rechtecks mit dem angegebenen Typ und Stil.  
  
```  
BOOL DrawEdge(
    LPRECT lpRect,  
    UINT nEdge,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Ein Zeiger auf eine **RECT** Struktur, die die logischen Koordinaten des Rechtecks enthält.  
  
 *nEdge*  
 Gibt den Typ des inneren und äußeren Rand gezeichnet. Dieser Parameter muss eine Kombination aus einem inneren Rahmen-Flag und eine äußere Rahmen-Flag sein. Finden Sie unter [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Tabelle mit den Parametertypen verwendet.  
  
 `nFlags`  
 Die Flags, die angeben, den Typ des Rahmens, gezeichnet werden soll. Finden Sie unter `DrawEdge` in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Tabelle, der die Werte des Parameters. Für die diagonalen Linien die **BF_RECT** Flags Geben Sie den Endpunkt des Vektors durch den Rechteckparameter begrenzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namedrawescapea--cdcdrawescape"></a><a name="drawescape"></a>CDC::DrawEscape  
 Greift auf Zeichnen Funktionen einer Videoanzeige, die nicht direkt über die Graphics Device Interface (GDI) verfügbar sind.  
  
```  
int DrawEscape(
    int nEscape,  
    int nInputSize,  
    LPCSTR lpszInputData);
```  
  
### <a name="parameters"></a>Parameter  
 `nEscape`  
 Gibt die Escape-Funktion ausgeführt werden.  
  
 `nInputSize`  
 Gibt die Anzahl der Bytes der Daten, indem Sie auf die `lpszInputData` Parameter.  
  
 `lpszInputData`  
 Verweist auf die Eingabe-Struktur für die angegebene Escape erforderlich.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der Funktion an. Größer als&0; (null), wenn erfolgreich, mit Ausnahme der **QUERYESCSUPPORT** zeichnen Escapezeichen Implementierung nur; oder NULL, wenn der überprüft das Escapezeichen ist nicht implementiert, oder kleiner als NULL, wenn ein Fehler aufgetreten ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung ruft `DrawEscape`, die identifizierten Daten `nInputSize` und `lpszInputData` wird direkt an den angegebenen Anzeigetreiber übergeben.  
  
##  <a name="a-namedrawfocusrecta--cdcdrawfocusrect"></a><a name="drawfocusrect"></a>CDC::DrawFocusRect  
 Zeichnet ein Rechteck in den Stil verwendet, um anzugeben, dass das Rechteck über den Fokus verfügt.  
  
```  
void DrawFocusRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die logischen Koordinaten des Rechtecks gezeichnet werden angibt.  
  
### <a name="remarks"></a>Hinweise  
 Da dies eine booleschen XOR-Funktion ist, wird ein Aufruf dieser Funktion ein zweites Mal mit dem gleichen das Rechteck aus der Anzeige entfernt. Das Rechteck gezeichnet, die von dieser Funktion kann nicht durchgeführt werden. Um einen Bereich mit einem Rechteck gezeichnet, die von dieser Funktion einen Bildlauf durchzuführen, rufen Sie zuerst `DrawFocusRect` um das Rechteck aus der Anzeige zu entfernen, führen Sie den Bereich einen Bildlauf aus, und rufen Sie dann `DrawFocusRect` erneut aus, um das Rechteck in die neue Position.  
  
> [!CAUTION]
> `DrawFocusRect`funktioniert nur in `MM_TEXT` Modus. In anderen Modi diese Funktion zeichnet keine Fokusrechtecks ordnungsgemäß, aber es gibt keinen Fehler zurück.  
  
##  <a name="a-namedrawframecontrola--cdcdrawframecontrol"></a><a name="drawframecontrol"></a>CDC::DrawFrameControl  
 Rufen Sie diese Memberfunktion zum Zeichnen eines Steuerelements Frame mit dem angegebenen Typ und Stil.  
  
```  
BOOL DrawFrameControl(
    LPRECT lpRect,  
    UINT nType,  
    UINT nState);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Ein Zeiger auf eine **RECT** Struktur, die die logischen Koordinaten des Rechtecks enthält.  
  
 `nType`  
 Gibt den Typ der Frame-Steuerelement zu zeichnen. Finden Sie unter der *uType* -Parameter in [DrawFrameControl](http://msdn.microsoft.com/library/windows/desktop/dd162480) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der möglichen Werte für diesen Parameter.  
  
 `nState`  
 Gibt den ursprünglichen Status des Frame-Steuerelement an. Einer oder mehrere Werte beschrieben, für die *uState* -Parameter in `DrawFrameControl` in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Verwenden der `nState` Wert **DFCS_ADJUSTRECT** das umschließende Rechteck zum Ausschließen von des umgebenden Randes der Schaltfläche anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In vielen Fällen `nState` hängt von der `nType` Parameter. Die folgende Liste zeigt die Beziehung zwischen den vier `nType` Werte und `nState`:  
  
- **DFC_BUTTON**  
  
    - **DFCS_BUTTON3STATE** drei-Status-Schaltfläche  
  
    - **DFCS_BUTTONCHECK** Kontrollkästchen  
  
    - **DFCS_BUTTONPUSH** Schaltfläche  
  
    - **DFCS_BUTTONRADIO** Optionsfeld  
  
    - **DFCS_BUTTONRADIOIMAGE** Bild für Optionsfeld (nicht quadratische benötigt Bild)  
  
    - **DFCS_BUTTONRADIOMASK** Maske für Optionsfeld (benötigt Maske nicht quadratische)  
  
- **DFC_CAPTION**  
  
    - **DFCS_CAPTIONCLOSE** Schaltfläche "Schließen"  
  
    - **DFCS_CAPTIONHELP** Schaltfläche "Hilfe"  
  
    - **DFCS_CAPTIONMAX** Maximieren-Schaltfläche  
  
    - **DFCS_CAPTIONMIN** Schaltfläche "Minimieren"  
  
    - **DFCS_CAPTIONRESTORE** "Wiederherstellen"  
  
- **DFC_MENU**  
  
    - **DFCS_MENUARROW** Untermenüpfeil  
  
    - **DFCS_MENUBULLET** Aufzählungszeichen  
  
    - **DFCS_MENUCHECK** Häkchen  
  
- **DFC_SCROLL**  
  
    - **DFCS_SCROLLCOMBOBOX** Kombinationsfeld Feld Bildlaufleiste.  
  
    - **DFCS_SCROLLDOWN** Pfeil Bildlaufleiste.  
  
    - **DFCS_SCROLLLEFT** der Bildlaufleiste nach-links  
  
    - **DFCS_SCROLLRIGHT** der Bildlaufleiste nach-rechts  
  
    - **DFCS_SCROLLSIZEGRIP** Größenziehpunkts in der unteren rechten Ecke des Fensters  
  
    - **DFCS_SCROLLUP** Pfeil der Bildlaufleiste nach oben  
  
### <a name="example"></a>Beispiel  
 Dieser Code zeichnet die Größe Ziehpunkt in der Ecke unten rechts im Fenster. Es eignet sich für die `OnPaint` Ereignishandler von einem Dialogfeld verfügt über keine Formatvorlagen und normalerweise keine andere Steuerelemente (z. B. eine Statusleiste), mit denen sie eine Größe Ziehpunkte erhalten können.  
  
 [!code-cpp[NVC_MFCDocView&#34;](../../mfc/codesnippet/cpp/cdc-class_6.cpp)]  
  
##  <a name="a-namedrawicona--cdcdrawicon"></a><a name="drawicon"></a>CDC::DrawIcon  
 Zeichnet ein Symbol auf dem Gerät, das vom aktuellen `CDC` Objekt.  
  
```  
BOOL DrawIcon(
    int x,  
    int y,  
    HICON hIcon);

 
BOOL DrawIcon(
    POINT point,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate der oberen linken Ecke des Symbols an.  
  
 *y*  
 Gibt die logische y-Koordinate der oberen linken Ecke des Symbols an.  
  
 `hIcon`  
 Gibt das Handle für das Symbol gezeichnet wird.  
  
 `point`  
 Gibt die logische X - und y-Koordinaten von der oberen linken Ecke des Symbols an. Können Sie übergeben ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion setzt die linke obere Ecke das Symbol am angegebenen Speicherort *x* und *y*. Der Speicherort ist abhängig von der aktuellen Zuordnungsmodus des Gerätekontexts.  
  
 Die Symbolressource muss zuvor geladen mithilfe der Funktionen `CWinApp::LoadIcon`, `CWinApp::LoadStandardIcon`, oder `CWinApp::LoadOEMIcon`. Die `MM_TEXT` Zuordnungsmodus muss vor der Verwendung dieser Funktion ausgewählt werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::IsIconic](../../mfc/reference/cwnd-class.md#isiconic).  
  
##  <a name="a-namedrawstatea--cdcdrawstate"></a><a name="drawstate"></a>CDC::DrawState  
 Rufen Sie diese Memberfunktion, um ein Bild anzeigen und einen visuellen Effekt zur Angabe eines Status, z. B. ein deaktiviertes oder Standardstatus zu übernehmen.  
  
> [!NOTE]
>  Für alle `nFlag` Zustände mit Ausnahme von **DSS_NORMAL**, das Bild wird in Monochrom zu konvertiert, bevor Sie der visuelle Effekt angewendet wird.  
  
```  
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    HBITMAP hBitmap,  
    UINT nFlags,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    CBitmap* pBitmap,  
    UINT nFlags,  
    CBrush* pBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    HICON hIcon,  
    UINT nFlags,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    HICON hIcon,  
    UINT nFlags,  
    CBrush* pBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    LPCTSTR lpszText,  
    UINT nFlags,  
    BOOL bPrefixText = TRUE,  
    int nTextLen = 0,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    LPCTSTR lpszText,  
    UINT nFlags,  
    BOOL bPrefixText = TRUE,  
    int nTextLen = 0,  
    CBrush* pBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    DRAWSTATEPROC lpDrawProc,  
    LPARAM lData,  
    UINT nFlags,  
    HBRUSH hBrush = NULL);

 
BOOL DrawState(
    CPoint pt,  
    CSize size,  
    DRAWSTATEPROC lpDrawProc,  
    LPARAM lData,  
    UINT nFlags,  
    CBrush* pBrush = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Gibt den Speicherort des Bilds.  
  
 `size`  
 Gibt die Größe des Bilds.  
  
 `hBitmap`  
 Ein Handle für eine Bitmap.  
  
 `nFlags`  
 Flags, die den Bildtyp und Zustand angeben. Finden Sie unter [DrawState](http://msdn.microsoft.com/library/windows/desktop/dd162496) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für die möglichen `nFlags` Typen und Status.  
  
 `hBrush`  
 Ein Handle für einen Pinsel.  
  
 `pBitmap`  
 Ein Zeiger auf ein CBitmap-Objekt.  
  
 `pBrush`  
 Ein Zeiger auf ein CBrush-Objekt.  
  
 `hIcon`  
 Ein Handle für ein Symbol.  
  
 `lpszText`  
 Ein Zeiger auf den Text.  
  
 *bPrefixText*  
 Text, der möglicherweise eine Zugriffstaste mnemonisches Zeichen enthalten. Die `lData` Parameter gibt die Adresse der Zeichenfolge ist, und die `nTextLen` Parameter gibt die Länge. Wenn `nTextLen` gleich 0 ist, wird angenommen, dass die Zeichenfolge Null-terminiert sein.  
  
 `nTextLen`  
 Länge der Zeichenfolge auf den `lpszText`. Wenn `nTextLen` gleich 0 ist, wird angenommen, dass die Zeichenfolge Null-terminiert sein.  
  
 *lpDrawProc*  
 Ein Zeiger auf eine Callback-Funktion verwendet, um ein Bild zu rendern. Dieser Parameter ist erforderlich, wenn der Bildtyp in `nFlags` ist **DST_COMPLEX**. Es ist optional und kann **NULL** ist der Bildtyp **DST_TEXT**. Für alle anderen Bildtypen wird dieser Parameter ignoriert. Weitere Informationen über die Callback-Funktion finden Sie unter der [DrawStateProc](http://msdn.microsoft.com/library/windows/desktop/dd162497) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lData`  
 Gibt Informationen zu dem Bild. Die Bedeutung dieses Parameters hängt von der Bildtyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namedrawtexta--cdcdrawtext"></a><a name="drawtext"></a>CDC:: DrawText  
 Rufen Sie diese Memberfunktion zum Formatieren von Text im angegebenen Rechteck. Verwenden Sie zum Angeben zusätzlicher Formatierungsoptionen [CDC::DrawTextEx](#drawtextex).  
  
```  
virtual int DrawText(
    LPCTSTR lpszString,  
    int nCount,  
    LPRECT lpRect,  
    UINT nFormat);

 
int DrawText(
    const CString& str,  
    LPRECT lpRect,  
    UINT nFormat);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Verweist auf das zu zeichnende Zeichenfolge. Wenn `nCount` –&1; ist, wird die Zeichenfolge Null-terminiert sein muss.  
  
 `nCount`  
 Gibt die Anzahl der Zeichen in der Zeichenfolge an. Wenn `nCount` –&1; ist, dann ist `lpszString` wird als ein long-Zeiger auf eine auf Null endende Zeichenfolge und `DrawText` berechnet die Anzahl der Zeichen, automatisch.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Rechteck (in logischen Koordinaten) enthält, wird der Text formatiert werden.  
  
 `str`  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den angegebenen Zeichen, gezeichnet werden soll.  
  
 `nFormat`  
 Gibt die Methode den Text zu formatieren. Es kann eine beliebige Kombination der Werte beschrieben, für die `uFormat` -Parameter in [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. (mit dem bitweisen OR-Operator kombinieren Sie:)  
  
> [!NOTE]
>  Einige `uFormat` Flag-Kombinationen können dazu führen, dass die übergebene Zeichenfolge geändert werden. Mithilfe von **DT_MODIFYSTRING** mit **DT_END_ELLIPSIS** oder **DT_PATH_ELLIPSIS** kann dazu führen, dass die Zeichenfolge, die geändert werden, verursacht eine Assertion in der `CString` außer Kraft setzen. Die Werte `DT_CALCRECT`, `DT_EXTERNALLEADING`, **DT_INTERNAL**, `DT_NOCLIP`, und `DT_NOPREFIX` kann nicht verwendet werden, mit der `DT_TABSTOP` Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Texts, wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Es formatiert Text Registerkarten in die entsprechenden Leerzeichen, Ausrichten von Text auf der linken, rechten, oder die Mitte des angegebenen Rechtecks erweitert, und Zerlegen von Text in Zeilen, die in das angegebene Rechteck passt. Die Art der Formatierung wird angegeben, indem `nFormat`.  
  
 Diese Memberfunktion verwendet des Gerätekontexts ausgewählten Schriftart, Textfarbe und Hintergrundfarbe zum Zeichnen des Texts. Es sei denn, die `DT_NOCLIP` Format verwendet wird, `DrawText` schneidet den Text, damit der Text nicht außerhalb des angegebenen Rechtecks angezeigt wird. Die gesamte Formatierung wird davon ausgegangen, dass mehrere Zeilen vorhanden sind, es sei denn, die `DT_SINGLELINE` Format erhält.  
  
 Wenn die ausgewählte Schriftart zu groß für das angegebene Rechteck, ist die `DrawText` Memberfunktion versucht nicht, eine kleinere Schriftart zu ersetzen.  
  
 Wenn die `DT_CALCRECT` Flag angegeben ist, wird anhand des Rechtecks `lpRect` wird die Breite und Höhe, die zum Zeichnen des Texts entsprechend aktualisiert.  
  
 Wenn die **TA_UPDATECP** textausrichtung Flag festgelegt wurde (finden Sie unter [CDC::SetTextAlign](#settextalign)), `DrawText` den Text ab, an der aktuellen Position und nicht auf der linken Seite des angegebenen Rechtecks. `DrawText`Text wird nicht umbrochen bei der **TA_UPDATECP** Flag festgelegt wurde (d. h. die `DT_WORDBREAK` Flag hat keine Auswirkung).  
  
 Die Farbe des Texts kann festgelegt werden, indem [CDC::SetTextColor](#settextcolor).  
  
##  <a name="a-namedrawtextexa--cdcdrawtextex"></a><a name="drawtextex"></a>CDC::DrawTextEx  
 Formatiert den Text im angegebenen Rechteck.  
  
```  
virtual int DrawTextEx(
    LPTSTR lpszString,  
    int nCount,  
    LPRECT lpRect,  
    UINT nFormat,
    LPDRAWTEXTPARAMS lpDTParams);

 
int DrawTextEx(
    const CString& str,  
    LPRECT lpRect,  
    UINT nFormat,
    LPDRAWTEXTPARAMS lpDTParams);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Verweist auf das zu zeichnende Zeichenfolge. Wenn `nCount` –&1; ist, wird die Zeichenfolge Null-terminiert werden muss.  
  
 `nCount`  
 Gibt die Anzahl der Zeichen in der Zeichenfolge an. Wenn `nCount` –&1; ist, dann ist `lpszString` wird als ein long-Zeiger auf eine auf Null endende Zeichenfolge und `DrawText` berechnet die Anzahl der Zeichen, automatisch.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Rechteck (in logischen Koordinaten) enthält, wird der Text formatiert werden.  
  
 `str`  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den angegebenen Zeichen, gezeichnet werden soll.  
  
 `nFormat`  
 Gibt die Methode den Text zu formatieren. Es kann eine beliebige Kombination der Werte beschrieben, für die `uFormat` -Parameter in [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. (Mithilfe des bitweisen kombinieren `OR` Operator):  
  
> [!NOTE]
>  Einige `uFormat` Flag-Kombinationen können dazu führen, dass die übergebene Zeichenfolge geändert werden. Mithilfe von **DT_MODIFYSTRING** mit **DT_END_ELLIPSIS** oder **DT_PATH_ELLIPSIS** kann dazu führen, dass die Zeichenfolge, die geändert werden, verursacht eine Assertion in der `CString` außer Kraft setzen. Die Werte `DT_CALCRECT`, `DT_EXTERNALLEADING`, **DT_INTERNAL**, `DT_NOCLIP`, und `DT_NOPREFIX` kann nicht verwendet werden, mit der `DT_TABSTOP` Wert.  
  
 `lpDTParams`  
 Zeiger auf eine [DRAWTEXTPARAMS](http://msdn.microsoft.com/library/windows/desktop/dd162500) "Optionen"-Struktur, zusätzliche Formatierungsinformationen angibt. Dieser Parameter kann **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Es formatiert Text Registerkarten in die entsprechenden Leerzeichen, Ausrichten von Text auf der linken, rechten, oder die Mitte des angegebenen Rechtecks erweitert, und Zerlegen von Text in Zeilen, die in das angegebene Rechteck passt. Die Art der Formatierung wird angegeben, indem `nFormat` und `lpDTParams`. Weitere Informationen finden Sie unter [CDC:: DrawText](#drawtext) und [DrawTextEx](http://msdn.microsoft.com/library/windows/desktop/dd162499) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Die Farbe des Texts kann festgelegt werden, indem [CDC::SetTextColor](#settextcolor).  
  
##  <a name="a-nameellipsea--cdcellipse"></a><a name="ellipse"></a>CDC::Ellipse  
 Zeichnet eine Ellipse.  
  
```  
BOOL Ellipse(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
BOOL Ellipse(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des umschließenden Rechtecks für die Ellipse an.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des umschließenden Rechtecks für die Ellipse an.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des die Ellipse umschließenden Rechtecks an.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des die Ellipse umschließenden Rechtecks an.  
  
 `lpRect`  
 Gibt an, das die Ellipse umschließenden Rechtecks. Sie können auch übergeben einer [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Mittelpunkt der Ellipse steht im Mittelpunkt des umschließenden Rechtecks, das vom angegebenen `x1`, `y1`, `x2`, und `y2`, oder `lpRect`. Die Ellipse wird mit dem aktuellen Stift gezeichnet und inneren wird mit dem aktuellen Pinsel gefüllt.  
  
 In der Abbildung gezeichnet, die durch diese Funktion bis zu erweitert, aber nicht umfasst, die Rechte und untere Koordinaten. Dies bedeutet, dass die Höhe der Abbildung `y2` – `y1` und die Breite der Abbildung ist `x2` – `x1`.  
  
 Wenn die Breite oder die Höhe des umschließenden Rechtecks 0 ist, wird keine Ellipse gezeichnet.  
  
##  <a name="a-nameenddoca--cdcenddoc"></a><a name="enddoc"></a>CDC::EndDoc  
 Beendet einen Druckauftrag gestartet durch einen Aufruf der [StartDoc](#startdoc) Member-Funktion.  
  
```  
int EndDoc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Größer als oder gleich 0, wenn die Funktion erfolgreich ist, oder einen negativen Wert, wenn ein Fehler aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ersetzt die **ENDDOC** Druckerescape, sofort nach dem Abschluss eines erfolgreichen Druckauftrags aufgerufen werden.  
  
 Wenn eine Anwendung eines Druckfehlers oder einen abgebrochenen Druckvorgang auftritt, darf es nicht versuchen, den Vorgang zu beenden, indem Sie entweder `EndDoc` oder [AbortDoc](#abortdoc). GDI wird automatisch den Vorgang vor dem Zurückgeben des Fehlerwert beendet.  
  
 Diese Funktion sollte nicht in Metadateien verwendet werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC::StartDoc](#startdoc).  
  
##  <a name="a-nameendpagea--cdcendpage"></a><a name="endpage"></a>CDC::EndPage  
 Informiert, dass die Anwendung das Schreiben in eine Seite wurde dem Gerät.  
  
```  
int EndPage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Größer als oder gleich 0, wenn die Funktion erfolgreich ist, oder einen negativen Wert, wenn ein Fehler aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion dient normalerweise zum Weiterleiten des Gerätetreibers auf, um eine neue Seite wechseln.  
  
 Diese Memberfunktion ersetzt die **NEWFRAME** Druckerescape. Im Gegensatz zu **NEWFRAME**, diese Funktion wird immer nach dem Drucken einer Seite aufgerufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC::StartDoc](#startdoc).  
  
##  <a name="a-nameendpatha--cdcendpath"></a><a name="endpath"></a>CDC::EndPath  
 Schließt eine Klammer Pfad, und wählt den Pfad, der die schließende Klammer im Gerätekontext definiert.  
  
```  
BOOL EndPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC:: beginpath](#beginpath).  
  
##  <a name="a-nameenumobjectsa--cdcenumobjects"></a><a name="enumobjects"></a>CDC:: EnumObjects  
 Listet die Stifte und Pinsel in einem Gerätekontext verfügbar.  
  
```  
int EnumObjects(
    int nObjectType,  
    int (CALLBACK* lpfn)(
    LPVOID,
    LPARAM),  
    LPARAM lpData);
```  
  
### <a name="parameters"></a>Parameter  
 *nObjectType*  
 Gibt den Objekttyp an. Sie können die Werte **OBJ_BRUSH** oder **OBJ_PEN**.  
  
 `lpfn`  
 Ist die Adresse der Prozedur-Instanz der Anwendung bereitgestellten Rückruffunktion. Finden Sie im Abschnitt "Hinweise".  
  
 `lpData`  
 Zeigt auf die von der Anwendung bereitgestellten Daten. Die Daten werden an die Callback-Funktion zusammen mit Objektinformationen über das übergeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den letzten Wert zurückgegeben, indem Sie die [Rückruffunktion](../../mfc/reference/callback-function-for-cdc-enumobjects.md). Die Bedeutung ist benutzerdefiniert.  
  
### <a name="remarks"></a>Hinweise  
 Für jedes Objekt eines bestimmten Typs wird die Callback-Funktion, die Sie übergeben mit den Informationen für das Objekt aufgerufen. Das System Ruft die Callback-Funktion, bis keine weiteren Objekte vorhanden sind oder die Callback-Funktion gibt 0 zurück.  
  
 Beachten Sie, dass die neue Funktionen von Microsoft Visual C++ können Sie eine gewöhnliche Funktion zu verwenden, wie die Funktion, die an `EnumObjects`. Die Adresse an übergeben `EnumObjects` ist ein Zeiger auf eine Funktion mit exportierten **EXPORTIEREN** und die Pascal-Aufrufkonvention. Im geschützten Modus Applications müssen Sie keinen kostenlose die Funktion nach der Verwendung mit der FreeProcInstance Windows-Funktion oder erstellen diese Funktion mit der Windows-MakeProcInstance-Funktion.  
  
 Sie auch keinen So exportieren Sie den Namen der Funktion in einer **EXPORTE** -Anweisung in einer Moduldefinitionsdatei für Ihre Anwendung. Stattdessen können Sie die **EXPORTIEREN** Modifizierer als in-Funktion  
  
 **Int-RÜCKRUF EXPORTIEREN** AFunction **(LPSTR**, **LPSTR);**  
  
 um den Compiler an, den richtigen Datensatz für den Export nach Namen ohne Aliasing ausgeben zu verursachen. Dies funktioniert für die meisten Anforderungen. Für einige Sonderfälle, z. B. eine Funktion nach Ordnungszahl oder Aliasing exportieren exportieren, Sie noch benötigen eine **EXPORTE** -Anweisung in einer DEF-Datei.  
  
 Zum Kompilieren von Programmen für Microsoft Foundation, verwenden Sie normalerweise die/GA und /GEs-Compileroptionen. Die Compileroption "/ GW" ist nicht mit der Microsoft Foundation Classes verwendet. (Wenn Sie die Windows-Funktion verwenden **MakeProcInstance**, Sie müssen explizit über den zurückgegebenen Funktionszeiger umgewandelt **FARPROC** in den Typ, der in dieser API erforderlich.) Registrierung Rückrufschnittstellen sind jetzt als typsicherer (Sie müssen in einen Funktionszeiger, der auf die richtige Art von Funktion für den bestimmten Rückruf zeigt übergeben).  
  
 Beachten Sie außerdem, dass alle Rückruffunktionen vor der Rückgabe auf Windows, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht Microsoft Foundation-Ausnahmen abfangen müssen. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#35;](../../mfc/codesnippet/cpp/cdc-class_7.cpp)]  
  
##  <a name="a-nameescapea--cdcescape"></a><a name="escape"></a>CDC::Escape  
 Diese Memberfunktion ist praktisch für Win32-Programmierung veraltet.  
  
```  
virtual int Escape(
    int nEscape,  
    int nCount,  
    LPCSTR lpszInData,  
    LPVOID lpOutData);

 
int Escape(
    int nEscape,  
    int nInputSize,  
    LPCSTR lpszInputData,  
    int nOutputSize,  
    LPSTR lpszOutputData);
```  
  
### <a name="parameters"></a>Parameter  
 `nEscape`  
 Gibt die Escape-Funktion ausgeführt werden.  
  
 Eine vollständige Liste der Escape-Funktionen, finden Sie unter [Escape](http://msdn.microsoft.com/library/windows/desktop/dd162701) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nCount`  
 Gibt die Anzahl der Bytes der Daten, die auf den `lpszInData`.  
  
 `lpszInData`  
 Verweist auf die Eingabedaten-Struktur, die für diese Escapezeichen erforderlich sind.  
  
 `lpOutData`  
 Verweist auf die Struktur, die aus dieser Escape Ausgabe erhalten. Die `lpOutData` Parameter ist **NULL** , wenn keine Daten zurückgegeben werden.  
  
 `nInputSize`  
 Gibt die Anzahl der Bytes der Daten, indem Sie auf die `lpszInputData` Parameter.  
  
 `lpszInputData`  
 Verweist auf die Eingabe-Struktur für die angegebene Escape erforderlich.  
  
 `nOutputSize`  
 Gibt die Anzahl der Bytes der Daten, indem Sie auf die `lpszOutputData` Parameter.  
  
 `lpszOutputData`  
 Verweist auf die Struktur, die Ausgabe von dieser Escape empfängt. Dieser Parameter sollte sein **NULL** , wenn keine Daten zurückgegeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein positiver Wert wird zurückgegeben, wenn die Funktion erfolgreich ist, mit Ausnahme der **QUERYESCSUPPORT** Escapesequenz, die nur für die Implementierung überprüft. 0 (null) wird zurückgegeben, wenn das Escapezeichen nicht implementiert ist. Ein negativer Wert wird zurückgegeben, wenn ein Fehler aufgetreten. Im folgenden sind häufige Fehler:  
  
- **SP_ERROR** allgemeiner Fehler.  
  
- **SP_OUTOFDISK** nicht genügend Speicherplatz auf dem Datenträger steht zurzeit zum Spoolen und keinen Speicherplatz mehr zur Verfügung stehen.  
  
- **SP_OUTOFMEMORY** ist nicht genügend Arbeitsspeicher zum Spoolen verfügbar.  
  
- **SP_USERABORT** Benutzer beendet den Auftrag über den Druck-Manager.  
  
### <a name="remarks"></a>Hinweise  
 Von der ursprünglichen Drucker versieht, nur **QUERYESCSUPPORT** wird für die Win32-Anwendung unterstützt. Alle Drucker-Escapesequenzen sind veraltet und werden nur für Kompatibilität mit 16-Bit-Anwendung unterstützt.  
  
 Für die Win32-Programmierung `CDC` bietet jetzt sechs Memberfunktionen, die die entsprechenden Drucker Escapezeichen zu ersetzen:  
  
- [CDC::AbortDoc](#abortdoc)  
  
- [CDC::EndDoc](#enddoc)  
  
- [CDC::EndPage](#endpage)  
  
- [CDC:: setabortproc](#setabortproc)  
  
- [CDC::StartDoc](#startdoc)  
  
- [CDC::StartPage](#startpage)  
  
 Darüber hinaus [GetDeviceCaps](#getdevicecaps) unterstützt Win32-Indizes, die andere Drucker Escapezeichen ablösen. Finden Sie unter [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
 Diese Memberfunktion Funktionen eines bestimmten Geräts den Zugriff auf ermöglicht, die nicht direkt über GDI verfügbar sind.  
  
 Verwenden Sie die erste Version, wenn die Anwendung vordefinierte Escape-Werte verwendet. Verwenden Sie die zweite Version, wenn Ihre Anwendung privat Escape-Werte definiert. Finden Sie unter [ExtEscape](http://msdn.microsoft.com/library/windows/desktop/dd162708) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen über die zweite Version.  
  
##  <a name="a-nameexcludecliprecta--cdcexcludecliprect"></a><a name="excludecliprect"></a>CDC::ExcludeClipRect  
 Erstellt einen neuen Ausschneidebereich, der aus den vorhandenen Ausschneidebereich abzüglich des angegebenen Rechtecks besteht.  
  
```  
int ExcludeClipRect(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
int ExcludeClipRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des Rechtecks.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Rechtecks.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des Rechtecks.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des Rechtecks.  
  
 `lpRect`  
 Gibt das Rechteck. Kann auch ein `CRect` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den neuen Ausschneidebereich-Typ. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** der Bereich hat Ränder überlappen.  
  
- **Fehler** wurde keine Region erstellt.  
  
- **NULLREGION** die Region ist leer.  
  
- **SIMPLEREGION** die Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die Breite des Rechtecks um den absoluten Wert des angegebenen `x2` – `x1`, darf maximal 32.767 Einheiten. Dieser Grenzwert gilt für die Höhe des Rechtecks sowie.  
  
##  <a name="a-nameexcludeupdatergna--cdcexcludeupdatergn"></a><a name="excludeupdatergn"></a>CDC::ExcludeUpdateRgn  
 Zeichnen in ungültigen Bereichen eines Fensters einen aktualisierten Bereich im Fenster der zugeordneten Ausschneidebereich ausgeschlossen verhindert die `CDC` Objekt.  
  
```  
int ExcludeUpdateRgn(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Window-Objekt, dessen Fenster aktualisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ der ausgeschlossenen Region. Einer der folgenden Werte sind möglich:  
  
- **COMPLEXREGION** der Bereich hat Ränder überlappen.  
  
- **Fehler** wurde keine Region erstellt.  
  
- **NULLREGION** die Region ist leer.  
  
- **SIMPLEREGION** die Region besitzt keine überlappenden Rahmen.  
  
##  <a name="a-nameextfloodfilla--cdcextfloodfill"></a><a name="extfloodfill"></a>CDC::ExtFloodFill  
 Füllt einen Bereich der Anzeigeoberfläche mit dem aktuellen Pinsel.  
  
```  
BOOL ExtFloodFill(
    int x,  
    int y,  
    COLORREF crColor,  
    UINT nFillType);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Punkts füllen beginnt.  
  
 *y*  
 Gibt die logische y-Koordinate des Punkts füllen beginnt.  
  
 `crColor`  
 Gibt die Farbe der Begrenzung oder des Bereichs, der ausgefüllt werden. Die Interpretation der `crColor` hängt vom Wert der `nFillType`.  
  
 `nFillType`  
 Gibt den Typ der auszuführenden füllen. Sie müssen einen der folgenden Werte sein:  
  
- **FLOODFILLBORDER** Füllbereichs wird begrenzt durch die Farbe, die durch angegebene `crColor`. Dieses Format ist identisch mit der durchgeführten füllen `FloodFill`.  
  
- **FLOODFILLSURFACE** Füllbereichs wird definiert, indem die Farbe, die durch angegebene `crColor`. Füllen weiterhin nach außen in alle Richtungen, solange die Farbe gefunden wird. Dieses Format eignet sich zum Füllen von Bereichen mit mehrfarbigen Grenzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, wenn das Füllen nicht abgeschlossen werden konnte, wenn der angegebene Punkt der Grenze ist, vom angegebene Farbe `crColor` (Wenn **FLOODFILLBORDER** angefordert wurde), wenn der angegebene Punkt keinen die angegebenen Farbe `crColor` (Wenn **FLOODFILLSURFACE** angefordert wurde), oder wenn der Punkt außerhalb des Clippingbereichs ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion bietet mehr Flexibilität als `FloodFill` , da Sie einen Typ in angeben können `nFillType`.  
  
 Wenn `nFillType` Wert **FLOODFILLBORDER**, wird angenommen, dass der Bereich vollständig durch die Farbe, die durch angegebene umschlossen werden `crColor`. Die Funktion beginnt am angegebenen Punkt *x* und *y* und in alle Richtungen zur Grenze Farbe gefüllt.  
  
 Wenn `nFillType` Wert **FLOODFILLSURFACE**, startet die Funktion am angegebenen Punkt *x* und *y* und weiterhin in alle Richtungen, füllen alle benachbarte Bereiche, die mit der angegebenen Farbe `crColor`.  
  
 Nur die Arbeitsspeicher-Gerätekontexte und Geräte, die Unterstützung für Raster-Technologie unterstützen `ExtFloodFill`. Weitere Informationen finden Sie unter der [GetDeviceCaps](#getdevicecaps) Member-Funktion.  
  
##  <a name="a-nameexttextouta--cdcexttextout"></a><a name="exttextout"></a>CDC::ExtTextOut  
 Rufen Sie diese Memberfunktion zum Schreiben einer Zeichenfolge in einen rechteckigen Bereich mit der aktuell ausgewählten Schriftart.  
  
```  
virtual BOOL ExtTextOut(
    int x,  
    int y,  
    UINT nOptions,  
    LPCRECT lpRect,  
    LPCTSTR lpszString,  
    UINT nCount,  
    LPINT lpDxWidths);

 
BOOL ExtTextOut(
    int x,  
    int y,  
    UINT nOptions,  
    LPCRECT lpRect,  
    const CString& str,  
    LPINT lpDxWidths);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate der Zeichenzelle für das erste Zeichen in der angegebenen Zeichenfolge an.  
  
 *y*  
 Gibt die logische y-Koordinate des oberen Rands Zeichenzelle für das erste Zeichen in der angegebenen Zeichenfolge an.  
  
 `nOptions`  
 Gibt den Typ des Rechtecks. Dieser Parameter kann eine, beide oder keines der folgenden Werte sein:  
  
- **ETO_CLIPPED** gibt an, dass Text in das Rechteck abgeschnitten wird.  
  
- **ETO_OPAQUE** gibt an, dass die aktuelle Hintergrundfarbe ausgefüllt. (Festlegen und Abfragen mit die aktuellen Hintergrundfarbe der [SetBkColor](#setbkcolor) und [GetBkColor](#getbkcolor) Memberfunktionen.)  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die Dimensionen des Rechtecks bestimmt. Dieser Parameter kann **NULL**. Sie können auch übergeben einer [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
 `lpszString`  
 Verweist auf die angegebene Zeichenfolge, gezeichnet werden soll. Sie können auch übergeben einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt für diesen Parameter.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an.  
  
 `lpDxWidths`  
 Zeigt auf ein Array von Werten, die den Abstand zwischen der Ursprung von angrenzenden Zeichenzellen angeben. Beispielsweise `lpDxWidths`[ *ich*] logische Einheiten unterteilen die Ursprünge Zeichenzelle *ich* und Zeichenzelle *ich* + 1. Wenn `lpDxWidths` ist **NULL**, `ExtTextOut` den Standardabstand zwischen Zeichen verwendet.  
  
 `str`  
 Ein `CString` -Objekt, das den angegebenen Zeichen, gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Rechteckige Bereich kann nicht transparenten (ausgefüllt mit der aktuellen Hintergrundfarbe), und einen Ausschneidebereich sein.  
  
 Wenn `nOptions` ist 0 und `lpRect` ist **NULL**, die Funktion schreibt Text in den Gerätekontext, ohne einen rechteckigen Bereich. Standardmäßig wird die aktuelle Position von der Funktion nicht verwendet oder aktualisiert. Wenn eine Anwendung muss die aktuelle Position Aktualisieren beim Aufrufen `ExtTextOut`, kann die Anwendung aufrufen, die `CDC` Memberfunktion [SetTextAlign](#settextalign) mit `nFlags` festgelegt **TA_UPDATECP**. Wenn dieses Flag festgelegt ist, ignoriert Windows *x* und *y* bei nachfolgenden Aufrufen von `ExtTextOut` und verwendet Sie stattdessen die aktuelle Position. Wenn eine Anwendung verwendet **TA_UPDATECP** die aktuelle Position aktualisieren `ExtTextOut` setzt die aktuelle Position am Ende der vorherigen Zeile des Texts oder durch das letzte Element des Arrays auf die angegebene Position `lpDxWidths`, welcher Wert größer ist.  
  
##  <a name="a-namefillpatha--cdcfillpath"></a><a name="fillpath"></a>CDC::FillPath  
 Schließt alle geöffneten Figuren im aktuellen Pfad und den Pfad innere mithilfe des aktuellen Pinsel und Polygon-Füllmodus füllt.  
  
```  
BOOL FillPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem inneren gefüllt ist, wird der Pfad aus dem Gerätekontext verworfen.  
  
##  <a name="a-namefillrecta--cdcfillrect"></a><a name="fillrect"></a>CDC::fillRect  
 Rufen Sie diese Memberfunktion zum Füllen eines angegebenen Rechtecks mit dem angegebenen Pinsel.  
  
```  
void FillRect(
    LPCRECT lpRect,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die den logischen Koordinaten des Rechtecks ausgefüllt werden. Sie können auch übergeben einer [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt für diesen Parameter.  
  
 `pBrush`  
 Identifiziert den Pinsel ab, um das Rechteck zu füllen.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion abgeschlossen wird, einschließlich der linken und oberen Rahmens, aber nicht den rechten und unteren Rahmen aufgefüllt wird.  
  
 Der Pinsel muss entweder mit erstellt werden, die [CBrush](../../mfc/reference/cbrush-class.md) Memberfunktionen [CreateHatchBrush](../../mfc/reference/cbrush-class.md#createhatchbrush), [CreatePatternBrush](../../mfc/reference/cbrush-class.md#createpatternbrush), und [CreateSolidBrush](../../mfc/reference/cbrush-class.md#createsolidbrush), oder abgerufen, indem die `GetStockObject` -Funktion von Windows.  
  
 Wenn das angegebene Rechteck ausgefüllt `FillRect` enthält keine Rechte und untere Seiten des Rechtecks. GDI bis zu füllt ein Rechteck, jedoch keine, die rechte Spalte und unteren Zeile unabhängig von der aktuellen Zuordnungsmodus. `FillRect`Vergleicht die Werte der **oben**, **unten**, **linken**, und **rechten** Mitglieder des angegebenen Rechtecks. Wenn **unten** ist kleiner als oder gleich **oben**, oder wenn **Rechte** ist kleiner als oder gleich **linken**, nicht das Rechteck gezeichnet wird.  
  
 `FillRect`ähnelt dem [CDC::FillSolidRect](#fillsolidrect)jedoch `FillRect` nimmt einen Pinsel und kann daher verwendet werden, um ein Rechteck mit einer Volltonfarbe, einem geditherte Farbe, schraffierten Pinsel oder ein Muster zu füllen. `FillSolidRect`verwendet nur Volltonfarben (angezeigt durch ein **COLORREF** Parameter). `FillRect`in der Regel ist langsamer als `FillSolidRect`.  
  
##  <a name="a-namefillrgna--cdcfillrgn"></a><a name="fillrgn"></a>CDC::FillRgn  
 Füllt den angegebenen Bereich `pRgn` mit dem angegebenen Pinsel `pBrush`.  
  
```  
BOOL FillRgn(
    CRgn* pRgn,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Ein Zeiger auf die Region ausgefüllt werden. Die Koordinaten für den angegebenen Bereich sind in logischen Einheiten angegeben.  
  
 `pBrush`  
 Identifiziert den Pinsel verwendet werden, um den Bereich zu füllen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Pinsel muss entweder mit erstellt werden die `CBrush` Memberfunktionen `CreateHatchBrush`, `CreatePatternBrush`, `CreateSolidBrush`, oder abgerufen werden, indem **GetStockObject**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateRoundRectRgn](../../mfc/reference/crgn-class.md#createroundrectrgn).  
  
##  <a name="a-namefillsolidrecta--cdcfillsolidrect"></a><a name="fillsolidrect"></a>CDC::FillSolidRect  
 Rufen Sie diese Memberfunktion zum angegebene Rechteck mit dem angegebenen Volltonfarbe zu füllen.  
  
```  
void FillSolidRect(
    LPCRECT lpRect,  
    COLORREF clr);

 
void FillSolidRect(
    int x,  
    int y,  
    int cx,  
    int cy,  
    COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Gibt das umschließende Rechteck (in logischen Einheiten). Sie können entweder einen Zeiger zu übergeben einer [RECT](../../mfc/reference/rect-structure1.md) Datenstruktur oder ein `CRect` -Objekt für diesen Parameter.  
  
 `clr`Gibt die Farbe an, die verwendet werden, um das Rechteck zu füllen.  
  
 *x*  
 Gibt die logische X-Koordinate der oberen linken Ecke des Rechtecks.  
  
 *y*  
 Gibt die logische y-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 `cx`  
 Gibt die Breite des Rechtecks.  
  
 `cy`  
 Gibt die Höhe des Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 `FillSolidRect`ähnelt dem [CDC::FillRect](#fillrect)jedoch `FillSolidRect` verwendet nur Volltonfarben (erkennbar der **COLORREF** Parameter), während `FillRect` nimmt einen Pinsel und kann daher verwendet werden, um ein Rechteck mit einer Volltonfarbe, einem geditherte Farbe, schraffierten Pinsel oder ein Muster zu füllen. `FillSolidRect`in der Regel ist schneller als `FillRect`.  
  
> [!NOTE]
>  Beim Aufruf von `FillSolidRect`, die Hintergrundfarbe, der zuvor festgelegt wurde, mit [SetBkColor](#setbkcolor), auf die durch Farbe festgelegt ist `clr`.  
  
##  <a name="a-nameflattenpatha--cdcflattenpath"></a><a name="flattenpath"></a>CDC::FlattenPath  
 Wandelt alle Kurven in den aktuellen Gerätekontext ausgewählten Pfad umwandelt und jede Kurve in eine Sequenz von Zeilen.  
  
```  
BOOL FlattenPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
##  <a name="a-namefloodfilla--cdcfloodfill"></a><a name="floodfill"></a>CDC::FloodFill  
 Füllt einen Bereich der Anzeigeoberfläche mit dem aktuellen Pinsel.  
  
```  
BOOL FloodFill(
    int x,  
    int y,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Punkts füllen beginnt.  
  
 *y*  
 Gibt die logische y-Koordinate des Punkts füllen beginnt.  
  
 `crColor`  
 Gibt die Farbe der Grenze.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 wird zurückgegeben, wenn das Füllen nicht abgeschlossen werden konnte, wurde der angegebene Punkt der angegebenen Randfarbe `crColor`, oder der Punkt befindet sich außerhalb des Clippingbereichs.  
  
### <a name="remarks"></a>Hinweise  
 Der Bereich wird davon ausgegangen, die als umschlossen werden anhand des `crColor`. Die `FloodFill` Funktion beginnt am angegebenen Punkt *x* und *y* und in alle Richtungen zur Grenze Farbe wird fortgesetzt.  
  
 Nur die Arbeitsspeicher-Gerätekontexte und Geräte, die Unterstützung für Raster-Technologie unterstützen die `FloodFill` Member-Funktion. Informationen zu **RC_BITBLT** Funktion finden Sie unter der `GetDeviceCaps` Member-Funktion.  
  
 Die `ExtFloodFill` -Funktion bietet ähnliche Funktionen jedoch größere Flexibilität.  
  
##  <a name="a-nameframerecta--cdcframerect"></a><a name="framerect"></a>CDC:: FrameRect  
 Zeichnet einen Rahmen um das Rechteck mit dem angegebenen `lpRect`.  
  
```  
void FrameRect(
    LPCRECT lpRect,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die logischen Koordinaten von der oberen linken und der unteren rechten Ecke des Rechtecks enthält. Sie können auch übergeben ein `CRect` -Objekt für diesen Parameter.  
  
 `pBrush`  
 Identifiziert den Pinsel für das Rechteck framing verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion verwendet den angegebenen Pinsel zum Zeichnen des Rahmens. Die Breite und Höhe des Rahmens ist immer 1, logische Einheit.  
  
 Wenn des Rechtecks **unten** Koordinate ist kleiner als oder gleich **oben**, oder wenn **Rechte** ist kleiner als oder gleich **linken**, nicht das Rechteck gezeichnet wird.  
  
 Der Rahmen gezeichnet `FrameRect` befindet sich in der gleichen Position wie ein Rahmen gezeichnet, die durch die **Rechteck** Memberfunktion, die mit den Koordinaten (Wenn **Rechteck** verwendet einen Stift, der logischen Einheit wide 1 ist). Das Innere des Rechtecks wird nicht übernommen `FrameRect`.  
  
##  <a name="a-nameframergna--cdcframergn"></a><a name="framergn"></a>CDC::FrameRgn  
 Zeichnet einen Rahmen um den angegebenen Bereich `pRgn` mit dem angegebenen Pinsel `pBrush`.  
  
```  
BOOL FrameRgn(
    CRgn* pRgn,  
    CBrush* pBrush,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Verweist auf das `CRgn` -Objekt, das den Bereich innerhalb eines Rahmens eingeschlossen werden identifiziert. Die Koordinaten für den angegebenen Bereich sind in logischen Einheiten angegeben.  
  
 `pBrush`  
 Verweist auf das `CBrush` -Objekt, das den Pinsel zum Zeichnen des Rahmens zu verwendende identifiziert.  
  
 `nWidth`  
 Gibt die Breite des Rahmens in senkrechter Striche in Geräteeinheiten an.  
  
 `nHeight`  
 Gibt die Höhe des Rahmens in einem horizontalen Pinselstrich in Geräteeinheiten an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CombineRgn](../../mfc/reference/crgn-class.md#combinergn).  
  
##  <a name="a-namefromhandlea--cdcfromhandle"></a><a name="fromhandle"></a>CDC::FromHandle  
 Gibt einen Zeiger auf ein `CDC` Objekt, wenn ein Handle für einen Gerätekontext angegeben.  
  
```  
static CDC* PASCAL FromHandle(HDC hDC);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Enthält ein Handle für einen Windows-Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger kann temporär sein und sollte nicht hinter sofort gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CDC`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CDC`-Objekt erstellt und angefügt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetPrinterDC](../../mfc/reference/cprintdialog-class.md#getprinterdc).  
  
##  <a name="a-namegetarcdirectiona--cdcgetarcdirection"></a><a name="getarcdirection"></a>CDC::GetArcDirection  
 Gibt den aktuellen Bogen Richtung für den Gerätekontext zurück.  
  
```  
int GetArcDirection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle Bogen Richtung an, ob erfolgreich. Es folgen die gültige Rückgabewerte:  
  
- **AD_COUNTERCLOCKWISE** Bögen und Rechtecke, die gegen den Uhrzeigersinn gezeichnet.  
  
- **AD_CLOCKWISE** Bögen und Rechtecke im Uhrzeigersinn gezeichnet.  
  
 Wenn ein Fehler auftritt, ist der Rückgabewert&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Bogen und Rechteck verwenden die Arc-Richtung.  
  
##  <a name="a-namegetaspectratiofiltera--cdcgetaspectratiofilter"></a><a name="getaspectratiofilter"></a>CDC::GetAspectRatioFilter  
 Ruft die Einstellung für den aktuellen Seitenverhältnis Filter ab.  
  
```  
CSize GetAspectRatioFilter() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` -Objekt, das Seitenverhältnis des aktuellen Seitenverhältnis Filters darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Das Seitenverhältnis ist das Verhältnis zwischen Höhe und Breite in Pixel des Geräts gebildet. Informationen zu einem Gerät Seitenverhältnis wird in die Erstellung, Auswahl und Anzeige von Schriftarten verwendet. Windows bietet einen speziellen Filter, der Filter Seitenverhältnis Schriftarten für ein bestimmtes Seitenverhältnis aus allen verfügbaren Schriftarten auswählen. Der Filter verwendet das Seitenverhältnis, angegeben durch die `SetMapperFlags` -Memberfunktion.  
  
##  <a name="a-namegetbkcolora--cdcgetbkcolor"></a><a name="getbkcolor"></a>CDC::GetBkColor  
 Gibt die aktuelle Hintergrundfarbe zurück.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Hintergrundmodus ist **nicht TRANSPARENTEN**, das System die Hintergrundfarbe zum Füllen der Lücken in der formatierten Zeilen, die Lücken zwischen schraffierten Linien Pinsel und den Hintergrund in Zeichenzellen verwendet. Das System verwendet auch die Hintergrundfarbe beim Konvertieren von Bitmaps zwischen Farbe und Schwarzweiß Gerätekontexte.  
  
##  <a name="a-namegetbkmodea--cdcgetbkmode"></a><a name="getbkmode"></a>CDC::GetBkMode  
 Der Hintergrundmodus zurückgegeben.  
  
```  
int GetBkMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den aktuellen Hintergrundmodus, die möglicherweise **nicht TRANSPARENTEN** oder **TRANSPARENT**.  
  
### <a name="remarks"></a>Hinweise  
 Hintergrund definiert, ob das System vorhandene Hintergrundfarben auf die Zeichenoberfläche entfernt vor dem Text, schraffierten Pinsel oder einen Stiftstil, der keiner durchgezogenen Linie zeichnen.  
  
##  <a name="a-namegetboundsrecta--cdcgetboundsrect"></a><a name="getboundsrect"></a>CDC::GetBoundsRect  
 Gibt das aktuelle kumulierte umschließende Rechteck für den angegebenen Gerätekontext zurück.  
  
```  
UINT GetBoundsRect(
    LPRECT lpRectBounds,  
    UINT flags);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRectBounds`  
 Zeigt auf einen Puffer, der den aktuellen umschließenden Rechtecks erhalten. Das Rechteck wird in logischen Koordinaten zurückgegeben.  
  
 `flags`  
 Gibt an, ob das umschließende Rechteck gelöscht werden, nachdem er zurückgegeben wird. Dieser Parameter sollte&0; (null) oder auf den folgenden Wert festgelegt:  
  
- **DCB_RESET** erzwingt das umschließende Rechteck gelöscht werden sollen, nachdem sie zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Status des umschließenden Rechtecks, wenn die Funktion erfolgreich ist. Es kann eine Kombination der folgenden Werte sein:  
  
- **DCB_ACCUMULATE** umschließende Rechteck Ansammlung stattfindet.  
  
- **DCB_RESET** umgebende Rechteck ist leer.  
  
- **DCB_SET** umgebende Rechteck ist nicht leer.  
  
- **DCB_ENABLE** umgebenden Ansammlung ist.  
  
- **DCB_DISABLE** umgebenden Ansammlung ist deaktiviert.  
  
##  <a name="a-namegetbrushorga--cdcgetbrushorg"></a><a name="getbrushorg"></a>CDC::GetBrushOrg  
 Ruft den Ursprung (in Geräteeinheiten) des Pinsels ausgewählten für den Gerätekontext ab.  
  
```  
CPoint GetBrushOrg() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Ursprung des Pinsels (in Geräteeinheiten) als ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Anfängliche Pinsel stammt bei (0,0) des Clientbereichs. Der Rückgabewert gibt diesen Punkt im Geräteeinheiten relativ zum Ursprung des Fensters auf dem desktop.  
  
##  <a name="a-namegetcharacterplacementa--cdcgetcharacterplacement"></a><a name="getcharacterplacement"></a>CDC::GetCharacterPlacement  
 Ruft verschiedene Typen von Informationen zu einer Zeichenfolge ab.  
  
```  
DWORD GetCharacterPlacement(
    LPCTSTR lpString,  
    int nCount,  
    int nMaxExtent,  
    LPGCP_RESULTS lpResults,  
    DWORD dwFlags) const;  
  
DWORD GetCharacterPlacement(
    CString& str,  
    int nMaxExtent,  
    LPGCP_RESULTS lpResults,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpString`  
 Ein Zeiger auf die zu verarbeitende Zeichenfolge.  
  
 `nCount`  
 Gibt die Länge der Zeichenfolge an. Bei der ANSI-Version ist es eine Byteanzahl und bei der Unicode-Funktion ist es eine Wortanzahl. Weitere Informationen finden Sie unter [GetCharacterPlacement](http://msdn.microsoft.com/library/windows/desktop/dd144860\(v=vs.85\).aspx).  
  
 `nMaxExtent`  
 Gibt der maximale Wertbereich (in logischen Einheiten) an, zu dem die Zeichenfolge verarbeitet wird. Zeichen, die diesen Wertbereich bei Verarbeitung überschreiten würden, werden ignoriert. Berechnungen für alle erforderlichen Reihenfolge- oder Glyphenarrays gelten nur für die enthaltenen Zeichen. Dieser Parameter wird nur verwendet, wenn der GCP_MAXEXTENT-Wert im Parameter `dwFlags` angegeben wird. Da die Funktion die Eingabezeichenfolge verarbeitet, wird jedes Zeichen und sein Wertebereich nur dann der Ausgabe, dem Wertebereich und anderen Arrays hinzugefügt, wenn der gesamte Wertebereich das Maximum noch nicht überschritten hat. Bei Erreichen des Limits wird die Verarbeitung beendet.  
  
 lpResults  
 Zeiger auf eine [GCP_Results](http://msdn.microsoft.com/library/windows/desktop/dd144842\(v=vs.85\).aspx) -Struktur, die die Ergebnisse der Funktion empfängt.  
  
 `dwFlags`  
 Gibt das Verarbeiten der Zeichenfolge in die erforderlichen Arrays an. Dieser Parameter kann eine oder mehrere der Werte in der `dwFlags` Teil der [GetCharacterPlacement](http://msdn.microsoft.com/library/windows/desktop/dd144860\(v=vs.85\).aspx) Thema.  
  
 `str`  
 Ein Zeiger auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt zu verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, handelt es sich bei dem Rückgabewert um die Breite und Höhe der Zeichenfolge in logischen Einheiten.  
  
 Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetCharacterPlacement](http://msdn.microsoft.com/library/windows/desktop/dd144860\(v=vs.85\).aspx), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcharabcwidthsa--cdcgetcharabcwidths"></a><a name="getcharabcwidths"></a>CDC::GetCharABCWidths  
 Ruft die Breite der aufeinander folgenden Zeichen in einem angegebenen Bereich aus der aktuellen TrueType-Schriftart ab.  
  
```  
BOOL GetCharABCWidths(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPABC lpabc) const;  
  
BOOL GetCharABCWidths(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPABCFLOAT lpABCF) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nFirstChar`  
 Gibt das erste Zeichen im Bereich von Zeichen aus der aktuellen Schriftart für die Breite der Zeichen zurückgegeben werden.  
  
 `nLastChar`  
 Gibt das letzte Zeichen im Bereich von Zeichen aus der aktuellen Schriftart für die Breite der Zeichen zurückgegeben werden.  
  
 `lpabc`  
 Verweist auf ein Array von [ABC](../../mfc/reference/abc-structure.md) Strukturen, die die breiten Zeichen zu erhalten, wenn die Funktion zurückgibt. Dieses Array muss mindestens so viele **ABC** Strukturen als Zeichen im angegebenen Bereich vorhanden sind die `nFirstChar` und `nLastChar` Parameter.  
  
 *lpABCF*  
 Verweist auf eine von der Anwendung bereitgestellten Puffer mit einem Array von [ABCFLOAT](../../mfc/reference/abcfloat-structure.md) Strukturen für Breite Zeichen zu erhalten, wenn die Funktion zurückgibt. Die Breite, die von dieser Funktion zurückgegebenen sind in der IEEE-Gleitkomma-Format.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Breite in logischen Einheiten zurückgegeben. Diese Funktion ist nur mit TrueType-Schriftarten erfolgreich.  
  
 Die TrueType-Rasterisierungsfunktion bietet Zeichenabstand "ABC", nachdem eine bestimmte Punktgröße ausgewählt wurde. "A" Abstand ist der Abstand, der an der aktuellen Position hinzugefügt wird, bevor Sie das Symbol platzieren. Abstand "B" ist die Breite des schwarzen Teils des Symbols. "C" Abstand wird die aktuelle Position für den Leerraum auf der rechten Seite des Symbols für das Konto hinzugefügt. Der gesamte erweiterte Breite, angegeben durch ein + B + C.  
  
 Wenn die `GetCharABCWidths` Memberfunktion ruft negative "A" oder "C" Breite für ein Zeichen, das das Zeichen enthält, Underhangs oder Überhängen.  
  
 Zum Konvertieren der breiten ABC in Schriftentwurfseinheiten Erstellen einer Anwendung sollte eine Schriftart, deren Höhe (gemäß den Angaben in der **LfHeight** Mitglied der ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur) ist gleich dem Wert in gespeicherten der **NtmSizeEM** Mitglied der [NEWTEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162741) Struktur. (Der Wert der **NtmSizeEM** Member abgerufen werden kann, durch Aufrufen der [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) -Funktion von Windows.)  
  
 Breite ABC das Standardzeichen sind für Zeichen verwendet, die außerhalb des Bereichs der derzeit ausgewählten Schriftart.  
  
 Rufen Sie die Breite der Zeichen in nicht-TrueType-Schriftarten Clientanwendungen verwenden, sollten die [GetCharWidth](http://msdn.microsoft.com/library/windows/desktop/dd144861) Windows-Funktion.  
  
##  <a name="a-namegetcharabcwidthsia--cdcgetcharabcwidthsi"></a><a name="getcharabcwidthsi"></a>CDC::GetCharABCWidthsI  
 Ruft die Breite in logischen Einheiten von aufeinander folgenden Glyph-Indizes in einem angegebenen Bereich aus der aktuellen TrueType-Schriftart ab.  
  
```  
BOOL GetCharABCWidthsI(
    UINT giFirst,  
    UINT cgi,  
    LPWORD pgi,  
    LPABC lpabc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `giFirst`  
 Gibt den ersten Symbolindex in der Gruppe der aufeinanderfolgenden Glyph-Indizes aus der aktuellen Schriftart. Dieser Parameter wird nur verwendet, wenn die `pgi` Parameter ist **NULL**.  
  
 `cgi`  
 Gibt die Anzahl von Glyph-Indizes.  
  
 `pgi`  
 Ein Zeiger auf ein Array mit Glyph-Indizes. Wenn der Wert **NULL**der `giFirst` Parameter wird stattdessen verwendet. Die `cgi` Parameter gibt die Anzahl der Glyph-Indizes im Array.  
  
 `lpabc`  
 Zeiger auf ein Array von [ABC](http://msdn.microsoft.com/library/windows/desktop/dd162454) Strukturen, die die breiten Zeichen empfangen. Dieses Array muss mindestens so viele **ABC** Strukturen als Symbolindizes stehen den `cgi` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetCharABCWidthsI](http://msdn.microsoft.com/library/windows/desktop/dd144859), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcharwidtha--cdcgetcharwidth"></a><a name="getcharwidth"></a>CDC::GetCharWidth  
 Ruft die Breite der einzelnen Zeichen in eine Gruppe aufeinander folgender Zeichen aus der aktuellen Schriftart ab mit `m_hAttribDC`, Eingabegerät Kontext.  
  
```  
BOOL GetCharWidth(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPINT lpBuffer) const;  
  
BOOL GetCharWidth(
    UINT nFirstChar,  
    UINT nLastChar,  
    float* lpFloatBuffer) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nFirstChar`  
 Gibt das erste Zeichen in aufeinander folgende Zeichen in der aktuellen Schriftart.  
  
 `nLastChar`  
 Gibt das letzte Zeichen in aufeinander folgende Zeichen in der aktuellen Schriftart.  
  
 `lpBuffer`  
 Zeigt auf einen Puffer, der die Breitenwerte für aufeinander folgende Zeichen in der aktuellen Schriftart erhalten.  
  
 *lpFloatBuffer*  
 Zeigt auf einen Puffer zum Empfangen der breiten Zeichen. Die zurückgegebenen breiten sind im 32-Bit-IEEE-Gleitkomma-Format. (Die Breiten werden entlang der Grundlinie der Zeichen gemessen.)  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel wenn `nFirstChar` identifiziert den Buchstaben 'a' und `nLastChar` identifiziert dem Buchstaben "Z", die die Funktion übernimmt die Breite der nur aus Kleinbuchstaben bestehen.  
  
 Die Funktion speichert die Werte in den Puffer, der auf `lpBuffer`. Dieser Puffer muss groß genug für alle für die Breite. D. h. muss vorhanden sein mindestens 26 Einträge im Beispiel angegeben.  
  
 Wenn ein Zeichen in der Gruppe aufeinander folgender Zeichen in einer bestimmten Schriftart nicht vorhanden ist, wird den Width-Wert, der das Standardzeichen zugewiesen werden.  
  
##  <a name="a-namegetcharwidthia--cdcgetcharwidthi"></a><a name="getcharwidthi"></a>CDC::GetCharWidthI  
 Ruft die Breite in logischen Koordinaten der aufeinander folgenden Glyph-Indizes in einem angegebenen Bereich aus der aktuellen Schriftart ab.  
  
```  
BOOL GetCharWidthI(
    UINT giFirst,  
    UINT cgi,  
    LPWORD pgi,  
    LPINT lpBuffer) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `giFirst`  
 Gibt den ersten Symbolindex in der Gruppe der aufeinanderfolgenden Glyph-Indizes aus der aktuellen Schriftart. Dieser Parameter wird nur verwendet, wenn die `pgi` Parameter ist **NULL**.  
  
 `cgi`  
 Gibt die Anzahl von Glyph-Indizes.  
  
 `pgi`  
 Ein Zeiger auf ein Array mit Glyph-Indizes. Wenn der Wert **NULL**der `giFirst` Parameter wird stattdessen verwendet. Die `cgi` Parameter gibt die Anzahl der Glyph-Indizes im Array.  
  
 `lpBuffer`  
 Ein Zeiger auf einen Puffer, der die Breite empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetCharWidthI](http://msdn.microsoft.com/library/windows/desktop/dd144864), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetclipboxa--cdcgetclipbox"></a><a name="getclipbox"></a>CDC::GetClipBox  
 Ruft die Dimensionen des tightest umschließenden Rechtecks um den aktuellen Clipping Grenze ab.  
  
```  
virtual int GetClipBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf die [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Dimensionen des Rechtecks zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ausschneidebereich-Typ. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** Ausschneidebereich hat Ränder überlappen.  
  
- **Fehler** Gerätekontext ist ungültig.  
  
- **NULLREGION** Ausschneidebereich ist leer.  
  
- **SIMPLEREGION** Ausschneidebereich besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die Dimensionen werden in den Puffer, die auf kopiert `lpRect`.  
  
##  <a name="a-namegetcoloradjustmenta--cdcgetcoloradjustment"></a><a name="getcoloradjustment"></a>CDC::GetColorAdjustment  
 Ruft die Farbe Anpassungswerte für den Gerätekontext ab.  
  
```  
BOOL GetColorAdjustment(LPCOLORADJUSTMENT lpColorAdjust) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpColorAdjust`  
 Verweist auf eine [COLORADJUSTMENT](../../mfc/reference/coloradjustment-structure.md) -Datenstruktur, die Anpassung Farbwerte empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
##  <a name="a-namegetcurrentbitmapa--cdcgetcurrentbitmap"></a><a name="getcurrentbitmap"></a>CDC::GetCurrentBitmap  
 Gibt einen Zeiger auf das derzeit ausgewählte `CBitmap` Objekt.  
  
```  
CBitmap* GetCurrentBitmap() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CBitmap` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion kann temporäre Objekte zurückgeben.  
  
##  <a name="a-namegetcurrentbrusha--cdcgetcurrentbrush"></a><a name="getcurrentbrush"></a>CDC::GetCurrentBrush  
 Gibt einen Zeiger auf das derzeit ausgewählte `CBrush` Objekt.  
  
```  
CBrush* GetCurrentBrush() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CBrush` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion kann temporäre Objekte zurückgeben.  
  
##  <a name="a-namegetcurrentfonta--cdcgetcurrentfont"></a><a name="getcurrentfont"></a>CDC::GetCurrentFont  
 Gibt einen Zeiger auf das derzeit ausgewählte `CFont` Objekt.  
  
```  
CFont* GetCurrentFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CFont` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion kann temporäre Objekte zurückgeben.  
  
##  <a name="a-namegetcurrentpalettea--cdcgetcurrentpalette"></a><a name="getcurrentpalette"></a>CDC::GetCurrentPalette  
 Gibt einen Zeiger auf das derzeit ausgewählte `CPalette` Objekt.  
  
```  
CPalette* GetCurrentPalette() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CPalette` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion kann temporäre Objekte zurückgeben.  
  
##  <a name="a-namegetcurrentpena--cdcgetcurrentpen"></a><a name="getcurrentpen"></a>CDC::GetCurrentPen  
 Gibt einen Zeiger auf das derzeit ausgewählte `CPen` Objekt.  
  
```  
CPen* GetCurrentPen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CPen` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion kann temporäre Objekte zurückgeben.  
  
##  <a name="a-namegetcurrentpositiona--cdcgetcurrentposition"></a><a name="getcurrentposition"></a>CDC::GetCurrentPosition  
 Ruft die aktuelle Position (in logischen Koordinaten) ab.  
  
```  
CPoint GetCurrentPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Position als ein `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Position kann festgelegt werden, mit der `MoveTo` Member-Funktion.  
  
##  <a name="a-namegetdcbrushcolora--cdcgetdcbrushcolor"></a><a name="getdcbrushcolor"></a>CDC::GetDCBrushColor  
 Ruft die aktuelle Pinselfarbe ab.  
  
```  
COLORREF GetDCBrushColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert der [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert für die aktuelle Pinselfarbe.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert **CLR_INVALID**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetDCBrushColor](http://msdn.microsoft.com/library/windows/desktop/dd144872), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdcpencolora--cdcgetdcpencolor"></a><a name="getdcpencolor"></a>CDC::GetDCPenColor  
 Ruft die aktuelle Stiftfarbe ab.  
  
```  
COLORREF GetDCPenColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert der [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert für die aktuelle Stiftfarbe.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert **CLR_INVALID**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verwendet die Win32-Funktion [GetDCPenColor](http://msdn.microsoft.com/library/windows/desktop/dd144875), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdevicecapsa--cdcgetdevicecaps"></a><a name="getdevicecaps"></a>GetDeviceCaps  
 Ruft eine Vielzahl von gerätespezifischen Informationen anzeigen.  
  
```  
int GetDeviceCaps(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den Typ der zurückzugebenden Informationen. Finden Sie unter [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert für die angeforderte Funktion, wenn die Funktion erfolgreich ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetDefaults](../../mfc/reference/cprintdialog-class.md#getdefaults).  
  
##  <a name="a-namegetfontdataa--cdcgetfontdata"></a><a name="getfontdata"></a>CDC::GetFontData  
 Ruft den Schriftart-Metrik-Informationen aus einer Datei skalierbare Schriftart ab.  
  
```  
DWORD GetFontData(
    DWORD dwTable,  
    DWORD dwOffset,  
    LPVOID lpData,  
    DWORD cbData) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwTable`  
 Gibt den Namen der Metrik Tabelle zurückgegeben werden. Dieser Parameter kann einer der Metriken Tabellen in der TrueType-Schriftartdateien Spezifikation veröffentlicht Microsoft Corporation dokumentiert sein. Wenn dieser Parameter 0 ist, werden die Informationen am Anfang der Schriftartdatei beginnt, abgerufen.  
  
 `dwOffset`  
 Gibt den Offset vom Anfang der Tabelle auf dem Informationen abgerufen werden soll. Wenn dieser Parameter 0 ist, die Informationen abgerufen beginnend am Anfang der Tabelle, angegeben durch die `dwTable` Parameter. Wenn dieser Wert größer als oder gleich der Größe der Tabelle `GetFontData` gibt 0 zurück.  
  
 `lpData`  
 Zeigt auf einen Puffer, der Informationen über den erhalten. Wenn dieser Wert **NULL**, die Funktion gibt die Größe des Puffers für die Schriftartdaten im angegebenen erforderlichen der `dwTable` Parameter.  
  
 `cbData`  
 Gibt die Länge in Bytes, der die Informationen abgerufen werden sollen. Wenn dieser Parameter 0 ist `GetFontData` gibt die Größe der Daten in der `dwTable` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Bytes im Puffer auf den zurückgegebenen `lpData` Wenn die Funktion erfolgreich, andernfalls –&1;.  
  
### <a name="remarks"></a>Hinweise  
 Die Informationen abgerufen werden sollen, wird durch Angeben eines Offsets in der Schriftartdatei und die Länge der zurückzugebenden Informationen identifiziert.  
  
 Eine Anwendung kann auch mithilfe der `GetFontData` Member-Funktion, um eine TrueType-Schriftart mit einem Dokument zu speichern. Zu diesem Zweck die Anwendung bestimmt, ob die Schriftart eingebettet werden kann, und dann die gesamte Schriftartdatei Ruft, Angabe von 0 für die `dwTable`, `dwOffset`, und `cbData` Parameter.  
  
 Clientanwendungen können bestimmen, ob eine Schriftart kann, überprüfen eingebettet werden die **OtmfsType** Mitglied der [OUTLINETEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162755) Struktur. Wenn bit 1 des **OtmfsType** festgelegt ist, Einbetten der Schriftart nicht zulässig ist. Wenn Bit 1 ist, kann die Schriftart eingebettet werden. Wenn Bit 2 festgelegt ist, ist das Einbetten schreibgeschützt.  
  
 Wenn eine Anwendung versucht, diese Funktion verwenden Sie zum Abrufen von Informationen für nicht-TrueType-Schriftarten, die `GetFontData` Memberfunktion gibt-1 zurück.  
  
##  <a name="a-namegetfontlanguageinfoa--cdcgetfontlanguageinfo"></a><a name="getfontlanguageinfo"></a>CDC::GetFontLanguageInfo  
 Gibt Informationen über die aktuell ausgewählte Schriftart für das angegebene Kontext zurück.  
  
```  
DWORD GetFontLanguageInfo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt Eigenschaften der derzeit ausgewählten Schriftart. Eine vollständige Liste der möglichen Werte finden Sie unter [GetFontLanguageInfo](http://msdn.microsoft.com/library/windows/desktop/dd144886).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetFontLanguageInfo](http://msdn.microsoft.com/library/windows/desktop/dd144886), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetglyphoutlinea--cdcgetglyphoutline"></a><a name="getglyphoutline"></a>CDC::GetGlyphOutline  
 Ruft die Gliederung Kurve oder eine Bitmap für eine Gliederung Zeichen in der aktuellen Schriftart ab.  
  
```  
DWORD GetGlyphOutline(
    UINT nChar,  
    UINT nFormat,  
    LPGLYPHMETRICS lpgm,  
    DWORD cbBuffer,  
    LPVOID lpBuffer,  
    const MAT2* lpmat2) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Gibt das Zeichen für das Informationen zurückgegeben werden.  
  
 `nFormat`  
 Gibt das Format, in dem die Funktion zum Zurückgeben von Informationen ist. Einer der folgenden Werte oder 0 sind möglich:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**GGO_BITMAP**|Gibt die Symbolbitmap zurück. Wenn die Funktion zurückgibt, werden die Puffer, die auf `lpBuffer` enthält eine 1-Bit-pro-Pixel-Bitmap, deren Zeilen auf Doppelwort Grenzen zu starten.|  
|**GGO_NATIVE**|Gibt die Kurve Datenpunkte die Rasterisierungsfunktion systemeigene Datenformate mit Geräteeinheiten zurück. Wenn dieser Wert angegeben wird, wird eine Transformation in angegebenen `lpmat2` wird ignoriert.|  
  
 Wenn der Wert der `nFormat` gleich 0 ist, füllt die Funktion ein [GLYPHMETRICS](http://msdn.microsoft.com/library/windows/desktop/dd144955) -Struktur, jedoch keine Glyphe Gliedern von Daten zurückgibt.  
  
 *lpgm*  
 Verweist auf eine **GLYPHMETRICS** Struktur, die die Position des Symbols im Zeichenzelle beschreibt.  
  
 `cbBuffer`  
 Gibt die Größe des Puffers, in dem die Funktion Informationen über die Gliederung Zeichen kopiert. Wenn dieser Wert 0 ist und die `nFormat` Parameter ist entweder der **GGO_BITMAP** oder **GGO_NATIVE** Werte, die Funktion gibt die erforderliche Größe des Puffers zurück.  
  
 `lpBuffer`  
 Zeigt auf einen Puffer, in dem die Funktion Informationen über die Gliederung Zeichen kopiert. Wenn `nFormat` gibt die **GGO_NATIVE** -Wert, der Informationen in Form von kopiert **TTPOLYGONHEADER** und **TTPOLYCURVE** Strukturen. Wenn dieser Wert **NULL** und `nFormat` ist entweder der **GGO_BITMAP** oder **GGO_NATIVE** Wert, gibt die Funktion die erforderliche Größe des Puffers zurück.  
  
 `lpmat2`  
 Verweist auf eine [MAT2](http://msdn.microsoft.com/library/windows/desktop/dd145048) -Struktur, die eine Transformationsmatrix für das Zeichen enthält. Dieser Parameter darf nicht **NULL**, selbst wenn die **GGO_NATIVE** angegebene Wert ist `nFormat`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe in Bytes des Puffers für die abgerufenen Informationen erforderlich, wenn `cbBuffer` 0 oder `lpBuffer` ist **NULL**. Andernfalls ist sie positiv, wenn die Funktion erfolgreich ist oder –&1;, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann im Bitmap-Format abgerufene werden, indem eine 2 x 2-Transformationsmatrix angeben, in der Struktur auf das Zeichen drehen `lpmat2`.  
  
 Eine Gliederung Symbol wird als eine Reihe von Konturen zurückgegeben. Jede Kontur wird definiert, indem ein [TTPOLYGONHEADER](http://msdn.microsoft.com/library/windows/desktop/dd145158) Struktur folgt, so viele **TTPOLYCURVE** Strukturen als erforderlich sind, um es zu beschreiben. Alle Punkte werden zurückgegeben, als [POINTFX](http://msdn.microsoft.com/library/windows/desktop/dd162806) -Strukturen und absolute Positionen, keinen relativen wechselt darstellen. Der Anfangspunkt vom der **PfxStart** Mitglied der [TTPOLYGONHEADER](http://msdn.microsoft.com/library/windows/desktop/dd145158) Struktur ist der Punkt, an dem die Gliederung der Kontur beginnt. Die [TTPOLYCURVE](http://msdn.microsoft.com/library/windows/desktop/dd145157) Strukturen, die folgen kann entweder Polylinie oder Spline-Datensätze. Polyline-Datensätze sind eine Reihe von Punkten. zwischen den Punkten gezeichnete Linien beschreiben die Gliederung des Zeichens. Spline Datensätze repräsentieren die quadratischen Kurven von TrueType (d. h. quadratische b-Splines) verwendet.  
  
##  <a name="a-namegetgraphicsmodea--cdcgetgraphicsmode"></a><a name="getgraphicsmode"></a>CDC::GetGraphicsMode  
 Ruft den aktuellen Grafikmodus für den angegebenen Gerätekontext.  
  
```  
int GetGraphicsMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Grafikmodus bei Erfolg zurück. Eine Liste der Werte, die diese Methode zurückgeben kann, finden Sie unter [GetGraphicsMode](http://msdn.microsoft.com/library/windows/desktop/dd144892).  
  
 Gibt 0 bei einem Fehler zurück.  
  
 Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode umschließt die Windows GDI-Funktion [GetGraphicsMode](http://msdn.microsoft.com/library/windows/desktop/dd144892).  
  
##  <a name="a-namegethalftonebrusha--cdcgethalftonebrush"></a><a name="gethalftonebrush"></a>CDC::GetHalftoneBrush  
 Rufen Sie diese Memberfunktion, um einen Pinsel Halbton abzurufen.  
  
```  
static CBrush* PASCAL GetHalftoneBrush();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CBrush` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Halbton Pinsel zeigt Pixel, die abwechselnd Vordergrund- und Hintergrundfarben Dithering Muster zu erstellen sind. Folgendes ist ein Beispiel für eine Dithering Muster, die von einem Pinsel Halbton erstellt.  
  
 ![Detail eines geditherten Stiftstrichs](../../mfc/reference/media/vc318s1.gif "vc318s1")  
  
##  <a name="a-namegetkerningpairsa--cdcgetkerningpairs"></a><a name="getkerningpairs"></a>CDC::GetKerningPairs  
 Ruft das Zeichen, kerning-Paare für die Schriftart, die in den angegebenen Gerätekontext markiert ist.  
  
```  
int GetKerningPairs(
    int nPairs,  
    LPKERNINGPAIR lpkrnpair) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPairs`  
 Gibt die Anzahl der [KERNINGPAIR](http://msdn.microsoft.com/library/windows/desktop/dd145024) Strukturen auf den `lpkrnpair`. Die Funktion wird der Kopiervorgang nicht mehr kerning-Paare als `nPairs`.  
  
 `lpkrnpair`  
 Verweist auf ein Array von **KERNINGPAIR** -Strukturen, die den Abstand empfangen-Paaren bei Rückgabe der Funktion. Dieses Array muss mindestens so viele Strukturen Angaben enthalten `nPairs`. Wenn dieser Parameter **NULL**, die Funktion gibt die Gesamtanzahl der kerning-Paare für die Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der kerning-Paare, die abgerufen oder die Gesamtanzahl der kerning-Paare in der Schriftart an, wenn die Funktion erfolgreich ist. 0 (null) wird zurückgegeben, wenn die Funktion fehlschlägt, oder es keine kerning-Paare für die Schriftart sind.  
  
##  <a name="a-namegetlayouta--cdcgetlayout"></a><a name="getlayout"></a>CDC::GetLayout  
 Rufen Sie diese Memberfunktion, um das Layout von Text und Grafiken für einen Gerätekontext, z. B. einen Drucker oder eine Metadatei zu bestimmen.  
  
```  
DWORD GetLayout() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall kennzeichnet das Layout für den aktuellen Gerätekontext. Andernfalls **GDI_ERROR**. Rufen Sie für erweiterte Fehlerinformationen [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Eine Liste der Flags, die Layout, finden Sie unter [CDC::SetLayout](#setlayout).  
  
### <a name="remarks"></a>Hinweise  
 Das Standardlayout ist links nach rechts.  
  
##  <a name="a-namegetmapmodea--cdcgetmapmode"></a><a name="getmapmode"></a>CDC::GetMapMode  
 Ruft den aktuellen Zuordnungsmodus ab.  
  
```  
int GetMapMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Mappingmodus.  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Zuordnungsmodi finden Sie in der `SetMapMode` Member-Funktion.  
  
> [!NOTE]
>  Wenn Sie aufrufen [SetLayout](#setlayout) so ändern Sie den DC in rechts-nach-links-Layout **SetLayout** automatisch ändert die Zuordnung zu `MM_ISOTROPIC`. Folglich jeder nachfolgende Aufruf von `GetMapMode` zurück `MM_ISOTROPIC`.  
  
##  <a name="a-namegetmiterlimita--cdcgetmiterlimit"></a><a name="getmiterlimit"></a>CDC::GetMiterLimit  
 Gibt die Gehrungsgrenze für den Gerätekontext zurück.  
  
```  
float GetMiterLimit() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Gehrungsgrenze wird beim Zeichnen geometrische Zeilen mit Joins Linienverbindungsstile verwendet.  
  
##  <a name="a-namegetnearestcolora--cdcgetnearestcolor"></a><a name="getnearestcolor"></a>CDC::GetNearestColor  
 Gibt die Farbe, die eine bestimmten logischen Farbe am ehesten entspricht.  
  
```  
COLORREF GetNearestColor(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die Farbe zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein (Rot, Grün, Blau) RGB-Wert, der dem stabilen definiert Farbe am nächsten gelegenen der `crColor` -Wert, der das Gerät darstellen kann.  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Gerät muss diese Farbe darstellen können.  
  
##  <a name="a-namegetoutlinetextmetricsa--cdcgetoutlinetextmetrics"></a><a name="getoutlinetextmetrics"></a>CDC::GetOutlineTextMetrics  
 Ruft die Metrik Informationen TrueType-Schriftarten ab.  
  
```  
UINT GetOutlineTextMetrics(
    UINT cbData,  
    LPOUTLINETEXTMETRIC lpotm) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpotm`  
 Verweist auf ein Array von [OUTLINETEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162755) Strukturen. Wenn dieser Parameter **NULL**, die Funktion gibt die Größe des Puffers für die abgerufenen metrischen Daten erforderlich sind.  
  
 `cbData`  
 Gibt die Größe in Bytes des Puffers, der Informationen zurückgegeben werden.  
  
 `lpotm`  
 Verweist auf ein **OUTLINETEXTMETRIC** Struktur. Wenn dieser Parameter **NULL**, die Funktion gibt die Größe des Puffers für die Metrik abgerufenen Informationen erforderlich sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die [OUTLINETEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd162755) Struktur enthält die meisten bereitgestellt, mit dem Format TrueType-Schriftart Metrik Informationen einschließlich einer [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) Struktur. Die letzten vier Mitglieder der **OUTLINETEXTMETRIC** Struktur sind Zeiger auf Zeichenfolgen. Clientanwendungen sollten diese Zeichenfolgen zusätzlich zu den erforderlichen Speicherplatz für die anderen Mitglieder Speicherplatz zuweisen. Da keine Beschränkung System eingeführt, um die Größe der Zeichenfolgen besteht, ist die einfachste Methode zum Reservieren von Speicher durch Angabe die erforderliche Größe abrufen **NULL** für `lpotm` im ersten Aufruf der `GetOutlineTextMetrics` Funktion.  
  
##  <a name="a-namegetoutputcharwidtha--cdcgetoutputcharwidth"></a><a name="getoutputcharwidth"></a>CDC::GetOutputCharWidth  
 Verwendet den Gerätekontext Ausgabe `m_hDC`, und ruft die Breite der einzelnen Zeichen in eine Gruppe aufeinander folgender Zeichen aus der aktuellen Schriftart ab.  
  
```  
BOOL GetOutputCharWidth(
    UINT nFirstChar,  
    UINT nLastChar,  
    LPINT lpBuffer) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nFirstChar`  
 Gibt das erste Zeichen in aufeinander folgende Zeichen in der aktuellen Schriftart.  
  
 `nLastChar`  
 Gibt das letzte Zeichen in aufeinander folgende Zeichen in der aktuellen Schriftart.  
  
 `lpBuffer`  
 Zeigt auf einen Puffer, der die Breitenwerte für aufeinander folgende Zeichen in der aktuellen Schriftart erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel wenn `nFirstChar` identifiziert den Buchstaben 'a' und `nLastChar` identifiziert dem Buchstaben "Z", die die Funktion übernimmt die Breite der nur aus Kleinbuchstaben bestehen.  
  
 Die Funktion speichert die Werte in den Puffer, der auf `lpBuffer`. Dieser Puffer muss groß genug für alle für die Breite sein. d. h. muss vorhanden sein mindestens 26 Einträge im Beispiel angegeben.  
  
 Wenn ein Zeichen in der Gruppe aufeinander folgender Zeichen in einer bestimmten Schriftart nicht vorhanden ist, wird den Width-Wert, der das Standardzeichen zugewiesen werden.  
  
##  <a name="a-namegetoutputtabbedtextextenta--cdcgetoutputtabbedtextextent"></a><a name="getoutputtabbedtextextent"></a>CDC::GetOutputTabbedTextExtent  
 Rufen Sie diese Memberfunktion zum Berechnen der Breite und Höhe einer Zeichenfolge mit Zeichen [M_hDC](#m_hdc), den Ausgabe-Gerätekontext.  
  
```  
CSize GetOutputTabbedTextExtent(
    LPCTSTR lpszString,  
    int nCount,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
  
CSize GetOutputTabbedTextExtent(
    const CString& str,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Zeigt auf eine Zeichenfolge gemessen wird. Sie können auch übergeben einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt für diesen Parameter.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an. Wenn `nCount` –&1; ist, wird die Länge wird berechnet.  
  
 `nTabPositions`  
 Gibt die Anzahl der Tabstopp Positionen im Array auf die `lpnTabStopPositions`.  
  
 `lpnTabStopPositions`  
 Zeigt auf ein Array von Ganzzahlen, die Tabstopp Positionen in logischen Einheiten. Die Tabstopps müssen in aufsteigender Reihenfolge sortiert werden; der kleinste X-Wert sollte das erste Element im Array. Negative Tabstopps sind nicht zulässig.  
  
 `str`  
 Ein `CString` -Objekt, das den angegebenen Zeichen gemessen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Dimensionen der Zeichenfolge (in logischen Einheiten) in einem [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Enthält die Zeichenfolge einen oder mehrere Tabstoppzeichen, basiert die Breite der Zeichenfolge auf die angegebenen Tabstopps `lpnTabStopPositions`. Die Funktion verwendet die aktuell ausgewählte Schriftart, um die Dimensionen der Zeichenfolge zu berechnen.  
  
 Die Breite und Höhe von zurückgegebenen des aktuellen Ausschneidebereichs kein versetzen der `GetOutputTabbedTextExtent` Funktion.  
  
 Da einige Geräte kein Zeichen in regulären Zelle Arrays setzen (d. h. sie Unterschneiden von Zeichen), die Summe der Blöcke, die Zeichen in einer Zeichenfolge in dem Umfang der Zeichenfolge entspricht möglicherweise nicht.  
  
 Wenn `nTabPositions` ist 0 und `lpnTabStopPositions` ist **NULL**, Registerkarten auf acht durchschnittliche Zeichen breiten erweitert werden. Wenn `nTabPositions` 1 ist, ist der Abstand, der durch den ersten Wert in das Array, das die angegebenen Tabstopps getrennt werden `lpnTabStopPositions` Punkte. Wenn `lpnTabStopPositions` verweist auf mehr als einen einzelnen Wert, einen Tabstopp wird für jeden Wert im Array bis zur angegebenen Anzahl setzen `nTabPositions`.  
  
##  <a name="a-namegetoutputtextextenta--cdcgetoutputtextextent"></a><a name="getoutputtextextent"></a>CDC::GetOutputTextExtent  
 Rufen Sie diese Memberfunktion zum Verwenden des Ausgabe-Gerätekontext [M_hDC](#m_hdc), und berechnen Sie die Breite und Höhe einer Textzeile an, mit der aktuellen Schriftart.  
  
```  
CSize GetOutputTextExtent(
    LPCTSTR lpszString,  
    int nCount) const;  
  
CSize GetOutputTextExtent(const CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Zeigt auf eine Zeichenfolge. Sie können auch übergeben einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt für diesen Parameter.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an. Wenn `nCount` –&1; ist, wird die Länge wird berechnet.  
  
 `str`  
 Ein `CString` -Objekt, das den angegebenen Zeichen gemessen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Dimensionen der Zeichenfolge (in logischen Einheiten) zurückgegeben, die einem [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der aktuelle Ausschneidebereich hat keinen Einfluss auf die Breite und Höhe von zurückgegebenen `GetOutputTextExtent`.  
  
 Da einige Geräte kein Zeichen in regulären Zelle Arrays setzen (d. h. sie durchzuführen, kerning), die Summe der Blöcke, die Zeichen in einer Zeichenfolge in dem Umfang der Zeichenfolge entspricht möglicherweise nicht.  
  
##  <a name="a-namegetoutputtextmetricsa--cdcgetoutputtextmetrics"></a><a name="getoutputtextmetrics"></a>CDC::GetOutputTextMetrics  
 Ruft die Metrik für die aktuelle Schriftart mit `m_hDC`, den Ausgabe-Gerätekontext.  
  
```  
BOOL GetOutputTextMetrics(LPTEXTMETRIC lpMetrics) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpMetrics`  
 Verweist auf die [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) -Struktur, die Metriken empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
##  <a name="a-namegetpatha--cdcgetpath"></a><a name="getpath"></a>CDC::getPath  
 Ruft die Koordinaten definieren die Endpunkte der Linien und die Steuerpunkte der Kurven finden Sie in den Pfad, der in den Gerätekontext ausgewählt ist.  
  
```  
int GetPath(
    LPPOINT lpPoints,  
    LPBYTE lpTypes,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von [Punkt](../../mfc/reference/point-structure1.md) Datenstrukturen oder `CPoint` Objekte, die die Endpunkte und die Kurve Kontrollpunkte, platziert werden.  
  
 `lpTypes`  
 Zeigt auf ein Array von Bytes, die in der Vertextypen platziert werden. Werte sind die folgenden:  
  
- **PT_MOVETO** gibt, die an die entsprechende `lpPoints` einen separaten beginnt.  
  
- **PT_LINETO** gibt, die im vorherigen Punkt und dem entsprechenden zeigen `lpPoints` sind die Endpunkte einer Zeile.  
  
- **PT_BEZIERTO** gibt, die an die entsprechende `lpPoints` ist ein Kontrollpunkt oder den Endpunkt für eine Kurve Bzier.  
  
 **PT_BEZIERTO** Typen werden immer in drei Gruppen erfolgen. Der Punkt im unmittelbar vorausgehenden Pfad definiert den Anfangspunkt der Kurve Bzier. Die ersten beiden **PT_BEZIERTO** sind die Steuerpunkte, und die dritte **PT_BEZIERTO** Punkt ist der Endpunkt (wenn hartcodierte).  
  
     Ein **PT_LINETO** oder **PT_BEZIERTO** Typ kann mit dem folgenden Kennzeichen kombiniert werden (mit dem bitweisen Operator `OR`) um anzugeben, dass der entsprechende Punkt der letzte Punkt in einer Figur ist und die Figur geschlossen werden muss:  
  
- **PT_CLOSEFIGURE** gibt, die in der Abbildung wird automatisch geschlossen, nach der entsprechenden Zeile oder Kurve gezeichnet wird. In der Abbildung wird durch eine Linie vom oder Kurve Endpunkt zum Zeitpunkt der letzten geschlossen **PT_MOVETO**.  
  
 `nCount`  
 Gibt die Gesamtanzahl der [Punkt](../../mfc/reference/point-structure1.md) Datenstrukturen, die in platziert werden, können die `lpPoints` Array. Dieser Wert muss identisch mit der Anzahl der Bytes, die in platziert werden kann der `lpTypes` Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die `nCount` Parameter ungleich NULL ist, ist die Anzahl der Punkte aufgelistet. Wenn `nCount` ist 0, die Gesamtzahl der Punkte im Pfad (und `GetPath` nichts in den Puffer geschrieben). Wenn `nCount` ungleich NULL und kleiner als die Anzahl der Punkte im Pfad, der Rückgabewert-1 ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Gerätekontext muss einen geschlossenen Pfad enthalten. Die Punkte des Pfads werden in logischen Koordinaten zurückgegeben. Punkte befinden sich im Pfad in logische Koordinaten, also `GetPath` ändert sich die Punkte in logische Koordinaten in logische Koordinaten mithilfe der Umkehrung der aktuellen Transformation. Die `FlattenPath` Member-Funktion kann aufgerufen werden, bevor `GetPath`, um alle Kurven im Pfad in Liniensegmente zu konvertieren.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC:: beginpath](#beginpath).  
  
##  <a name="a-namegetpixela--cdcgetpixel"></a><a name="getpixel"></a>CDC::getPixel  
 Ruft den RGB-Farbwert des Pixels am angegebenen Punkt *x* und *y*.  
  
```  
COLORREF GetPixel(
    int x,  
    int y) const;  
  
COLORREF GetPixel(POINT point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Punktes, der überprüft werden.  
  
 *y*  
 Gibt die logische y-Koordinate des Punktes, der überprüft werden.  
  
 `point`  
 Gibt die logische X - und y-Koordinaten des Punkts, der überprüft werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Für Version der Funktion einen RGB-Farbwert für die Farbe des angegebenen Punkt. Es ist -1, wenn die Koordinaten ein Punkts in den Ausschneidebereich nicht angeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt muss in den Ausschneidebereich sein. Ist der Punkt nicht in den Ausschneidebereich, wird die Funktion hat keine Auswirkung und gibt-1 zurück.  
  
 Nicht alle Geräte unterstützen die **GetPixel** Funktion. Weitere Informationen finden Sie unter der **RC_BITBLT** Raster Funktion unter den [GetDeviceCaps](#getdevicecaps) Member-Funktion.  
  
 Die **GetPixel** Member-Funktion weist zwei Formen. Der erste erfordert zwei Koordinatenwerte; der zweite erfordert entweder ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
##  <a name="a-namegetpolyfillmodea--cdcgetpolyfillmode"></a><a name="getpolyfillmode"></a>CDC::GetPolyFillMode  
 Ruft den aktuellen Polygon Füllmodus ab.  
  
```  
int GetPolyFillMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle gefülltes Polygon Modus **ALTERNATIVEN** oder **WICKLUNGSREIHENFOLGEN**, wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter der `SetPolyFillMode` Member-Funktion für eine Beschreibung der Polygon füllen.  
  
##  <a name="a-namegetrop2a--cdcgetrop2"></a><a name="getrop2"></a>CDC::GetROP2  
 Ruft den Zeichnungsmodus des aktuellen ab.  
  
```  
int GetROP2() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeichnungsmodus. Eine Liste der Werte für den zeichnen, finden Sie unter der `SetROP2` Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Zeichnungsmodus gibt an, wie die Farben des Stifts und das Innere eines ausgefüllten Objekte mit Farbe bereits auf der Anzeigeoberfläche kombiniert werden.  
  
##  <a name="a-namegetsafehdca--cdcgetsafehdc"></a><a name="getsafehdc"></a>CDC::GetSafeHdc  
 Rufen Sie diese Memberfunktion abzurufenden [M_hDC](#m_hdc), den Ausgabe-Gerätekontext.  
  
```  
HDC GetSafeHdc() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für einen Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert auch mit null-Zeiger.  
  
##  <a name="a-namegetstretchbltmodea--cdcgetstretchbltmode"></a><a name="getstretchbltmode"></a>CDC::GetStretchBltMode  
 Ruft den aktuellen Dehnen von Bitmap-Modus ab.  
  
```  
int GetStretchBltMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt den aktuellen Dehnen von Bitmap-Modus – **STRETCH_ANDSCANS**, **STRETCH_DELETESCANS**, oder **STRETCH_ORSCANS** – Wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Dehnen von Bitmap-Modus definiert, wie Informationen aus Bitmaps entfernt werden, die gestreckt oder komprimiert die `StretchBlt` Member-Funktion.  
  
 Die **STRETCH_ANDSCANS** und **STRETCH_ORSCANS** Modi werden in der Regel verwendet, um Vordergrund Pixel monochrome Bitmaps beizubehalten. Die **STRETCH_DELETESCANS** Modus wird normalerweise verwendet, um Farbe in Farbbitmaps zu erhalten.  
  
##  <a name="a-namegettabbedtextextenta--cdcgettabbedtextextent"></a><a name="gettabbedtextextent"></a>CDC::GetTabbedTextExtent  
 Rufen Sie diese Memberfunktion zum Berechnen der Breite und Höhe einer Zeichenfolge mit Zeichen [M_hAttribDC](#m_hattribdc), den Gerätekontext Attribut.  
  
```  
CSize GetTabbedTextExtent(
    LPCTSTR lpszString,  
    int nCount,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
  
CSize GetTabbedTextExtent(
    const CString& str,  
    int nTabPositions,  
    LPINT lpnTabStopPositions) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Zeigt auf eine Zeichenfolge. Sie können auch übergeben einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt für diesen Parameter.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an. Wenn `nCount` –&1; ist, wird die Länge wird berechnet.  
  
 `nTabPositions`  
 Gibt die Anzahl der Tabstopp Positionen im Array auf die `lpnTabStopPositions`.  
  
 `lpnTabStopPositions`  
 Zeigt auf ein Array von Ganzzahlen, die Tabstopp Positionen in logischen Einheiten. Die Tabstopps müssen in aufsteigender Reihenfolge sortiert werden; der kleinste X-Wert sollte das erste Element im Array. Negative Tabstopps sind nicht zulässig.  
  
 `str`  
 Ein `CString` -Objekt, das den angegebenen Zeichen, gezeichnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Dimensionen der Zeichenfolge (in logischen Einheiten) in einem [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Enthält die Zeichenfolge einen oder mehrere Tabstoppzeichen, basiert die Breite der Zeichenfolge auf die angegebenen Tabstopps `lpnTabStopPositions`. Die Funktion verwendet die aktuell ausgewählte Schriftart, um die Dimensionen der Zeichenfolge zu berechnen.  
  
 Die Breite und Höhe von zurückgegebenen des aktuellen Ausschneidebereichs kein versetzen der `GetTabbedTextExtent` Funktion.  
  
 Da einige Geräte kein Zeichen in regulären Zelle Arrays setzen (d. h. sie Unterschneiden von Zeichen), die Summe der Blöcke, die Zeichen in einer Zeichenfolge in dem Umfang der Zeichenfolge entspricht möglicherweise nicht.  
  
 Wenn `nTabPositions` ist 0 und `lpnTabStopPositions` ist **NULL**, Registerkarten auf acht Mal die durchschnittliche Zeichenbreite erweitert werden. Wenn `nTabPositions` 1 ist, ist der Abstand, der durch den ersten Wert in das Array, das die angegebenen Tabstopps getrennt werden `lpnTabStopPositions` Punkte. Wenn `lpnTabStopPositions` verweist auf mehr als einen einzelnen Wert, einen Tabstopp wird für jeden Wert im Array bis zur angegebenen Anzahl setzen `nTabPositions`.  
  
##  <a name="a-namegettextaligna--cdcgettextalign"></a><a name="gettextalign"></a>CDC::GetTextAlign  
 Ruft den Status der Flags Ausrichtung für den Gerätekontext ab.  
  
```  
UINT GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status der Flags Ausrichtung. Der Rückgabewert ist eine oder mehrere der folgenden Werte:  
  
- **TA_BASELINE** gibt die Ausrichtung der x-Achse und der Baseline für die ausgewählte Schriftart innerhalb des umschließenden Rechtecks an.  
  
- **TA_BOTTOM** gibt die Ausrichtung der x-Achse und dem unteren Rand des umschließenden Rechtecks an.  
  
- **TA_CENTER** gibt die Ausrichtung der y-Achse und dem Mittelpunkt des umschließenden Rechtecks an.  
  
- **TA_LEFT** gibt die Ausrichtung der y-Achse und dem linken Rand des umschließenden Rechtecks an.  
  
- **TA_NOUPDATECP** gibt an, dass die aktuelle Position nicht aktualisiert wird.  
  
- **TA_RIGHT** gibt die Ausrichtung der y-Achse und der rechten Seite des umschließenden Rechtecks an.  
  
- **TA_TOP** Ausrichtung der x-Achse und dem oberen Rand das umschließende Rechteck angibt.  
  
- **TA_UPDATECP** gibt an, dass die aktuelle Position aktualisiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Ausrichtung Flags legen fest, wie die `TextOut` und `ExtTextOut` Memberfunktionen ausrichten eine Textzeichenfolge in Bezug auf die Zeichenfolge Ausgangspunkt. Die Ausrichtung Flags sind nicht unbedingt ein Einzelbit-Flags und möglicherweise gleich 0 ist. Um zu testen, ob ein Flag festgelegt ist, sollte eine Anwendung die folgenden Schritte ausführen:  
  
1.  Anwenden der bitweisen OR-Operators das Flag und seine zugehörigen Flags, die wie folgt zusammengefasst:  
  
    - **TA_LEFT**, **TA_CENTER**, und **TA_RIGHT**  
  
    - **TA_BASELINE**, **TA_BOTTOM**, und **TA_TOP**  
  
    - **TA_NOUPDATECP** und **TA_UPDATECP**  
  
2.  Anwenden von bitweisen- und Operator das Ergebnis und der Rückgabewert von `GetTextAlign`.  
  
3.  Testen Sie die Gleichheit dieses Ergebnis und dem Flag.  
  
##  <a name="a-namegettextcharacterextraa--cdcgettextcharacterextra"></a><a name="gettextcharacterextra"></a>CDC::GetTextCharacterExtra  
 Ruft die aktuelle Einstellung für den Zeichenabstands ab.  
  
```  
int GetTextCharacterExtra() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Anteil der Zeichenabstands.  
  
### <a name="remarks"></a>Hinweise  
 GDI hinzugefügt jedes Zeichen, einschließlich Zeilenumbruchzeichen unverändert, wenn sie eine Textzeile in den Gerätekontext schreibt diesen Abstand.  
  
 Der Standardwert für den Zeichenabstands ist 0.  
  
##  <a name="a-namegettextcolora--cdcgettextcolor"></a><a name="gettextcolor"></a>CDC::GetTextColor  
 Ruft die Textfarbe ab.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Textfarbe als einen RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Farbe des Texts wird die Vordergrundfarbe der Zeichen, die mit der Ausgabe von Text Memberfunktionen GDI gezeichnet [TextOut](#textout), [ExtTextOut](#exttextout), und [TabbedTextOut](#tabbedtextout).  
  
##  <a name="a-namegettextextenta--cdcgettextextent"></a><a name="gettextextent"></a>CDC::getTextExtent  
 Rufen Sie diese Memberfunktion, um die Breite und Höhe einer Textzeile, die mit der aktuellen Schriftart ermitteln, die Dimensionen zu berechnen.  
  
```  
CSize GetTextExtent(
    LPCTSTR lpszString,  
    int nCount) const;  
  
CSize GetTextExtent(const CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Zeigt auf eine Zeichenfolge. Sie können auch übergeben einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt für diesen Parameter.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an.  
  
 `str`  
 Ein `CString` -Objekt, das die angegebenen Zeichen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Dimensionen der Zeichenfolge (in logischen Einheiten) in einem [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Informationen werden abgerufen, von [M_hAttribDC](#m_hattribdc), den Gerätekontext Attribut.  
  
 In der Standardeinstellung `GetTextExtent` geht davon aus, der Text für die Dimension wird in einer horizontalen Linie festgelegt ist (d. h. "Escapement" ist 0). Wenn Sie eine Schriftart, die Angabe einer nicht-NULL "Escapement" erstellen, müssen Sie den Winkel des Texts explizit auf die Dimensionen der Zeichenfolge erhalten konvertieren.  
  
 Der aktuelle Ausschneidebereich hat keinen Einfluss auf die Breite und Höhe von zurückgegebenen `GetTextExtent`.  
  
 Da einige Geräte kein Zeichen in regulären Zelle Arrays setzen (d. h. sie durchzuführen, kerning), die Summe der Blöcke, die Zeichen in einer Zeichenfolge in dem Umfang der Zeichenfolge entspricht möglicherweise nicht.  
  
##  <a name="a-namegettextextentexpointia--cdcgettextextentexpointi"></a><a name="gettextextentexpointi"></a>CDC::GetTextExtentExPointI  
 Ruft die Anzahl der Zeichen in einer angegebenen Zeichenfolge, die in einem angegebenen Bereich passt, und füllt ein Bytearray mit dem Text-Block für jedes dieser Zeichen ab.  
  
```  
BOOL GetTextExtentExPointI(
    LPWORD pgiIn,  
    int cgi,  
    int nMaxExtent,  
    LPINT lpnFit,  
    LPINT alpDx,  
    LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pgiIn`  
 Ein Zeiger auf ein Array von Glyph-Indizes, die für die Blöcke abgerufen werden sollen.  
  
 `cgi`  
 Gibt die Anzahl der Symbole in das Array, das auf den `pgiIn`.  
  
 `nMaxExtent`  
 Gibt die maximale zulässige Breite in logischen Einheiten der formatierten Zeichenfolge.  
  
 `lpnFit`  
 Ein Zeiger auf eine ganze Zahl, die Anzahl der die maximale Anzahl von Zeichen empfängt, die in den angegebenen Platz passen `nMaxExtent`. Wenn `lpnFit` ist **NULL**, `nMaxExtent` wird ignoriert.  
  
 *alpDx*  
 Ein Zeiger auf ein Array von Ganzzahlen, die teilweise Glyphe Blöcke empfängt. Jedes Element im Array gibt den Abstand in logischen Einheiten zwischen dem Beginn des Arrays Indizes Glyphe und eines der Symbole, die in den angegebenen Platz passt `nMaxExtent`. Obwohl dieses Array mindestens so viele Elemente als Symbolindizes haben sollten `cgi`, die Funktion füllt das Array mit den Wertebereichen nur für beliebig viele Glyph-Indizes wie vom angegebenen `lpnFit`. Wenn *LpnDx* ist **NULL**, die Funktion ist nicht Teil der Zeichenfolge Breite berechnet.  
  
 `lpSize`  
 Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die Dimensionen des Arrays Indizes Glyphe in logischen Einheiten empfängt. Dieser Wert kann nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetTextExtentExPointI](http://msdn.microsoft.com/library/windows/desktop/dd144936), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettextextentpointia--cdcgettextextentpointi"></a><a name="gettextextentpointi"></a>CDC::GetTextExtentPointI  
 Ruft die Breite und Höhe des angegebenen Arrays von Glyph-Indizes.  
  
```  
BOOL GetTextExtentPointI(
    LPWORD pgiIn,  
    int cgi,  
    LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pgiIn`  
 Ein Zeiger auf ein Array von Glyph-Indizes, die für die Blöcke abgerufen werden sollen.  
  
 `cgi`  
 Gibt die Anzahl der Symbole in das Array, das auf den `pgiIn`.  
  
 `lpSize`  
 Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die Dimensionen des Arrays Indizes Glyphe in logischen Einheiten empfängt. Dieser Wert kann nicht **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der Funktion [GetTextExtentPointI](http://msdn.microsoft.com/library/windows/desktop/dd144939), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettextfacea--cdcgettextface"></a><a name="gettextface"></a>CDC::GetTextFace  
 Rufen Sie diese Memberfunktion um den Namen der aktuellen Schriftart in einen Puffer zu kopieren.  
  
```  
int GetTextFace(
    int nCount,  
    LPTSTR lpszFacename) const;  
  
int GetTextFace(CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nCount`  
 Gibt die Größe des Puffers (in Byte). Wenn der Schriftartname länger als die Anzahl der Bytes, die von diesem Parameter angegeben ist, wird der Name abgeschnitten.  
  
 *lpszFacename*  
 Verweist auf den Puffer für den Namen.  
  
 `rString`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes in den Puffer, nicht einschließlich des abschließenden Zeichens Null kopiert. Es ist 0, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Der Schriftartname wird als Null-terminierte Zeichenfolge kopiert.  
  
##  <a name="a-namegettextmetricsa--cdcgettextmetrics"></a><a name="gettextmetrics"></a>CDC::GetTextMetrics  
 Ruft die Metriken für die aktuelle Schriftart mit den Gerätekontext Attribut ab.  
  
```  
BOOL GetTextMetrics(LPTEXTMETRIC lpMetrics) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpMetrics`  
 Verweist auf die [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) -Struktur, die Metriken empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
##  <a name="a-namegetviewportexta--cdcgetviewportext"></a><a name="getviewportext"></a>CDC::GetViewportExt  
 Ruft die x und y-Blöcke von den Gerätekontext Viewport ab.  
  
```  
CSize GetViewportExt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die X - und y-Blöcke (in Geräteeinheiten) als ein `CSize` Objekt.  
  
##  <a name="a-namegetviewportorga--cdcgetviewportorg"></a><a name="getviewportorg"></a>CDC::GetViewportOrg  
 Ruft die x und y-Koordinaten des Ursprungs der Viewport der Gerätekontext zugeordnet.  
  
```  
CPoint GetViewportOrg() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Herkunft des Viewports (in logische Koordinaten) als ein `CPoint` Objekt.  
  
##  <a name="a-namegetwindowa--cdcgetwindow"></a><a name="getwindow"></a>CDC::GetWindow  
 Gibt das Fenster der Anzeige-Gerätekontext zugeordnet.  
  
```  
CWnd* GetWindow() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine `CWnd` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte Funktion. Beispielsweise kann diese Memberfunktion das Ansichtsfenster nicht beim Drucken oder in der Seitenansicht zurück. Es gibt immer das Fenster Ausgabe zugeordnet. Ausgabefunktionen, mit denen der angegebene Domänencontroller in diesem Fenster zeichnen.  
  
##  <a name="a-namegetwindowexta--cdcgetwindowext"></a><a name="getwindowext"></a>CDC::GetWindowExt  
 Ruft die x und y-Blöcke im Fenster den Gerätekontext zugeordnet.  
  
```  
CSize GetWindowExt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die X - und y-Blöcke (in logischen Einheiten) als ein `CSize` Objekt.  
  
##  <a name="a-namegetwindoworga--cdcgetwindoworg"></a><a name="getwindoworg"></a>CDC::GetWindowOrg  
 Ruft die x- und y-Koordinaten des Ursprungs des Fensters den Gerätekontext zugeordnet.  
  
```  
CPoint GetWindowOrg() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ursprung des Fensters (in logischen Koordinaten) als ein `CPoint` Objekt.  
  
##  <a name="a-namegetworldtransforma--cdcgetworldtransform"></a><a name="getworldtransform"></a>CDC::GetWorldTransform  
 Ruft den aktuellen World Speicherplatz für Seite-Space-Transformation ab.  
  
```  
BOOL GetWorldTransform(XFORM& rXform) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rXform`  
 Ein Verweis auf eine [XFORM](http://msdn.microsoft.com/library/windows/desktop/dd145228) -Struktur, die den aktuellen World Speicherplatz für Seite-Space-Transformation empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL bei Erfolg zurück.  
  
 Gibt 0 bei einem Fehler zurück.  
  
 Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode umschließt die Windows GDI-Funktion [GetWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd144953).  
  
##  <a name="a-namegradientfilla--cdcgradientfill"></a><a name="gradientfill"></a>CDC::GradientFill  
 Rufen Sie diese Memberfunktion zum Rechteck und Dreieck Strukturen mit Farbe zu füllen, das problemlos von einer Seite zur anderen ausgeblendet wird.  
  
```  
BOOL GradientFill(
    TRIVERTEX* pVertices,  
    ULONG nVertices,  
    void* pMesh,  
    ULONG nMeshElements,  
    DWORD dwMode);
```  
  
### <a name="parameters"></a>Parameter  
 *pVertices*  
 Zeiger auf ein Array von [TRIVERTEX](http://msdn.microsoft.com/library/windows/desktop/dd145142) Strukturen, die jeweils ein Dreieck Vertex definieren.  
  
 *nVertices*  
 Die Anzahl der Scheitelpunkte.  
  
 `pMesh`  
 Array von [GRADIENT_TRIANGLE](http://msdn.microsoft.com/library/windows/desktop/dd144959) im Modus Dreieck oder ein Array von Strukturen [GRADIENT_RECT](http://msdn.microsoft.com/library/windows/desktop/dd144958) Strukturen im Rechteck-Modus.  
  
 *nMeshElements*  
 Die Anzahl von Elementen (Dreiecke oder Rechtecke) in `pMesh`.  
  
 `dwMode`  
 Gibt den Farbverlauf-Modus. Eine Liste der möglichen Werte finden Sie unter [GradientFill](http://msdn.microsoft.com/library/windows/desktop/dd144957) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter `GradientFill` in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegraystringa--cdcgraystring"></a><a name="graystring"></a>CDC:: graystring  
 Zeichnet abgeblendet (grau) Text an der angegebenen Position durch Schreiben des Texts in einem Speicher-Bitmap, Bitmap ab- und anschließend kopieren die Bitmap für die Anzeige.  
  
```  
virtual BOOL GrayString(
    CBrush* pBrush,  
    BOOL (CALLBACK* lpfnOutput)(
    HDC,
    LPARAM,
    int),  
    LPARAM lpData,  
    int nCount,  
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `pBrush`  
 Identifiziert den Pinsel für Abblenden (abgeblendet) verwendet werden soll.  
  
 `lpfnOutput`  
 Gibt die Adresse der Prozedur-Instanz der Anwendung bereitgestellten Rückruffunktion an, die die Zeichenfolge gezeichnet wird. Weitere Informationen finden Sie unter der Beschreibung der Windows **OutputFunc** [Rückruffunktion](../../mfc/reference/callback-function-for-cdc-graystring.md). Wenn dieser Parameter **NULL**, das System verwendet die Windows `TextOut` Funktion zum Zeichnen der Zeichenfolge und `lpData` wird davon ausgegangen, dass ein long-Zeiger auf die Zeichenfolge ausgegeben werden.  
  
 `lpData`  
 Gibt einen ferner Zeiger auf Daten, die an die Ausgabefunktion übergeben werden. Wenn `lpfnOutput` ist **NULL**, `lpData` muss ein long-Zeiger auf die Zeichenfolge ausgegeben werden.  
  
 `nCount`  
 Gibt die Anzahl der Zeichen, die ausgegeben werden. Wenn dieser Parameter 0 ist `GrayString` berechnet die Länge der Zeichenfolge (vorausgesetzt, dass `lpData` ist ein Zeiger auf die Zeichenfolge). Wenn `nCount` ist – 1 und die Funktion, die auf den `lpfnOutput` 0 zurückgibt, ist das Bild angezeigt wird, jedoch nicht abgeblendet.  
  
 *x*  
 Gibt die logische X-Koordinate der Startposition des Rechtecks, das die Zeichenfolge enthält.  
  
 *y*  
 Gibt die logische y-Koordinate der Startposition des Rechtecks, das die Zeichenfolge enthält.  
  
 `nWidth`  
 Gibt die Breite (in logischen Einheiten) des Rechtecks, das die Zeichenfolge enthält. Wenn `nWidth` ist 0, `GrayString` berechnet die Breite des Bereichs, sofern `lpData` ist ein Zeiger auf die Zeichenfolge.  
  
 `nHeight`  
 Gibt die Höhe (in logischen Einheiten) des Rechtecks, das die Zeichenfolge enthält. Wenn `nHeight` ist 0, `GrayString` berechnet die Höhe des Bereichs, sofern `lpData` ist ein Zeiger auf die Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Zeichenfolge gezeichnet wird, oder 0, wenn entweder die `TextOut` oder die der Anwendung bereitgestellten Ausgabefunktion zurückgegebenen 0 ist, oder wenn nicht genügend Arbeitsspeicher zum Erstellen einer Bitmap Arbeitsspeicher zum Dämpfen.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion wird den Text unabhängig von der ausgewählten Pinsel und Hintergrund. Der `GrayString` Member-Funktion verwendet die aktuell ausgewählte Schriftart. Die `MM_TEXT` Zuordnungsmodus muss ausgewählt werden, bevor Sie diese Funktion verwenden.  
  
 Eine Anwendung auf Geräten mit Unterstützung von Grau als Volltonfarbe ohne Aufruf deaktiviert (abgeblendet) Zeichenfolgen Zeichnen der `GrayString` Member-Funktion. Die Systemfarbe **COLOR_GRAYTEXT** ist die einfarbig grau Systemfarbe zum Zeichnen von deaktivierten Text verwendet. Die Anwendung kann Aufrufen der **GetSysColor** Windows-Funktion zum Abrufen des Wertes der **COLOR_GRAYTEXT**. Die Anwendung kann aufrufen, ist die Farbe als 0 (Schwarz), die `SetTextColor` Memberfunktion, die die Farbe des Texts auf den Farbwert und zeichnen Sie dann die Zeichenfolge direkt. Wenn die abgerufene Farbe auf Schwarz festgelegt ist, muss die Anwendung aufrufen `GrayString` , abgeblendet (grau) den Text.  
  
 Wenn `lpfnOutput` ist **NULL**, GDI verwendet Windows [TextOut](http://msdn.microsoft.com/library/windows/desktop/dd145133) -Funktion und `lpData` wird davon ausgegangen, dass ein ferner Zeiger auf das Zeichen ausgegeben werden. Wenn die Zeichen ausgegeben werden von behandelt werden können der `TextOut` Member-Funktion (z. B. die Zeichenfolge als Bitmap gespeichert ist), die Anwendung muss eine eigene Ausgabefunktion bereitstellen.  
  
 Beachten Sie außerdem, dass alle Rückruffunktionen vor der Rückgabe auf Windows, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht Microsoft Foundation-Ausnahmen abfangen müssen. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
 Die Rückruffunktion übergeben wird, um `GrayString` verwenden, müssen die `__stdcall` -Aufrufkonvention verwendet und muss mit exportiert werden `__declspec`.  
  
 Wenn das Framework ist im Vorschaumodus, einen Aufruf der `GrayString` Memberfunktion übersetzt eine `TextOut` Aufruf und die Rückruffunktion wird nicht aufgerufen.  
  
##  <a name="a-namehimetrictodpa--cdchimetrictodp"></a><a name="himetrictodp"></a>CDC::HIMETRICtoDP  
 Verwenden Sie diese Funktion beim Konvertieren von **HIMETRIC** Größe von OLE in Pixel.  
  
```  
void HIMETRICtoDP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpSize`  
 Verweist auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zuordnung der Gerätekontextobjekt ist `MM_LOENGLISH`, `MM_HIENGLISH`, `MM_LOMETRIC` oder `MM_HIMETRIC`, und klicken Sie dann die Konvertierung auf die Anzahl der Pixel pro Zoll physischen basiert. Wenn der Zuordnungsmodus eines anderen Modus nicht beschränkt ist (z. B. `MM_TEXT`), und klicken Sie dann die Konvertierung auf die Anzahl der Pixel pro Zoll logische basiert.  
  
##  <a name="a-namehimetrictolpa--cdchimetrictolp"></a><a name="himetrictolp"></a>CDC::HIMETRICtoLP  
 Rufen Sie diese Funktion konvertiert **HIMETRIC** Einheiten in logischen Einheiten.  
  
```  
void HIMETRICtoLP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpSize`  
 Verweist auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, wenn man **HIMETRIC** mit einer Größe von OLE und möchten sie in Ihrer Anwendung natürliche Zuordnungsmodus konvertieren.  
  
 Die Konvertierung wird erreicht, indem zuerst konvertieren die **HIMETRIC** Einheiten in Pixel und anschließend diese Einheiten in logischen Einheiten, die mit den Gerätekontext aktuelle Zuordnung Einheiten konvertieren. Beachten Sie, dass die Blöcke von Fenster und Darstellungsbereich des Geräts das Ergebnis auswirkt.  
  
##  <a name="a-nameintersectcliprecta--cdcintersectcliprect"></a><a name="intersectcliprect"></a>CDC::IntersectClipRect  
 Erstellt einen neuen Ausschneidebereich durch die Schnittmenge der aktuelle Bereich und die durch angegebene Rechteck bilden `x1`, `y1`, `x2`, und `y2`.  
  
```  
int IntersectClipRect(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
int IntersectClipRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des Rechtecks.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Rechtecks.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des Rechtecks.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des Rechtecks.  
  
 `lpRect`  
 Gibt das Rechteck. Übergeben Sie entweder ein `CRect` Objekt oder einen Zeiger auf eine `RECT` Struktur für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Ausschneidebereich-Typ. Einer der folgenden Werte sind möglich:  
  
- **COMPLEXREGION** neue Ausschneidebereich hat Ränder überlappen.  
  
- **Fehler** Gerätekontext ist ungültig.  
  
- **NULLREGION** neue Ausschneidebereich ist leer.  
  
- **SIMPLEREGION** neue Ausschneidebereich besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 GDI Schneidet alle nachfolgenden Ausgaben an die neue Grenze an. Die Breite und Höhe darf maximal 32.767.  
  
##  <a name="a-nameinvertrecta--cdcinvertrect"></a><a name="invertrect"></a>CDC::InvertRect  
 Hierdurch wird der Inhalt des angegebenen Rechtecks.  
  
```  
void InvertRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf einen `RECT` , enthält die logischen Koordinaten des Rechtecks umgekehrt werden. Sie können auch übergeben ein `CRect` -Objekt für diesen Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Inversion ist eine logische nicht Vorgang und spiegelt die Bits der einzelnen Pixel. Auf die monochrome Anzeige Funktion, dass weißen Pixeln Schwarz und Schwarz Weiß. Farbe angezeigt wird hängt ab, der die Umkehrung wie Farben für die Anzeige generiert werden. Aufrufen von `InvertRect` zweimal mit dem gleichen Rechteck wird wiederhergestellt der vorherigen Farben angezeigt.  
  
 Wenn das Rechteck leer ist, wird nichts gezeichnet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView Nr.&36;](../../mfc/codesnippet/cpp/cdc-class_8.cpp)]  
  
##  <a name="a-nameinvertrgna--cdcinvertrgn"></a><a name="invertrgn"></a>CDC::InvertRgn  
 Invertiert die Farben in der angegebenen Region `pRgn`.  
  
```  
BOOL InvertRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Identifiziert den Bereich umgekehrt werden. Die Koordinaten des Bereichs werden in logischen Einheiten angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Auf die monochrome Anzeige Funktion, dass weißen Pixeln Schwarz und Schwarz Weiß. Die Umkehrung hängt mit Farben wie die Farben für die Anzeige generiert werden.  
  
##  <a name="a-nameisprintinga--cdcisprinting"></a><a name="isprinting"></a>CDC::IsPrinting  
 Bestimmt, ob es sich bei der Gerätekontext für das Drucken verwendet wird.  
  
```  
BOOL IsPrinting() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDC` Objekt ist ein Domänencontroller, andernfalls 0.  
  
##  <a name="a-namelinetoa--cdclineto"></a><a name="lineto"></a>CDC::LineTo  
 Zeichnet eine Linie von der aktuellen Position bis zum, aber nicht einschließlich, den durch angegebenen Punkt *x* und *y* (oder `point`).  
  
```  
BOOL LineTo(
    int x,  
    int y);  
  
BOOL LineTo(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Endpunkts der Linie.  
  
 *y*  
 Gibt die logische y-Koordinate des Endpunkts der Linie.  
  
 `point`  
 Gibt den Endpunkt für die Linie. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Linie gezeichnet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeile wird mit dem ausgewählten Stift gezeichnet. Die aktuelle Position festgelegt ist, um *x*, *y* oder `point`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRect::CenterPoint](../../atl-mfc-shared/reference/crect-class.md#centerpoint).  
  
##  <a name="a-namelptodpa--cdclptodp"></a><a name="lptodp"></a>CDC::LPtoDP  
 Logische Einheiten konvertiert in Geräteeinheiten.  
  
```  
void LPtoDP(
    LPPOINT lpPoints,  
    int nCount = 1) const;  
  
void LPtoDP(LPRECT lpRect) const;
void LPtoDP(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Zeigt auf ein Array von Punkten. Jedem Punkt im Array ist ein [zeigen](../../mfc/reference/point-structure1.md) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
 `nCount`  
 Die Anzahl der Punkte im Array.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt. Dieser Parameter wird für der häufige Fall einer Zuordnung ein Rechteck vom logischen Gerät Einheiten verwendet.  
  
 `lpSize`  
 Verweist auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die-Funktion ordnet die Koordinaten für jeden Punkt oder Dimensionen einer Größe von GDI logischen Koordinatensystem in das gerätekoordinatensystem. Die Konvertierung hängt von der aktuellen Zuordnungsmodus und die Einstellungen der Herkunft und Blöcke von Fenster und Darstellungsbereich des Geräts ab.  
  
 Die x- und y-Koordinaten der Punkte sind 2-Byte, die im Bereich von – 32.768 bis 32.767 Ganzzahlen mit Vorzeichen. In Fällen, in denen der Zuordnungsmodus Werte größer als diese Grenzwerte führen würde, setzt das System die Werte – 32.768 und 32.767.  
  
##  <a name="a-namelptohimetrica--cdclptohimetric"></a><a name="lptohimetric"></a>CDC::LPtoHIMETRIC  
 Rufen Sie diese Funktion zum Konvertieren von logischer Einheiten in **HIMETRIC** Einheiten.  
  
```  
void LPtoHIMETRIC(LPSIZE lpSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpSize`  
 Verweist auf eine **Größe** Struktur oder ein `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion erhalten Sie, wenn **HIMETRIC** Größen OLE, die von Ihrer Anwendung natürliche Zuordnungsmodus konvertieren. Beachten Sie, dass die Blöcke von Fenster und Darstellungsbereich des Geräts das Ergebnis auswirkt.  
  
 Die Konvertierung wird erreicht, indem Sie zuerst die logischen Einheiten in Pixel, wobei den Gerätekontext derzeit Zuordnung und dann diese Einheiten in konvertieren **HIMETRIC** Einheiten.  
  
##  <a name="a-namemhattribdca--cdcmhattribdc"></a><a name="m_hattribdc"></a>CDC::m_hAttribDC  
 Die Attribut-Gerätekontext für diesen `CDC` Objekt.  
  
```  
HDC m_hAttribDC;  
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist dieser Gerätekontext gleich `m_hDC`. Im allgemeinen `CDC` GDI-Aufrufe, die Informationen aus dem Gerätekontext geleitet `m_hAttribDC`. Finden Sie unter der [CDC](../../mfc/reference/cdc-class.md) klassenbeschreibung Weitere Informationen über die Verwendung dieser beiden Kontexte.  
  
##  <a name="a-namemhdca--cdcmhdc"></a><a name="m_hdc"></a>CDC::m_hDC  
 Die Ausgabe-Gerätekontext für diesen `CDC` Objekt.  
  
```  
HDC m_hDC;  
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `m_hDC` gleich `m_hAttribDC`, der andere vom Gerätekontext `CDC`. Im allgemeinen `CDC` GDI-Aufrufe, die Ausgabe zu erstellen, wechseln Sie zu der `m_hDC` Gerätekontext. Initialisieren Sie `m_hDC` und `m_hAttribDC` auf verschiedenen Geräten. Finden Sie unter der [CDC](../../mfc/reference/cdc-class.md) klassenbeschreibung Weitere Informationen über die Verwendung dieser beiden Kontexte.  
  
##  <a name="a-namemaskblta--cdcmaskblt"></a><a name="maskblt"></a>CDC::MaskBlt  
 Kombiniert die Farbdaten für die Quell- und Ziel-Bitmaps, die unter Verwendung der angegebenen Maske und Raster des Vorgangs.  
  
```  
BOOL MaskBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    CBitmap& maskBitmap,  
    int xMask,  
    int yMask,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 *y*  
 Gibt die logische y-Koordinate der oberen linken Ecke des Zielrechtecks.  
  
 `nWidth`  
 Gibt die Breite in logischen Einheiten der Bitmap für die Ziel-Rechteck und die Quelle an.  
  
 `nHeight`  
 Gibt die Höhe in logischen Einheiten der Bitmap für die Ziel-Rechteck und die Quelle an.  
  
 `pSrcDC`  
 Identifiziert den Gerätekontext, von dem die Bitmap ist, kopiert werden soll. Es muss NULL, wenn die *DwRop* Parameter gibt einen rastervorgang, der nicht mit eine Datenquelle enthält.  
  
 `xSrc`  
 Gibt die logische X-Koordinate der oberen linken Ecke des Quellbitmap.  
  
 `ySrc`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Quellbitmap.  
  
 `maskBitmap`  
 Identifiziert die monochrome Maskenbitmap in Kombination mit der Farbbitmap in den Quellgerätekontext an.  
  
 `xMask`  
 Gibt den horizontalen Pixel-Offset für den angegebenen Maskenbitmap der `maskBitmap` Parameter.  
  
 `yMask`  
 Gibt den vertikalen Pixel-Offset für den angegebenen Maskenbitmap der `maskBitmap` Parameter.  
  
 *dwRop*  
 Gibt die Vordergrund- und Hintergrundfarben ternäre rastervorgangscode, die die Funktion verwendet wird, um die Kombination von Quell-und Zieldaten zu steuern. Der Hintergrund Raster Vorgangscode wird in das höchstwertige Byte das hohe Word diesen Wert gespeichert. der Vordergrund Raster Vorgangscode wird in das hohe Word dieses Werts das niedrige Byte gespeichert. das niedrige Word dieses Werts wird ignoriert, und sollte&0; (null) sein. Das Makro **MAKEROP4** solche Kombinationen von Vordergrund- und rastervorgangscode erstellt. Finden Sie im Abschnitt "Hinweise" eine Erläuterung der Vordergrund- und Hintergrundfarbe im Kontext dieser Funktion. Finden Sie unter der `BitBlt` Member-Funktion eine Liste der allgemeinen rastervorgangscode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Wert 1 in der angegebenen Maske `maskBitmap` gibt an, dass der Vordergrund Raster Vorgangscode angegeben *DwRop* an dieser Stelle angewendet werden soll. Wert 0 in der Maske gibt an, dass der Hintergrund Raster Vorgangscode angegeben *DwRop* an dieser Stelle angewendet werden soll. Wenn die Rasteroperationen Quelle erforderlich ist, muss die Maske Rechteck Quellrechtecks abdecken. Wenn dies nicht der Fall ist, schlägt die Funktion fehl. Die Rasteroperationen keine Datenquelle erforderlich ist, muss das Rechteck Maske das Zielrechteck erstreckt. Wenn dies nicht der Fall ist, schlägt die Funktion fehl.  
  
 Wenn eine Drehung oder Verbiegen Transformation für den Quellgerätekontext gilt, wenn diese Funktion aufgerufen wird, tritt ein Fehler auf. Andere Typen von Transformationen sind jedoch zulässig.  
  
 Wenn sich die Farbenformate für die Quelle, Muster und Zielbitmaps unterscheiden, konvertiert diese Funktion das Muster Quellformat oder beides mit dem Ziel übereinstimmt. Wenn die Maskenbitmap nicht um eine monochrome Bitmap ist, tritt ein Fehler auf. Wenn eine erweiterte Metadatei aufgezeichnet werden wird, ein Fehler auftritt (und die Funktion gibt 0 zurück) der Quellgerätekontext eine EMF-Gerätekontext an. Nicht alle Geräte unterstützen `MaskBlt`. Eine Anwendung sollte Aufrufen `GetDeviceCaps` zu bestimmen, ob ein Gerät diese Funktion unterstützt. Wenn keine Maskenbitmap angegeben wird, verhält sich diese Funktion wie `BitBlt`, mit dem Vordergrund Raster Vorgangscode. Das Pixel offsets in der Maske Bitmap-Zuordnung zu dem Punkt (0,0) in den Quellgerätekontext-Bitmap. Dies ist nützlich für Fälle, in denen eine Maskenbitmap für eine Reihe von Masken enthält. eine Anwendung kann problemlos wenden Sie zum Maske Blitting durch Anpassen der Pixel-Offsets und Größen Rechteck an `MaskBlt`.  
  
##  <a name="a-namemodifyworldtransforma--cdcmodifyworldtransform"></a><a name="modifyworldtransform"></a>CDC::ModifyWorldTransform  
 Ändert die globale Transformation für einen Gerätekontext, der mit dem angegebenen Modus.  
  
```  
BOOL ModifyWorldTransform(
    const XFORM& rXform,  
    DWORD iMode);
```  
  
### <a name="parameters"></a>Parameter  
 `rXform`  
 Ein Verweis auf eine [XFORM](http://msdn.microsoft.com/library/windows/desktop/dd145228) Struktur verwendet, um die globale Transformation für den angegebenen Gerätekontext zu ändern.  
  
 `iMode`  
 Gibt an, wie die Transformationsdaten die aktuellen globalen Transformation ändert. Eine Liste der Werte, die für diesen Parameter finden Sie unter [ModifyWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd145060).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL bei Erfolg zurück.  
  
 Gibt 0 bei einem Fehler zurück.  
  
 Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode umschließt die Windows GDI-Funktion [ModifyWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd145060).  
  
##  <a name="a-namemovetoa--cdcmoveto"></a><a name="moveto"></a>CDC::MoveTo  
 Verschiebt die aktuelle Position von festgelegten Punkt *x* und *y* (oder `point`).  
  
```  
CPoint MoveTo(
    int x,  
    int y);  
  
CPoint MoveTo(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate der neuen Position.  
  
 *y*  
 Gibt die logische y-Koordinate der neuen Position.  
  
 `point`  
 Gibt die neue Position. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Die x- und y-Koordinaten der vorherigen Position als ein `CPoint` Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRect::CenterPoint](../../atl-mfc-shared/reference/crect-class.md#centerpoint).  
  
##  <a name="a-nameoffsetcliprgna--cdcoffsetcliprgn"></a><a name="offsetcliprgn"></a>CDC::OffsetClipRgn  
 Verschiebt den Ausschneidebereich des Gerätekontexts durch den angegebenen Offsets.  
  
```  
int OffsetClipRgn(
    int x,  
    int y);  
  
int OffsetClipRgn(SIZE size);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die Anzahl der logischen Einheiten verschieben nach links oder rechts.  
  
 *y*  
 Gibt die Anzahl der logischen Einheiten nach oben oder unten zu verschieben.  
  
 `size`  
 Gibt den Betrag für den offset.  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Bereich Typ. Einer der folgenden Werte sind möglich:  
  
- **COMPLEXREGION** Ausschneidebereich hat Ränder überlappen.  
  
- **Fehler** Gerätekontext ist ungültig.  
  
- **NULLREGION** Ausschneidebereich ist leer.  
  
- **SIMPLEREGION** Ausschneidebereich besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die-Funktion verschiebt die Region *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse.  
  
##  <a name="a-nameoffsetviewportorga--cdcoffsetviewportorg"></a><a name="offsetviewportorg"></a>CDC::OffsetViewportOrg  
 Ändert die Koordinaten des Ursprungs Viewport relativ zu den Koordinaten des Ursprungs des aktuellen Viewports an.  
  
```  
virtual CPoint OffsetViewportOrg(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Gibt die Anzahl der Geräteeinheiten X-Koordinate für den aktuellen Ursprung hinzu.  
  
 `nHeight`  
 Gibt die Anzahl der Geräteeinheiten, den aktuellen Ursprung y-Koordinate hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Viewport Ursprung (in logische Koordinaten) als ein `CPoint` Objekt.  
  
##  <a name="a-nameoffsetwindoworga--cdcoffsetwindoworg"></a><a name="offsetwindoworg"></a>CDC::OffsetWindowOrg  
 Ändert die Koordinaten des Ursprungs Fenster relativ zu den Koordinaten des Ursprungs des aktuellen Fensters.  
  
```  
CPoint OffsetWindowOrg(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Gibt die Anzahl der logischen Einheiten des aktuellen Ursprungs X-Koordinate hinzu.  
  
 `nHeight`  
 Gibt die Anzahl der logischen Einheiten des aktuellen Ursprungs y-Koordinate hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Ursprungspunkt des Fensters (in logischen Koordinaten) als ein `CPoint` Objekt.  
  
##  <a name="a-nameoperatorhdca--cdcoperator-hdc"></a><a name="operator_hdc"></a>CDC::Operator HDC  
 Verwenden Sie diesen Operator Handle für den Gerätekontext des abzurufenden der `CDC` Objekt.  
  
```  
operator HDC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Falls erfolgreich, das Handle für das Gerät Context-Objekt. andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Handle verwenden, Windows-APIs direkt aufrufen.  
  
##  <a name="a-namepaintrgna--cdcpaintrgn"></a><a name="paintrgn"></a>CDC::PaintRgn  
 Füllt den Bereich mit dem angegebenen `pRgn` mit dem aktuellen Pinsel.  
  
```  
BOOL PaintRgn(CRgn* pRgn);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Identifiziert den Bereich ausgefüllt werden. Die Koordinaten für den angegebenen Bereich sind in logischen Einheiten angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
##  <a name="a-namepatblta--cdcpatblt"></a><a name="patblt"></a>CDC::PatBlt  
 Erstellt ein Bitmuster auf dem Gerät.  
  
```  
BOOL PatBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate der oberen linken Ecke des Rechtecks, die das Muster zu erhalten.  
  
 *y*  
 Gibt die logische y-Koordinate der oberen linken Ecke des Rechtecks, die das Muster zu erhalten.  
  
 `nWidth`  
 Gibt die Breite (in logischen Einheiten) des Rechtecks, das das Muster zu erhalten.  
  
 `nHeight`  
 Gibt die Höhe (in logischen Einheiten) des Rechtecks, das das Muster zu erhalten.  
  
 *dwRop*  
 Gibt den Code für die Raster-Vorgangs. Raster-Operationscodes (-RPC-Vorgänge) definieren, wie GDI Farben in Ausgabevorgängen kombiniert, die ein aktueller Pinsel, eine mögliche Quellbitmap und eine Zielbitmap beteiligt sind. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **PATCOPY** Muster Zielbitmap kopiert.  
  
- **PATINVERT** Zielbitmap mithilfe des booleschen XOR-Operators mit Muster kombiniert.  
  
- **DSTINVERT** Hierdurch wird die Zielbitmap.  
  
- **BLACKNESS** Ausgabe Schwarz.  
  
- **WHITENESS** Ausgabe weiß.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Das Muster ist eine Kombination aus den ausgewählten Pinsel und das Muster bereits auf dem Gerät. Das Raster Vorgangscode angegebenen *DwRop* definiert, wie die Muster kombiniert werden sollen. Die Raster-Vorgänge für diese Funktion aufgeführt sind, eine beschränkte Teilmenge des vollständigen 256 ternäre Raster-Operationscodes. Insbesondere kann ein Raster-Vorgangs-Code, der auf eine Datenquelle verweist verwendet werden.  
  
 Nicht alle Gerätekontexte unterstützen die `PatBlt` Funktion. Bestimmt, ob ein Gerätekontext unterstützt `PatBlt`, rufen Sie die `GetDeviceCaps` Memberfunktion mit der **RASTERCAPS** index, und überprüfen Sie den Rückgabewert für die **RC_BITBLT** Flag.  
  
##  <a name="a-namepiea--cdcpie"></a><a name="pie"></a>CDC::PIE  
 Zeichnet einen kreisförmigen Keil durch Zeichnen eines elliptischen Bogens, dessen Mittelpunkt und zwei Endpunkte durch Linien verbunden sind.  
  
```  
BOOL Pie(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3,  
    int x4,  
    int y4);

 
BOOL Pie(
    LPCRECT lpRect,
    POINT ptStart,
    POINT ptEnd);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des umschließenden Rechtecks (in logischen Einheiten) an.  
  
 *x3*  
 Gibt die X-Koordinate des Anfangspunkts des Bogens, (in logischen Einheiten) an. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `y3`  
 Gibt die y-Koordinate des Anfangspunkts des Bogens, (in logischen Einheiten) an. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `x4`  
 Gibt die X-Koordinate des Endpunkts des Bogens, (in logischen Einheiten) an. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `y4`  
 Gibt die y-Koordinate des Endpunkts des Bogens, (in logischen Einheiten) an. Dieser Punkt muss nicht genau auf den Bogen liegen.  
  
 `lpRect`  
 Gibt das umschließende Rechteck. Übergeben Sie entweder ein `CRect` Objekt oder einen Zeiger auf eine `RECT` Struktur für diesen Parameter.  
  
 `ptStart`  
 Gibt den Anfangspunkt des Bogens an. Dieser Punkt muss nicht genau auf den Bogen liegen. Übergeben Sie entweder ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt für diesen Parameter.  
  
 `ptEnd`  
 Gibt den Endpunkt des Bogens. Dieser Punkt muss nicht genau auf den Bogen liegen. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Mitte des Bogens steht im Mittelpunkt des umschließenden Rechtecks, das vom angegebenen `x1`, `y1`, `x2`, und `y2` (oder `lpRect`). Die Anfangs- und Endpunkt des Bogens werden angegeben, indem *X3*, `y3`, `x4`, und `y4` (oder `ptStart` und `ptEnd`).  
  
 Der Bogen wird mit dem ausgewählten Stift, verschieben gegen den Uhrzeigersinn gezeichnet. Zwei zusätzliche Linien werden von jedem Endpunkt des Bogens Center gezeichnet. Der Bereich Kreissegmente ist mit dem aktuellen Pinsel gefüllt. Wenn *X3* gleich `x4` und `y3` gleich `y4`, das Ergebnis ist eine Ellipse mit einer einzelnen Linie von der Mitte der Ellipse zum Punkt ( *X3*, `y3`) oder ( `x4`, `y4`).  
  
 In der Abbildung gezeichnet, die durch diese Funktion bis zu erweitert, aber umfasst nicht die rechten und unteren Koordinaten. Dies bedeutet, dass die Höhe der Abbildung `y2` – `y1` und die Breite der Abbildung ist `x2` – `x1`. Die Breite und die Höhe des umschließenden Rechtecks müssen größer als 2 Einheiten und weniger als 32.767 Einheiten sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#37;](../../mfc/codesnippet/cpp/cdc-class_9.cpp)]  
  
##  <a name="a-nameplaymetafilea--cdcplaymetafile"></a><a name="playmetafile"></a>CDC::PlayMetaFile  
 Der Inhalt der angegebenen Metadatei wiedergegeben auf den Gerätekontext.  
  
```  
BOOL PlayMetaFile(HMETAFILE hMF);

 
BOOL PlayMetaFile(
    HENHMETAFILE hEnhMetaFile,  
    LPCRECT lpBounds);
```  
  
### <a name="parameters"></a>Parameter  
 *hMF*  
 Identifiziert die Metadatei wiedergegeben werden soll.  
  
 *hEnhMetaFile*  
 Identifiziert die erweiterte Metadatei an.  
  
 `lpBounds`  
 Verweist auf eine `RECT` Struktur oder ein `CRect` -Objekt, das die Koordinaten des umschließenden Rechtecks verwendet, um das Bild anzuzeigen. Die Koordinaten werden in logischen Einheiten angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Metadatei kann oft wiedergegeben werden.  
  
 Die zweite Version der `PlayMetaFile` zeigt das Bild in der angegebenen EMF-Datei gespeichert. Wenn eine Anwendung ruft die zweite Version der `PlayMetaFile`, Windows verwendet den Grafikrahmen im EMF-Header, um das Bild auf das Rechteck, das auf den zuzuordnen der `lpBounds` Parameter. (Dieses Bild möglicherweise verbogen oder gedreht festlegen die globale Transformation in das Ausgabegerät vor dem Aufruf von `PlayMetaFile`.) Punkte entlang der Ränder des Rechtecks sind in der Abbildung enthalten. Ein EMF-Bild kann durch die Definition des Ausschneidebereichs in das Ausgabegerät vor der Wiedergabe EMF abgeschnitten.  
  
 EMF eine optionale Palette enthält, kann eine Anwendung konsistente Farben erzielen, indem Sie das Einrichten einer Farbpalette auf dem Ausgabegerät vor dem Aufrufen der zweiten Version `PlayMetaFile`. Verwenden Sie zum Abrufen der optionalen Palette der **GetEnhMetaFilePaletteEntries** Windows-Funktion. Erweiterte Metadatei kann in eine neu erstellte erweiterte Metadatei eingebettet werden, durch Aufrufen der zweiten Version `PlayMetaFile` und Wiedergabe von der Quelle, die erweiterte Metadatei im Gerätekontext für das neue erweiterte Metadatei.  
  
 Mit dieser Funktion werden die Zustände des Gerätekontexts Ausgabe beibehalten. Durch diese Funktion wird ein Objekt erstellt, jedoch nicht in der erweiterten Metadatei gelöscht gelöscht. Um diese Funktion zu beenden, kann eine Anwendung Aufrufen der **CancelDC** Windows-Funktion von einem anderen Thread zum Beenden des Vorgangs. In diesem Fall gibt die Funktion&0; (null) zurück.  
  
##  <a name="a-nameplgblta--cdcplgblt"></a><a name="plgblt"></a>CDC::PlgBlt  
 Führt einen Bitblocktransfer der Farbdaten-Bits auf das angegebene Rechteck in den Quellgerätekontext an der angegebenen Parallelogramm unter den angegebenen Gerätekontext.  
  
```  
BOOL PlgBlt(
    LPPOINT lpPoint,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nWidth,  
    int nHeight,  
    CBitmap& maskBitmap,  
    int xMask,  
    int yMask);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoint`  
 Zeigt auf ein Array von drei Punkten in logischer Speicherplatz, der drei Ecken des Zielparallelogramms identifiziert. Der erste Punkt in dieses Array, das oben rechts auf den zweiten Punkt in diesem Array und der unteren linken Ecke dem dritten Punkt wird die linke obere Ecke des Quellrechtecks zugeordnet. Der unteren rechten Ecke des Quellrechtecks wird die implizite vierten Punkt in der Parallelogramm zugeordnet.  
  
 `pSrcDC`  
 Gibt den Quellgerätekontext an.  
  
 `xSrc`  
 Gibt die X-Koordinate, in logischen Einheiten von der linken oberen Ecke des Quellrechtecks.  
  
 `ySrc`  
 Gibt die y-Koordinate, in logischen Einheiten von der linken oberen Ecke des Quellrechtecks.  
  
 `nWidth`  
 Gibt die Breite in logischen Einheiten des Quellrechtecks an.  
  
 `nHeight`  
 Gibt die Höhe in logischen Einheiten des Quellrechtecks an.  
  
 `maskBitmap`  
 Gibt eine optionale monochrome Bitmap, die verwendet wird, um die Farben des Quellrechtecks.  
  
 `xMask`  
 Gibt die X-Koordinate der oberen linken Ecke der monochrome Bitmap an.  
  
 `yMask`  
 Gibt die y-Koordinate der oberen linken Ecke der monochrome Bitmap an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Handle der angegebenen Bitmaske gültige monochrome Bitmap bezeichnet, verwendet die Funktion diese Bitmap zum Maskieren der Bits der Farbdaten vom Quellrechtecks.  
  
 Vierten Scheitelpunkts des Parallelogramms (D) wird definiert, indem behandelt die ersten drei Punkte (A, B und C) als Vektoren und computing D = B + C – A.  
  
 Wenn die Bitmaske vorhanden ist, gibt der Wert 1 in der Maske, die Pixelfarbe Quelle zum Ziel kopiert werden sollen. Der Wert 0 in der Maske gibt an, dass die Ziel-Pixelfarbe nicht geändert werden.  
  
 Ist das Rechteck Maske kleiner als die Quelle und Ziel Rechtecke, repliziert die Funktion der Maskenmuster.  
  
 Skalierung, Verschiebung und Reflektion Transformationen sind in den Quellgerätekontext zulässig. Allerdings sind die Drehung und Neigung Transformationen nicht. Wenn die Maskenbitmap nicht um eine monochrome Bitmap ist, tritt ein Fehler auf. Der streckmodus für Zielgerätekontext wird verwendet, um zu bestimmen, wie gestreckt oder komprimiert die Pixel, wenn dies erforderlich ist. Wenn eine erweiterte Metadatei aufgezeichnet wird, tritt ein Fehler auf, wenn die Quellgerätekontext eine EMF-Gerätekontext identifiziert.  
  
 Die Zielkoordinaten werden gemäß dem Zielgerätekontext umgewandelt. Die Quellkoordinaten werden gemäß dem Quellgerätekontext umgewandelt. Wenn die Umwandlung einer Drehung oder Verbiegen verfügt, wird ein Fehler zurückgegeben. Wenn die Ziel- und Rechtecke nicht das gleiche Farbformat verfügen `PlgBlt` Quellrechtecks Zielrechtecks entsprechend konvertiert. Nicht alle Geräte unterstützen `PlgBlt`. Weitere Informationen finden Sie unter der Beschreibung der **RC_BITBLT** Raster-Funktion in der `CDC::GetDeviceCaps` Member-Funktion.  
  
 Wenn die Quelle und Ziel-Gerätekontexte inkompatible Geräte darstellen `PlgBlt` gibt einen Fehler zurück.  
  
##  <a name="a-namepolybeziera--cdcpolybezier"></a><a name="polybezier"></a>CDC::PolyBezier  
 Zeichnet eine oder mehrere Bzier Splines.  
  
```  
BOOL PolyBezier(
    const POINT* lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von [Punkt](../../mfc/reference/point-structure1.md) -Datenstrukturen, enthalten die Endpunkte und die Steuerpunkte der der Spline(s).  
  
 `nCount`  
 Gibt die Anzahl der Punkte in der `lpPoints` Array. Dieser Wert muss eine mehr als drei Mal der Anzahl der Splines gezeichnet werden, da jede Bzier Spline zwei Kontrollpunkte und einen Endpunkt und die anfängliche Splinekurve erfordert erfordert einen zusätzlichen Ausgangspunkt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zeichnet kubische Bzier Splines mithilfe der Endpunkte und die Steuerpunkte, die anhand der `lpPoints` Parameter. Der erste Spline wird vom ersten Punkt bis zum vierten Punkt gezeichnet mithilfe der zweite und dritte Punkt als Kontrollpunkte verwendet werden. Jede nachfolgende Spline in der Sequenz benötigt genau drei weitere Punkte: den Endpunkt des vorherigen Splines dient als Ausgangspunkt für die nächsten beiden Punkte sind Kontrollpunkte und die dritte ist der Endpunkt.  
  
 Die aktuelle Position ist weder verwendet noch aktualisiert, indem die `PolyBezier` Funktion. In der Abbildung wurde nicht ausgefüllt. Diese Funktion zeichnet Linien mit dem aktuellen Stift.  
  
##  <a name="a-namepolybeziertoa--cdcpolybezierto"></a><a name="polybezierto"></a>CDC::PolyBezierTo  
 Zeichnet eine oder mehrere Bzier Splines.  
  
```  
BOOL PolyBezierTo(
    const POINT* lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von [Punkt](../../mfc/reference/point-structure1.md) zeigt Datenstrukturen, die die Endpunkte und das Steuerelement enthält.  
  
 `nCount`  
 Gibt die Anzahl der Punkte in der `lpPoints` Array. Dieser Wert muss drei Mal der Anzahl der Splines gezeichnet werden, da für jeden Spline Bzier zwei Kontrollpunkte und ein Endpunkt erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zeichnet kubische Bzier Splines mithilfe der angegebenen Kontrollpunkten der `lpPoints` Parameter. Der erste Spline wird von der aktuellen Position dem dritten Punkt mit den ersten beiden Punkte als Steuerpunkte gezeichnet. Für jeden nachfolgenden Spline die Funktion genau drei weitere Punkte benötigt, und verwendet den Endpunkt des vorherigen Splines als Ausgangspunkt für die nächsten. `PolyBezierTo`Verschiebt die aktuelle Position und dem Endpunkt des letzten Bzier Splines. In der Abbildung wurde nicht ausgefüllt. Diese Funktion zeichnet Linien mit dem aktuellen Stift.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC:: beginpath](#beginpath).  
  
##  <a name="a-namepolydrawa--cdcpolydraw"></a><a name="polydraw"></a>CDC::PolyDraw  
 Zeichnet eine Reihe von Liniensegmenten und Bzier Splines.  
  
```  
BOOL PolyDraw(
    const POINT* lpPoints,  
    const BYTE* lpTypes,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von [Punkt](../../mfc/reference/point-structure1.md) Datenstrukturen, die Endpunkte enthält, die für jede Zeile Segment und die Endpunkte und Kontrollpunkte für jeden Spline Bzier.  
  
 `lpTypes`  
 Zeigt auf ein Array, der angibt, wie jede zeigen die `lpPoints` Array verwendet wird. Die folgenden Werte sind möglich:  
  
- **PT_MOVETO** gibt an, dass dieser Punkt getrennte Abbildung beginnt. Dieser Punkt wird die neue Position.  
  
- **PT_LINETO** gibt an, dass eine Linie von der aktuellen Position bis zu diesem Punkt gezeichnet werden soll, klicken Sie dann auf die neue Position wird.  
  
- **PT_BEZIERTO** gibt an, dass dieser Punkt ein Kontrollpunkt oder den Endpunkt für einen Spline Bzier ist.  
  
 **PT_BEZIERTO** Typen werden immer in drei Gruppen erfolgen. Die aktuelle Position definiert den Ausgangspunkt für den Spline Bzier. Die ersten beiden **PT_BEZIERTO** sind die Steuerpunkte, und die dritte **PT_BEZIERTO** Punkt ist der Endpunkt. Der Endpunkt wird die neue Position. Wenn nicht vorhanden drei aufeinander folgende sind **PT_BEZIERTO** Punkte, eine Fehlermeldung ausgegeben.  
  
     Ein **PT_LINETO** oder **PT_BEZIERTO** Typ kann mit der folgenden Konstanten mit dem bitweisen Operator kombiniert werden, oder um anzugeben, dass der entsprechende Punkt der letzte Punkt in einer Abbildung und in der Abbildung ist geschlossen werden:  
  
- **PT_CLOSEFIGURE** gibt, die in der Abbildung automatisch, nachdem geschlossen wird die **PT_LINETO** oder **PT_BEZIERTO** Geben Sie für diesen Punkt erfolgt. Wird eine Linie an diesem Punkt an die aktuelle **PT_MOVETO** oder `MoveTo` zeigen.  
  
     Dieses Flag gibt zusammen mit der **PT_LINETO** Typ für eine Linie oder mit der **PT_BEZIERTO** Typ der Endpunkt für einen Spline Bzier unter Verwendung des bitweisen `OR` Operator. Die aktuelle Position wird auf den Endpunkt, der die abschließende Zeile festgelegt.  
  
 `nCount`  
 Gibt die Gesamtzahl der Punkte in der `lpPoints` identisch mit der Anzahl der Bytes im array der `lpTypes` Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion kann verwendet werden, zum Zeichnen von getrennten Zahlen anstelle von aufeinander folgende Aufrufe von `CDC::MoveTo`, `CDC::LineTo`, und `CDC::PolyBezierTo` Memberfunktionen. Werden die Zeilen und Splines gezeichnet mit dem aktuellen Stift und Zahlen nicht aufgefüllt werden. Befindet sich der aktive Pfad durch den Aufruf gestartet der `CDC::BeginPath` Memberfunktion `PolyDraw` fügt dem Pfad hinzu. Punkte der `lpPoints` Array und im `lpTypes` gibt an, ob jeder Punkt gehört eine `CDC::MoveTo`, `CDC::LineTo`, oder eine **CDC::BezierTo** Vorgang. Es ist auch möglich, Formen zu schließen. Diese Funktion aktualisiert die aktuelle Position.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC:: beginpath](#beginpath).  
  
##  <a name="a-namepolygona--cdcpolygon"></a><a name="polygon"></a>CDC::Polygon  
 Zeichnet ein Vieleck, bestehend aus zwei oder mehr Punkten (Scheitelpunkte) Linien, die mit dem aktuellen Stift.  
  
```  
BOOL Polygon(
    LPPOINT lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Zeigt auf ein Array von Punkten, die die Scheitelpunkte des Polygons. Jedem Punkt im Array ist ein **zeigen** Struktur oder ein `CPoint` Objekt.  
  
 `nCount`  
 Gibt die Anzahl der Scheitelpunkte im Array an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Das System schließt das Polygon automatisch, ggf. durch Zeichnen einer Linie zwischen dem letzten Scheitelpunkt zum ersten.  
  
 Der aktuelle Polygon Füllmodus kann abgerufen oder festgelegt werden, mit der `GetPolyFillMode` und `SetPolyFillMode` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#38;](../../mfc/codesnippet/cpp/cdc-class_10.cpp)]  
  
##  <a name="a-namepolylinea--cdcpolyline"></a><a name="polyline"></a>CDC::Polyline  
 Zeichnet eine Reihe von Liniensegmenten, die zwischen den Punkten, die durch angegebene `lpPoints`.  
  
```  
BOOL Polyline(
    LPPOINT lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von **Punkt** Strukturen oder `CPoint` Objekten verbunden werden.  
  
 `nCount`  
 Gibt die Anzahl der Punkte im Array an. Dieser Wert muss mindestens 2 sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Zeilen werden aus den ersten Punkt durch die nachfolgenden Punkte, die mit dem aktuellen Stift gezeichnet. Im Gegensatz zu den `LineTo` -Memberfunktion, die `Polyline` Funktion weder verwendet noch aktualisiert die derzeitige Position.  
  
 Weitere Informationen finden Sie unter [Polylinie](http://msdn.microsoft.com/library/windows/desktop/dd162815) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namepolylinetoa--cdcpolylineto"></a><a name="polylineto"></a>CDC::PolylineTo  
 Zeichnet eine oder mehrere gerade Linien.  
  
```  
BOOL PolylineTo(
    const POINT* lpPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von [Punkt](../../mfc/reference/point-structure1.md) Datenstrukturen, die die Eckpunkte der Linie enthält.  
  
 `nCount`  
 Gibt die Anzahl der Punkte im Array an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wird eine Linie von der aktuellen Position und dem ersten Punkt anhand der `lpPoints` Parameter mit dem aktuellen Stift. Für jede zusätzliche Zeile zeichnet die Funktion vom Endpunkt der vorherigen Zeile an der nächsten von `lpPoints`. `PolylineTo`Verschiebt die aktuelle Position zum Endpunkt der letzten Zeile. Wenn die Liniensegmente gezeichnet, die von dieser Funktion eine geschlossene bilden, wird in der Abbildung nicht ausgefüllt.  
  
##  <a name="a-namepolypolygona--cdcpolypolygon"></a><a name="polypolygon"></a>CDC::PolyPolygon  
 Erstellt zwei oder mehreren Polygonen, die mit den aktuellen Polygon Füllmodus aufgefüllt werden.  
  
```  
BOOL PolyPolygon(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von **Punkt** Strukturen oder `CPoint` -Objekten, die die Eckpunkte der Polygone definieren.  
  
 `lpPolyCounts`  
 Zeigt auf ein Array von Ganzzahlen, von denen jede gibt an, die Anzahl der Punkte in einem der Polygone in der `lpPoints` Array.  
  
 `nCount`  
 Die Anzahl der Einträge in der `lpPolyCounts` Array. Diese Zahl gibt die Anzahl von Polygonen, gezeichnet werden soll. Dieser Wert muss mindestens 2 sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Polygone möglicherweise getrennten oder überlappende.  
  
 Jedes Polygon angegeben, die in einem Aufruf der `PolyPolygon` Funktion muss geschlossen werden. Im Gegensatz zu Polygone erstellt, indem die **Polygon** -Memberfunktion, die Polygone erstellt `PolyPolygon` nicht automatisch geschlossen.  
  
 Die Funktion erstellt zwei oder mehreren Polygonen. Um ein einzelnes Polygon zu erstellen, eine Anwendung verwenden, sollten die **Polygon** Member-Funktion.  
  
 Der aktuelle Polygon Füllmodus kann abgerufen oder festgelegt werden, mit der `GetPolyFillMode` und `SetPolyFillMode` Memberfunktionen.  
  
##  <a name="a-namepolypolylinea--cdcpolypolyline"></a><a name="polypolyline"></a>CDC::PolyPolyline  
 Zeichnet mehrere Reihe verbundener Liniensegmente.  
  
```  
BOOL PolyPolyline(
    const POINT* lpPoints,  
    const DWORD* lpPolyPoints,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Zeigt auf ein Array von Strukturen, die die Eckpunkte der Polylinien enthält. Die Polylinien werden nacheinander festgelegt.  
  
 `lpPolyPoints`  
 Verweist auf ein Array von Variablen, die die Anzahl der Punkte in der `lpPoints` Array für das entsprechende Polygon. Jeder Eintrag muss größer oder gleich 2 sein.  
  
 `nCount`  
 Gibt die Gesamtanzahl der Zahlen in der `lpPolyPoints` Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Liniensegmente werden mit dem aktuellen Stift gezeichnet. Die Zahlen, die die Segmente gebildet werden nicht aufgefüllt. Die aktuelle Position ist weder verwendet noch von dieser Funktion aktualisiert.  
  
##  <a name="a-nameptvisiblea--cdcptvisible"></a><a name="ptvisible"></a>CDC::PtVisible  
 Bestimmt, ob der angegebene Punkt innerhalb des Clippingbereichs des Gerätekontexts.  
  
```  
virtual BOOL PtVisible(
    int x,  
    int y) const;  
  
BOOL PtVisible(POINT point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Punkts an.  
  
 *y*  
 Gibt die logische y-Koordinate des Punkts an.  
  
 `point`  
 Gibt den Punkt in logische Koordinaten zu überprüfen. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der angegebene Punkt innerhalb des Clippingbereichs ist; andernfalls 0.  
  
##  <a name="a-namequeryaborta--cdcqueryabort"></a><a name="queryabort"></a>CDC::QueryAbort  
 Ruft die Abort-Funktion installiert, indem Sie die [SetAbortProc](#setabortproc) Memberfunktion für eine Anwendung zum Drucken und Abfragen, ob das Drucken beendet werden soll.  
  
```  
BOOL QueryAbort() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist ungleich NULL, wenn Drucken fortgesetzt werden soll, oder es keine Abbruchvorgangs ist. Es ist 0, wenn der Druckauftrag beendet werden sollen. Der Rückgabewert ist von der Abort-Funktion bereitgestellt.  
  
##  <a name="a-namerealizepalettea--cdcrealizepalette"></a><a name="realizepalette"></a>CDC::RealizePalette  
 Ordnet die Einträge aus der aktuellen logischen Palette der Systempalette.  
  
```  
UINT RealizePalette();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, wie viele Einträge in der logischen Palette verschiedene Einträge in der Systempalette zugeordnet wurden. Dies stellt die Anzahl der Einträge, die dieser Funktion zugeordnet, um die Änderungen in der Systempalette gerecht zu werden, da die logische Palette zuletzt realisiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Eine logische Farbpalette fungiert als Puffer zwischen Farbe-Intensive Anwendung und dem System, dem eine Anwendung verwenden, wie viele Farben je nach Bedarf, ohne zu stören, eigene Farben angezeigt oder mit Farben, die von anderen Fenstern angezeigt.  
  
 Verfügt ein Fenster den Eingabefokus und die Aufrufe `RealizePalette`, Windows stellt sicher, dass das Fenster alle angeforderten Farben, bis die maximale Anzahl gleichzeitig zur Verfügung stehen, auf dem Bildschirm angezeigt werden. Windows zeigt auch die Farben, die in das Fenster Palette durch Vergleich mit verfügbaren Farben nicht gefunden.  
  
 Darüber hinaus entspricht Windows die Farben von inaktiven Fenstern, die die Funktion so weit wie möglich an die verfügbaren Farben aufrufen angefordert. Dadurch wird die unerwünschte Änderungen in den Farben im inaktiven Fenstern erheblich reduziert.  
  
##  <a name="a-namerectanglea--cdcrectangle"></a><a name="rectangle"></a>CDC::Rectangle  
 Zeichnet ein Rechteck mit dem aktuellen Stift.  
  
```  
BOOL Rectangle(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
BOOL Rectangle(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `lpRect`  
 Gibt das Rechteck in logischen Einheiten. Übergeben Sie entweder ein `CRect` Objekt oder einen Zeiger auf eine `RECT` Struktur für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Das Innere des Rechtecks wird mit dem aktuellen Pinsel gefüllt.  
  
 Das Rechteck bis zu erweitert, jedoch keine, die rechten und unteren Koordinaten. Dies bedeutet, dass die Höhe des Rechtecks `y2` – `y1` und die Breite des Rechtecks ist `x2` – `x1`. Die Breite und die Höhe eines Rechtecks müssen größer als 2 Einheiten und weniger als 32.767 Einheiten sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView Nr.&39;](../../mfc/codesnippet/cpp/cdc-class_11.cpp)]  
  
##  <a name="a-namerectvisiblea--cdcrectvisible"></a><a name="rectvisible"></a>CDC::RectVisible  
 Bestimmt, ob der Ausschneidebereich Anzeigekontext einen beliebigen Teil des angegebenen Rechtecks liegt.  
  
```  
virtual BOOL RectVisible(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder ein `CRect` -Objekt, das die logischen Koordinaten des angegebenen Rechtecks enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Teil des angegebenen Rechteck innerhalb des Ausschneidebereichs liegt; andernfalls 0.  
  
##  <a name="a-namereleaseattribdca--cdcreleaseattribdc"></a><a name="releaseattribdc"></a>CDC::ReleaseAttribDC  
 Rufen Sie diese Memberfunktion festzulegende `m_hAttribDC` auf **NULL**.  
  
```  
virtual void ReleaseAttribDC();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies führt nicht dazu, dass ein **trennen** auftreten. Der Gerätekontext Ausgabe angefügt ist das `CDC` -Objekt, und es können getrennt werden.  
  
##  <a name="a-namereleaseoutputdca--cdcreleaseoutputdc"></a><a name="releaseoutputdc"></a>CDC::ReleaseOutputDC  
 Rufen Sie diese Memberfunktion zum Festlegen der `m_hDC` Element **NULL**.  
  
```  
virtual void ReleaseOutputDC();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion kann nicht aufgerufen werden, wenn die Ausgabe-Gerätekontext zugeordnet ist die `CDC` Objekt. Verwenden der **trennen** Memberfunktion um den Ausgabe-Gerätekontext zu trennen.  
  
##  <a name="a-nameresetdca--cdcresetdc"></a><a name="resetdc"></a>CDC::ResetDC  
 Rufen Sie diese Memberfunktion auf den Gerätekontext, der vom Aktualisieren der `CDC` Objekt.  
  
```  
BOOL ResetDC(const DEVMODE* lpDevMode);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDevMode*  
 Ein Zeiger auf ein Windows `DEVMODE` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Gerätekontext wird aktualisiert, aus den Informationen in den Fenstern `DEVMODE` Struktur. Diese Memberfunktion setzt nur die Attribut-Gerätekontext zurück.  
  
 Eine Anwendung wird in der Regel verwenden Sie die `ResetDC` Member-Funktion, wenn ein Fenster verarbeitet eine `WM_DEVMODECHANGE` Nachricht. Diese Member-Funktion können auch um die Ausrichtung oder Papier Klassen beim Drucken eines Dokuments zu ändern.  
  
 Sie können diese Memberfunktion der Treibername oder Gerätenamen ändern oder a-Port. Wenn der Benutzer die Verbindung mit Port oder Gerätename ändert, müssen Sie löschen den ursprünglichen Gerätekontext und erstellen einen neuen Gerätekontext mit den neuen Informationen.  
  
 Bevor Sie diese Memberfunktion aufrufen, müssen Sie sicherstellen, dass alle Objekte (mit Ausnahme des vordefinierten Objekte), die in den Gerätekontext ausgewählt wurden, ausgewählt wurden.  
  
##  <a name="a-namerestoredca--cdcrestoredc"></a><a name="restoredc"></a>CDC::RestoreDC  
 Stellt den Gerätekontext zum vorherigen Status identifizierten `nSavedDC`.  
  
```  
virtual BOOL RestoreDC(int nSavedDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nSavedDC`  
 Gibt den Gerätekontext wiederhergestellt werden. Es kann ein Wert, der von einem vorherigen zurückgegebene `SaveDC` -Funktionsaufruf. Wenn `nSavedDC` ist-1, die zuletzt gespeicherte Gerätekontext wird wiederhergestellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der angegebene Kontext wiederhergestellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `RestoreDC`Stellt den Gerätekontext, Statusinformationen von einem Stapel erstellt, die von früheren aufrufen, etwa durch die `SaveDC` -Memberfunktion.  
  
 Der Stapel kann die Statusinformationen für mehrere Gerätekontexte enthalten. Wenn der Kontext angegeben `nSavedDC` ist nicht am Anfang des Stapels `RestoreDC` löscht alle Zustandsinformationen zwischen den angegebenen Gerätekontext `nSavedDC` und dem oberen Rand des Stapels. Die gelöschte Informationen geht verloren.  
  
##  <a name="a-nameroundrecta--cdcroundrect"></a><a name="roundrect"></a>CDC::RoundRect  
 Zeichnet ein Rechteck mit abgerundeten Ecken, die mit dem aktuellen Stift.  
  
```  
BOOL RoundRect(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);

 
BOOL RoundRect(
    LPCRECT lpRect,
    POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des Rechtecks (in logischen Einheiten) an.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des Rechtecks (in logischen Einheiten) an.  
  
 *x3*  
 Gibt die Breite der Ellipse, die zum Zeichnen der abgerundeten Ecken (in logischen Einheiten) verwendet.  
  
 `y3`  
 Gibt die Höhe der Ellipse, die zum Zeichnen der abgerundeten Ecken (in logischen Einheiten) verwendet.  
  
 `lpRect`  
 Gibt das umschließende Rechteck in logischen Einheiten. Übergeben Sie entweder ein `CRect` Objekt oder einen Zeiger auf eine `RECT` Struktur für diesen Parameter.  
  
 `point`  
 Die X-Koordinate des `point` gibt die Breite der Ellipse, die zum Zeichnen der abgerundeten Ecken (in logischen Einheiten). Die y-Koordinate des `point` gibt die Höhe der Ellipse, die zum Zeichnen der abgerundeten Ecken (in logischen Einheiten). Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Das Innere des Rechtecks wird mit dem aktuellen Pinsel gefüllt.  
  
 In der Abbildung, die diese Funktion zeichnet bis zu erweitert, aber umfasst nicht die rechten und unteren Koordinaten. Dies bedeutet, dass die Höhe der Abbildung `y2` – `y1` und die Breite der Abbildung ist `x2` – `x1`. Die Höhe und die Breite des umschließenden Rechtecks müssen größer als 2 Einheiten und weniger als 32.767 Einheiten sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#40;](../../mfc/codesnippet/cpp/cdc-class_12.cpp)]  
  
##  <a name="a-namesavedca--cdcsavedc"></a><a name="savedc"></a>CDC::SaveDC  
 Speichert den aktuellen Zustand des Gerätekontexts durch Kopieren von Informationen (z. B. Ausschneidebereich ausgewählter Objekte und Zuordnungsmodus) einen Stapel von Windows verwaltet wird.  
  
```  
virtual int SaveDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die gespeicherten Gerätekontext angibt. Es ist 0, wenn ein Fehler auftritt. Dieser Wert kann verwendet werden, um durch Aufrufen den Gerätekontext wiederherstellen zurückgeben `RestoreDC`.  
  
### <a name="remarks"></a>Hinweise  
 Gespeicherte Gerätekontext kann später wiederhergestellt werden, mithilfe von `RestoreDC`.  
  
 `SaveDC`kann oft verwendet, um eine beliebige Anzahl von Status Gerätekontext zu speichern.  
  
##  <a name="a-namescaleviewportexta--cdcscaleviewportext"></a><a name="scaleviewportext"></a>CDC::ScaleViewportExt  
 Ändert die Viewport-Blöcken Bezug auf die aktuellen Werte.  
  
```  
virtual CSize ScaleViewportExt(
    int xNum,  
    int xDenom,  
    int yNum,  
    int yDenom);
```  
  
### <a name="parameters"></a>Parameter  
 `xNum`  
 Gibt die Menge, mit der aktuellen X-Block multipliziert.  
  
 `xDenom`  
 Gibt an, wie durch die dividiert des Ergebnis der Multiplikation der aktuellen X-Block durch den Wert der `xNum` Parameter.  
  
 `yNum`  
 Gibt die Menge, mit der aktuellen y-Block multipliziert.  
  
 `yDenom`  
 Gibt an, wie durch die dividiert des Ergebnis der Multiplikation der aktuellen y-Block durch den Wert der `yNum` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Viewport-Blöcke (in Geräteeinheiten) als ein `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formeln werden wie folgt geschrieben:  
  
 `xNewVE = ( xOldVE * xNum ) / xDenom`  
  
 `yNewVE = ( yOldVE * yNum ) / yDenom`  
  
 Die neue Ansicht Blöcke werden berechnet, indem die aktuelle Blöcke mit der angegebenen Zähler multipliziert und durch Teilen durch den angegebenen Nenner.  
  
##  <a name="a-namescalewindowexta--cdcscalewindowext"></a><a name="scalewindowext"></a>CDC::ScaleWindowExt  
 Ändert die Blöcke im Fenster relativ zum aktuellen Werte.  
  
```  
virtual CSize ScaleWindowExt(
    int xNum,  
    int xDenom,  
    int yNum,  
    int yDenom);
```  
  
### <a name="parameters"></a>Parameter  
 `xNum`  
 Gibt die Menge, mit der aktuellen X-Block multipliziert.  
  
 `xDenom`  
 Gibt an, wie durch die dividiert des Ergebnis der Multiplikation der aktuellen X-Block durch den Wert der `xNum` Parameter.  
  
 `yNum`  
 Gibt die Menge, mit der aktuellen y-Block multipliziert.  
  
 `yDenom`  
 Gibt an, wie durch die dividiert des Ergebnis der Multiplikation der aktuellen y-Block durch den Wert der `yNum` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Fenster Blöcke (in logischen Einheiten) als ein `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formeln werden wie folgt geschrieben:  
  
 `xNewWE = ( xOldWE * xNum ) / xDenom`  
  
 `yNewWE = ( yOldWE * yNum ) / yDenom`  
  
 Das neue Fenster Wertebereiche werden berechnet, indem die aktuelle Blöcke mit der angegebenen Zähler multipliziert und durch Teilen durch den angegebenen Nenner.  
  
##  <a name="a-namescrolldca--cdcscrolldc"></a><a name="scrolldc"></a>CDC::ScrollDC  
 Führt einen Bildlauf ein Rechtecks mit Bits, horizontal und vertikal.  
  
```  
BOOL ScrollDC(
    int dx,  
    int dy,  
    LPCRECT lpRectScroll,  
    LPCRECT lpRectClip,  
    CRgn* pRgnUpdate,  
    LPRECT lpRectUpdate);
```  
  
### <a name="parameters"></a>Parameter  
 `dx`  
 Gibt die Anzahl der Einheiten der horizontalen Bildlaufleiste.  
  
 *dy*  
 Gibt die Anzahl der Einheiten der vertikalen Bildlaufleiste.  
  
 `lpRectScroll`  
 Verweist auf die `RECT` Struktur oder `CRect` -Objekt, das die Koordinaten des fortlaufenden Rechtecks enthält.  
  
 `lpRectClip`  
 Verweist auf die `RECT` Struktur oder `CRect` -Objekt, das die Koordinaten der das Clippingrechteck enthält. Wenn dieses Rechteck ist kleiner als eine auf den ursprünglichen `lpRectScroll`, Bildlauf tritt nur in kleinere Rechtecks.  
  
 `pRgnUpdate`  
 Identifiziert den Bereich, der durch den fortlaufenden Prozess im Detail. Die `ScrollDC` Funktion dieser Region definiert; es ist nicht unbedingt ein Rechteck.  
  
 `lpRectUpdate`  
 Verweist auf die `RECT` Struktur oder `CRect` -Objekt, das die Koordinaten des Rechtecks empfängt, das Update Bildlaufbereich umschließt. Dies ist die größte rechteckigen Bereichs, der Vorgang erfordert. Die Werte in der Struktur oder das Objekt bei Rückgabe der Funktion sind in Clientkoordinaten, unabhängig vom Zuordnungsmodus für den angegebenen Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Bildlauf ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `lpRectUpdate` ist **NULL**, Windows Update Rechtecks keine Verarbeitung. Wenn beide `pRgnUpdate` und `lpRectUpdate` sind **NULL**, Windows Aktualisierungsbereich keine Verarbeitung. Wenn `pRgnUpdate` nicht **NULL**, Windows wird davon ausgegangen, dass sie einen gültigen Zeiger auf den Bereich, der durch den fortlaufenden Prozess im Detail enthält (definiert durch die `ScrollDC` Member-Funktion). Dem Aktualisierungsbereich zurückgegeben `lpRectUpdate` übergeben werden kann, um `CWnd::InvalidateRgn` bei Bedarf.  
  
 Eine Anwendung verwenden, sollten die `ScrollWindow` -Memberfunktion der Klasse `CWnd` Wenn es den gesamten Clientbereich eines Fensters einen Bildlauf durchführen, ist. Andernfalls sollten Sie verwenden `ScrollDC`.  
  
##  <a name="a-nameselectclippatha--cdcselectclippath"></a><a name="selectclippath"></a>CDC::SelectClipPath  
 Wählt den aktuellen Pfad als einen Ausschneidebereich für den Gerätekontext, der neue Region mit alle vorhandenen Ausschneidebereich kombinieren, mit dem angegebenen Modus.  
  
```  
BOOL SelectClipPath(int nMode);
```  
  
### <a name="parameters"></a>Parameter  
 `nMode`  
 Gibt an, wie der Pfad verwendet werden. Die folgenden Werte sind zulässig:  
  
- **RGN_AND** der neuen Ausschneidebereich Schnittpunkt (überlappenden Bereichen) des aktuellen Ausschneidebereichs und der aktuelle Pfad enthält.  
  
- **RGN_COPY** der neue Ausschneidebereich ist der aktuelle Pfad.  
  
- **RGN_DIFF** der neuen Ausschneidebereich enthält die Bereiche des aktuellen Ausschneidebereichs und der den aktuellen Pfad ausgeschlossen werden.  
  
- **RGN_OR** der neuen Ausschneidebereich Union (kombinierten Bereiche) des aktuellen Ausschneidebereichs und der aktuelle Pfad enthält.  
  
- **RGN_XOR** der neuen Ausschneidebereich enthält die Gesamtmenge des aktuellen Ausschneidebereichs und der aktuelle Pfad, jedoch ohne die überlappenden Bereiche.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Gekennzeichnete Gerätekontext muss einen geschlossenen Pfad enthalten.  
  
##  <a name="a-nameselectcliprgna--cdcselectcliprgn"></a><a name="selectcliprgn"></a>CDC::SelectClipRgn  
 Die angegebene Region als des aktuellen Ausschneidebereichs für den Gerätekontext ausgewählt.  
  
```  
int SelectClipRgn(CRgn* pRgn);

 
int SelectClipRgn(
    CRgn* pRgn,  
    int nMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Identifiziert den Bereich ausgewählt werden.  
  
-   Für die erste Version dieser Funktion, wenn dieser Wert **NULL**der gesamten Clientbereich ausgewählt ist, und Ausgabe wird in das Fenster immer noch abgeschnitten.  
  
-   Die zweite Version dieser Funktion dieses Handle kann **NULL** nur, wenn die **RGN_COPY** Modus angegeben ist.  
  
 `nMode`  
 Gibt den Vorgang ausgeführt werden. Es muss einer der folgenden Werte sein:  
  
- **RGN_AND** der neue Ausschneidebereich kombiniert die überlappenden Bereiche des aktuellen Ausschneidebereichs und der Region identifizierten `pRgn`.  
  
- **RGN_COPY** der neue Ausschneidebereich ist eine Kopie der identifizierten Region `pRgn`. Dies ist eine Funktion ist identisch mit der ersten Version von `SelectClipRgn`. Wenn die Region identifizierte `pRgn` ist **NULL**, der neuen Ausschneidebereich wird der Standard-Ausschneidebereich (ein null-Bereich).  
  
- **RGN_DIFF** der neue Ausschneidebereich kombiniert die Bereiche des aktuellen Ausschneidebereichs mit diesen Bereichen durch identifizierten ausgeschlossen `pRgn`.  
  
- **RGN_OR** der neue Ausschneidebereich kombiniert des aktuellen Ausschneidebereichs und der Region identifizierten `pRgn`.  
  
- **RGN_XOR** der neue Ausschneidebereich kombiniert des aktuellen Ausschneidebereichs und der Region identifizierten `pRgn` aber überlappenden Bereiche ausgeschlossen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bereichstyp. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** neue Ausschneidebereich hat Ränder überlappen.  
  
- **Fehler** Gerätekontext oder die Region ist ungültig.  
  
- **NULLREGION** neue Ausschneidebereich ist leer.  
  
- **SIMPLEREGION** neue Ausschneidebereich besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Es wird nur eine Kopie des ausgewählten Bereichs verwendet. Die Region selbst kann eine beliebige Anzahl von anderen Gerätekontexte ausgewählt werden, oder kann gelöscht werden.  
  
 Die Funktion wird davon ausgegangen, dass die Koordinaten für den angegebenen Bereich Geräteeinheiten angegeben werden. Einige Drucker unterstützen die Ausgabe von Text mit einer höheren Auflösung als Grafikgerät um die Genauigkeit erforderlich, um Text Metriken express beibehalten. Diese Geräte Berichten Geräteeinheiten mit der höheren Auflösung, d. h. in Texteinheiten. Diese Geräte skalieren Koordinaten für Grafiken, damit mehrere Geräte Einheiten Zuordnung nur 1 Grafik Einheit gemeldet. Sie sollten immer aufrufen, die `SelectClipRgn` Funktion mithilfe von Texteinheiten.  
  
 Nutzen müssen die Skalierung von Grafikobjekten in GDI können die **GETSCALINGFACTOR** Druckerescape den Skalierungsfaktor bestimmt. Dieser Skalierungsfaktor wirkt sich auf Ausschneiden. Wenn eine Region für die clip-Grafiken verwendet wird, teilt GDI die Koordinaten durch den Skalierungsfaktor. Wenn der Bereich Ausschneiden von Text verwendet wird, macht GDI keine Skalierung Anpassung. Ein Skalierungsfaktor 1 bewirkt, dass die Koordinaten durch 2 geteilt wird. ein Skalierungsfaktor von 2 bewirkt, dass die Koordinaten durch 4 geteilt werden soll. Und so weiter.  
  
##  <a name="a-nameselectobjecta--cdcselectobject"></a><a name="selectobject"></a>CDC::SelectObject  
 Wählt ein Objekt in den Gerätekontext.  
  
```  
CPen* SelectObject(CPen* pPen);  
CBrush* SelectObject(CBrush* pBrush);  
virtual CFont* SelectObject(CFont* pFont);  
CBitmap* SelectObject(CBitmap* pBitmap);  
int SelectObject(CRgn* pRgn);  
CGdiObject* SelectObject(CGdiObject* pObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pPen*  
 Ein Zeiger auf eine [CPen](../../mfc/reference/cpen-class.md) Objekt ausgewählt werden muss.  
  
 `pBrush`  
 Ein Zeiger auf eine [CBrush](../../mfc/reference/cbrush-class.md) Objekt ausgewählt werden muss.  
  
 `pFont`  
 Ein Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) Objekt ausgewählt werden muss.  
  
 `pBitmap`  
 Ein Zeiger auf eine [CBitmap](../../mfc/reference/cbitmap-class.md) Objekt ausgewählt werden muss.  
  
 `pRgn`  
 Ein Zeiger auf eine [CRgn](../../mfc/reference/crgn-class.md) Objekt ausgewählt werden muss.  
  
 `pObject`  
 Ein Zeiger auf eine [CGdiObject](../../mfc/reference/cgdiobject-class.md) Objekt ausgewählt werden muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das zu ersetzende Objekt. Dies ist ein Zeiger auf ein Objekt eines abgeleitete `CGdiObject`, wie z. B. `CPen`, je nachdem, welche Version der Funktion verwendet wird. Der Rückgabewert ist **NULL** , wenn ein Fehler auftritt. Diese Funktion kann einen Zeiger auf ein temporäres Objekt zurückgeben. Dieses temporäre Objekt ist nur gültig, während der Verarbeitung einer Windows-Meldung. Weitere Informationen finden Sie unter `CGdiObject::FromHandle`.  
  
 Die Version der Memberfunktion, die einen Bereichsparameter annimmt, führt die gleiche Aufgabe wie die `SelectClipRgn` -Memberfunktion. Der Rückgabewert kann eines der folgenden sein:  
  
- **COMPLEXREGION** neue Ausschneidebereich hat Ränder überlappen.  
  
- **Fehler** Gerätekontext oder die Region ist ungültig.  
  
- **NULLREGION** neue Ausschneidebereich ist leer.  
  
- **SIMPLEREGION** neue Ausschneidebereich besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Klasse `CDC` bietet fünf Versionen für bestimmte Arten von GDI-Objekte, einschließlich Stifte, Pinsel, Schriftarten, Bitmaps und Regionen spezialisiert. Das neu ausgewählte Objekt ersetzt das vorherige Objekt des gleichen Typs. Z. B. wenn `pObject` der allgemeinen Version `SelectObject` verweist auf eine [CPen](../../mfc/reference/cpen-class.md) -Objekt, die Funktion ersetzt den aktuellen Stift mit dem angegebenen Stift `pObject`.  
  
 Eine Anwendung kann eine Bitmap in Speicher-Gerätekontexte nur und nur eine Speicher-Gerätekontext gleichzeitig auswählen. Das Format der Bitmap muss Monochrom oder mit den Gerätekontext kompatibel sein; ist dies nicht der Fall, `SelectObject` gibt einen Fehler zurück.  
  
 Windows 3.1 und höher die `SelectObject` Funktion gibt den gleichen Wert, ob es in einer Metadatei oder nicht verwendet wird. Unter früheren Versionen von Windows `SelectObject` einen Wert ungleich NULL für Erfolg und 0 für Fehler zurückgegeben, wenn es in einer Metadatei verwendet wurde.  
  
##  <a name="a-nameselectpalettea--cdcselectpalette"></a><a name="selectpalette"></a>CDC::SelectPalette  
 Wählt die logische Palette der von angegebenen `pPalette` wie das Palettenobjekt der ausgewählten des Gerätekontexts.  
  
```  
CPalette* SelectPalette(
    CPalette* pPalette,  
    BOOL bForceBackground);
```  
  
### <a name="parameters"></a>Parameter  
 `pPalette`  
 Gibt die logische Palette ausgewählt werden. Diese Palette muss haben bereits mit der `CPalette` Memberfunktion [CreatePalette](../../mfc/reference/cpalette-class.md#createpalette).  
  
 `bForceBackground`  
 Gibt an, ob die logische Palette ist ein Hintergrundpalette erzwungen wird. Wenn `bForceBackground` ist ungleich NULL ist, die ausgewählten Palette ist immer eine Hintergrundpalette, unabhängig davon, ob das Fenster den Eingabefokus besitzt. Wenn `bForceBackground` 0 und der Gerätekontext an ein Fenster angehängt wird, die logische Palette ist eine Vordergrund Palette aus, wenn das Fenster den Eingabefokus besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CPalette` -Objekt, das die logische Palette der Palette angegebenen Fassung identifiziert `pPalette`. Es ist **NULL** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die neue Palette wird die Palettenobjekt, das von GDI verwendet, um die Steuerelement-Farben, die in den Gerätekontext angezeigt und ersetzt die vorherige Palette.  
  
 Eine Anwendung kann eine logische Palette mehrere Gerätekontext auswählen. Änderungen an einer logischen Palette wirkt alle Gerätekontexte sich jedoch für die es aktiviert ist. Wenn eine Anwendung eine Palette mehrere Gerätekontext auswählt, müssen die Gerätekontexte alle auf demselben physischen Gerät gehören.  
  
##  <a name="a-nameselectstockobjecta--cdcselectstockobject"></a><a name="selectstockobject"></a>CDC::SelectStockObject  
 Wählt eine [CGdiObject](../../mfc/reference/cgdiobject-class.md) Objekt, das eine der vordefinierten stock Stifte, Pinsel oder Schriftarten entspricht.  
  
```  
virtual CGdiObject* SelectStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt die Art des gewünschten stock-Objekts. Die folgenden Werte sind möglich:  
  
- **BLACK_BRUSH** schwarzer Pinsel.  
  
- **DKGRAY_BRUSH** dunkel grauen Pinsel.  
  
- **GRAY_BRUSH** Gray Pinsel.  
  
- **HOLLOW_BRUSH** leeres Pinsel.  
  
- **LTGRAY_BRUSH** Light grauen Pinsel.  
  
- **NULL_BRUSH** Pinsel Null.  
  
- **WHITE_BRUSH** Pinsel weiß.  
  
- **BLACK_PEN** schwarzen Stift.  
  
- **NULL_PEN** Null Stift.  
  
- **WHITE_PEN** Weißer Stift.  
  
- **ANSI_FIXED_FONT** festen Systemschriftart ANSI.  
  
- **ANSI_VAR_FONT** Variable Systemschriftart ANSI.  
  
- **DEVICE_DEFAULT_FONT** geräteabhängige Schriftart.  
  
- **OEM_FIXED_FONT** OEM-abhängige Schriftart fest.  
  
- **SYSTEM_FONT** Systemschriftart. Standardmäßig verwendet Windows die Systemschriftart Menüs, Dialogfeld-Steuerelemente und anderen Text zeichnen. Es empfiehlt sich, jedoch nicht für SYSTEM_FONT zum Abrufen von Dialogfeldern und Fenstern verwendeten Schriftart abhängig. Verwenden Sie stattdessen die `SystemParametersInfo` Funktion mit dem SPI_GETNONCLIENTMETRICS ab-Parameter zum Abrufen der aktuellen Schriftart. `SystemParametersInfo`das aktuelle Design berücksichtigt sowie Schriftartinformationen für Beschriftungen, Menüs und Dialogfelder angezeigt.  
  
- **SYSTEM_FIXED_FONT** fester Breite Systemschriftart vor Version 3.0 in Windows verwendet. Dieses Objekt ist für die Kompatibilität mit früheren Versionen von Windows verfügbar.  
  
- **DEFAULT_PALETTE** Standardfarbpalette. Diese Palette besteht aus 20 statische Farben der Systempalette.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CGdiObject` -Objekt, das ersetzt wurde, wenn die Funktion erfolgreich ist. Ist das eigentliche Objekt, das auf eine [CPen](../../mfc/reference/cpen-class.md), [CBrush](../../mfc/reference/cbrush-class.md), oder [CFont](../../mfc/reference/cfont-class.md) Objekt. Wenn der Aufruf fehlschlägt, ist der Rückgabewert **NULL**.  
  
##  <a name="a-namesetabortproca--cdcsetabortproc"></a><a name="setabortproc"></a>CDC:: setabortproc  
 Installiert die Abort-Prozedur für den Auftrag.  
  
```  
int SetAbortProc(BOOL (CALLBACK* lpfn)(HDC, int));
```  
  
### <a name="parameters"></a>Parameter  
 `lpfn`  
 Ein Zeiger auf die Abort-Funktion, die als Abbruchvorgangs installieren. Weitere Informationen über die Callback-Funktion finden Sie unter [Rückruffunktion für CDC:: setabortproc](../../mfc/reference/callback-function-for-cdc-setabortproc.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der `SetAbortProc` Funktion. Einige der folgenden Werte sind wahrscheinlicher als andere, aber alle sind möglich.  
  
- **SP_ERROR** allgemeiner Fehler.  
  
- **SP_OUTOFDISK** nicht genügend Speicherplatz auf dem Datenträger steht zurzeit zum Spoolen und keinen Speicherplatz mehr zur Verfügung stehen.  
  
- **SP_OUTOFMEMORY** ist nicht genügend Arbeitsspeicher zum Spoolen verfügbar.  
  
- **SP_USERABORT** Benutzer beendet den Auftrag über den Druck-Manager.  
  
### <a name="remarks"></a>Hinweise  
 Ist eine Anwendung auf den Druckauftrag, während für Aufträge abgebrochen werden können, müssen sie die Abort-Funktion festgelegt, bevor der Druckauftrag mit gestartet wird die [StartDoc](#startdoc) Member-Funktion. Der Druck-Manager ruft die Abort-Funktion, während für Aufträge, damit die Anwendung den Auftrag abbrechen oder außerhalb der Speicherplatz verarbeiten kann. Wenn keine Abort-Funktion festgelegt ist, schlägt der Druckauftrag fehl, wenn es nicht genügend Speicherplatz zum Spoolen ist.  
  
 Beachten Sie, dass die Funktionen von Microsoft Visual C++ das Erstellen der übergebene Rückruffunktion vereinfachen `SetAbortProc`. Die Adresse übergeben, um die `EnumObjects` Member-Funktion ist ein Zeiger auf eine Funktion mit exportierten **__declspec(dllexport)** und mit der `__stdcall` Aufrufkonvention.  
  
 Sie auch keinen So exportieren Sie den Namen der Funktion in einer **EXPORTE** -Anweisung in einer Moduldefinitionsdatei für Ihre Anwendung. Stattdessen können Sie die **EXPORTIEREN** Modifizierer als in-Funktion  
  
 **BOOL RÜCKRUF EXPORT** AFunction ( **HDC**, `int` **);**  
  
 um den Compiler an, den richtigen Datensatz für den Export nach Namen ohne Aliasing ausgeben zu verursachen. Dies funktioniert für die meisten Anforderungen. Für einige Sonderfälle, z. B. eine Funktion nach Ordnungszahl oder Aliasing exportieren exportieren, Sie noch benötigen eine **EXPORTE** -Anweisung in einer DEF-Datei.  
  
 Registrierung Rückrufschnittstellen sind jetzt als typsicherer (Sie müssen in einen Funktionszeiger, der auf die richtige Art von Funktion für den bestimmten Rückruf zeigt übergeben).  
  
 Beachten Sie außerdem, dass alle Rückruffunktionen vor der Rückgabe auf Windows, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht Microsoft Foundation-Ausnahmen abfangen müssen. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
##  <a name="a-namesetarcdirectiona--cdcsetarcdirection"></a><a name="setarcdirection"></a>CDC::SetArcDirection  
 Richtung für das Zeichnen für Bogen und Rechteck Funktionen verwendet werden.  
  
```  
int SetArcDirection(int nArcDirection);
```  
  
### <a name="parameters"></a>Parameter  
 *nArcDirection*  
 Gibt die neue Arc-Richtung. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **AD_COUNTERCLOCKWISE** Zahlen, die gegen den Uhrzeigersinn gezeichnet.  
  
- **AD_CLOCKWISE** Zahlen im Uhrzeigersinn gezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die alte Bogen Richtung an, wenn erfolgreich. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert ist gegen den Uhrzeigersinn. Die `SetArcDirection` Funktion gibt die Richtung an, in dem die folgenden zeichnen Funktionen:  
  
|Bogen|Segment|  
|---------|---------|  
|`ArcTo`|**Rechteck**|  
|`Chord`|`RoundRect`|  
|**Ellipse**||  
  
##  <a name="a-namesetattribdca--cdcsetattribdc"></a><a name="setattribdc"></a>CDC::SetAttribDC  
 Rufen Sie diese Funktion zum Festlegen des Attribut-Gerätekontext `m_hAttribDC`.  
  
```  
virtual void SetAttribDC(HDC hDC);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Einen Windows-Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion auf den Gerätekontext nicht angefügt der `CDC` Objekt. Der Gerätekontext Ausgabe angefügt ist ein `CDC` Objekt.  
  
##  <a name="a-namesetbkcolora--cdcsetbkcolor"></a><a name="setbkcolor"></a>CDC::SetBkColor  
 Legt die aktuelle Hintergrundfarbe auf die angegebene Farbe fest.  
  
```  
virtual COLORREF SetBkColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die neue Hintergrundfarbe an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Hintergrundfarbe als einen RGB-Wert. Wenn ein Fehler auftritt, ist der Rückgabewert 0 x 80000000.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Hintergrundmodus ist **nicht TRANSPARENTEN**, das System die Hintergrundfarbe zum Füllen der Lücken in der formatierten Zeilen, die Lücken zwischen schraffierten Linien Pinsel und den Hintergrund in Zeichenzellen verwendet. Das System verwendet auch die Hintergrundfarbe beim Konvertieren von Bitmaps zwischen Farbe und Schwarzweiß Gerätekontexte.  
  
 Wenn das Gerät die angegebene Farbe nicht anzeigen kann, setzt das System die Hintergrundfarbe auf die nächstgelegene Farbe für die physischen.  
  
##  <a name="a-namesetbkmodea--cdcsetbkmode"></a><a name="setbkmode"></a>CDC::SetBkMode  
 Der Hintergrundmodus festgelegt.  
  
```  
int SetBkMode(int nBkMode);
```  
  
### <a name="parameters"></a>Parameter  
 *nBkMode*  
 Gibt den Modus festgelegt werden. Dieser Parameter kann einen der folgenden Werte sein:  
  
- **Nicht TRANSPARENTE** Hintergrund wird mit der aktuellen Hintergrundfarbe vor dem Text, schraffierten Pinsel gefüllt oder Stift gezeichnet wird. Dies ist der Standardmodus für den Hintergrund.  
  
- **TRANSPARENTE** Hintergrund wird vor dem Zeichnen nicht geändert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Hintergrundmodus.  
  
### <a name="remarks"></a>Hinweise  
 Hintergrund definiert, ob das System vorhandene Hintergrundfarben auf die Zeichenoberfläche entfernt vor dem Text, schraffierten Pinsel oder einen Stiftstil, der keiner durchgezogenen Linie zeichnen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor).  
  
##  <a name="a-namesetboundsrecta--cdcsetboundsrect"></a><a name="setboundsrect"></a>CDC::SetBoundsRect  
 Steuert die Akkumulation des umschließenden Rechtecks Informationen für den angegebenen Gerätekontext.  
  
```  
UINT SetBoundsRect(
    LPCRECT lpRectBounds,  
    UINT flags);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRectBounds`  
 Verweist auf eine `RECT` Struktur oder `CRect` -Objekt, das das umschließende Rechteck festgelegt. Rechteck Dimensionen sind in logischen Koordinaten angegeben. Dieser Parameter kann **NULL**.  
  
 `flags`  
 Gibt an, wie das neue Rechteck mit dem kumulierten Rechteck kombiniert werden. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
- **DCB_ACCUMULATE** das Rechteck angegebenen `lpRectBounds` auf das umschließende Rechteck (mit einem Rechteck-Union-Vorgang).  
  
- **DCB_DISABLE** Grenzen Ansammlung deaktivieren.  
  
- **DCB_ENABLE** Grenzen Ansammlung aktivieren. (Die Standardeinstellung für Grenzen Ansammlung ist deaktiviert).  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Status des umschließenden Rechtecks, wenn die Funktion erfolgreich ist. Wie `flags`, der Rückgabewert kann eine Kombination von **DCB_** Werte:  
  
- **DCB_ACCUMULATE** das umschließende Rechteck ist nicht leer. Dieser Wert wird immer festgelegt werden.  
  
- **DCB_DISABLE** Grenzen Ansammlung ist deaktiviert.  
  
- **DCB_ENABLE** Grenzen Ansammlung ist.  
  
### <a name="remarks"></a>Hinweise  
 Windows kann ein umschließendes Rechteck für alle Zeichenvorgänge verwalten. Dieses Rechteck kann abgefragt und von der Anwendung zurückgesetzt werden. Die Zeichnung Grenzen sind hilfreich für Bitmap-Caches für ungültig erklärt.  
  
##  <a name="a-namesetbrushorga--cdcsetbrushorg"></a><a name="setbrushorg"></a>CDC::SetBrushOrg  
 Gibt die Ursprungsdomäne, die GDI auf den nächsten Pinsel zuweist, die die Anwendung in den Gerätekontext auswählt.  
  
```  
CPoint SetBrushOrg(
    int x,  
    int y);  
  
CPoint SetBrushOrg(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die X-Koordinate (in Geräteeinheiten) des neuen Ursprungs. Dieser Wert muss im Bereich von 0 bis 7 sein.  
  
 *y*  
 Gibt die y-Koordinate (in Geräteeinheiten) des neuen Ursprungs. Dieser Wert muss im Bereich von 0 bis 7 sein.  
  
 `point`  
 Gibt die x- und y-Koordinaten des neuen Ursprungs. Jeder Wert muss im Bereich von 0 bis 7 sein. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Ursprung des Pinsels in Geräteeinheiten.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung für den Ursprung Pinsel koordiniert sind (0, 0). Aufrufen, um den Ursprung eines Pinsels ändern, die `UnrealizeObject` -Funktion für die `CBrush` -Objekt, rufen Sie `SetBrushOrg`, und rufen Sie dann die `SelectObject` Memberfunktion, wählen Sie den Pinsel im Gerätekontext.  
  
 Verwenden Sie keine `SetBrushOrg` mit Stock `CBrush` Objekte.  
  
##  <a name="a-namesetcoloradjustmenta--cdcsetcoloradjustment"></a><a name="setcoloradjustment"></a>CDC::SetColorAdjustment  
 Legt die Farbe Anpassungswerte für den Gerätekontext, der mit den angegebenen Werten.  
  
```  
BOOL SetColorAdjustment(const COLORADJUSTMENT* lpColorAdjust);
```  
  
### <a name="parameters"></a>Parameter  
 `lpColorAdjust`  
 Verweist auf eine [COLORADJUSTMENT](../../mfc/reference/coloradjustment-structure.md) -Datenstruktur mit den Farbwerten der Anpassung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Anpassungswerte für Farbe verwendet, um die Eingabe Farbe der Quellbitmap für Aufrufe von anzupassen der `CDC::StretchBlt` Memberfunktion beim **HALBTON** -Modus festgelegt ist.  
  
##  <a name="a-namesetdcbrushcolora--cdcsetdcbrushcolor"></a><a name="setdcbrushcolor"></a>CDC::SetDCBrushColor  
 Legt die aktuelle Pinselfarbe Gerät Gerätekontext (DC) auf den Wert der angegebenen Farbe fest.  
  
```  
COLORREF SetDCBrushColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die neue Pinselfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, gibt der Rückgabewert die vorherige DC Pinselfarbe als ein `COLORREF` Wert.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert `CLR_INVALID`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode emuliert die Funktionen der Funktion [SetDCBrushColor](http://msdn.microsoft.com/library/windows/desktop/dd162969)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetdcpencolora--cdcsetdcpencolor"></a><a name="setdcpencolor"></a>CDC::SetDCPenColor  
 Legt die aktuelle Stiftfarbe für Gerät Gerätekontext (DC) auf den Wert der angegebenen Farbe fest.  
  
```  
COLORREF SetDCPenColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die neue Stiftfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verwendet die Win32-Funktion [SetDCPenColor](http://msdn.microsoft.com/library/windows/desktop/dd162970)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetgraphicsmodea--cdcsetgraphicsmode"></a><a name="setgraphicsmode"></a>CDC::SetGraphicsMode  
 Legt den Grafikmodus für den angegebenen Gerätekontext.  
  
```  
int SetGraphicsMode(int iMode);
```  
  
### <a name="parameters"></a>Parameter  
 `iMode`  
 Gibt den Grafikmodus. Eine Liste der Werte, die für diesen Parameter finden Sie unter [SetGraphicsMode](http://msdn.microsoft.com/library/windows/desktop/dd162977).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den alten Grafikmodus bei Erfolg zurück.  
  
 Gibt 0 bei einem Fehler zurück. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode umschließt die Windows GDI-Funktion [SetGraphicsMode](http://msdn.microsoft.com/library/windows/desktop/dd162977).  
  
##  <a name="a-namesetlayouta--cdcsetlayout"></a><a name="setlayout"></a>CDC::SetLayout  
 Rufen Sie diese Memberfunktion zum Ändern des Layouts von Text und Grafiken für einen Gerätekontext auf von rechts nach links, das Standardlayout für Kulturen, wie z. B. Arabisch und Hebräisch.  
  
```  
DWORD SetLayout(DWORD dwLayout);
```  
  
### <a name="parameters"></a>Parameter  
 `dwLayout`  
 Gerät Kontext und Bitmap Flags zu bestimmen. Es kann eine Kombination der folgenden Werte sein.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|LAYOUT_BITMAPORIENTATIONPRESERVED|Deaktiviert alle Reflektion für Aufrufe von [CDC::BitBlt](#bitblt) und [CDC::StretchBlt](#stretchblt).|  
|LAYOUT_RTL|Legt den horizontalen Standardlayout werden von rechts nach links fest.|  
|LAYOUT_LTR|Legt das standardmäßige Layout von links nach rechts werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Falls erfolgreich, das vorherige Layout des Gerätekontexts.  
  
 Wenn dies nicht gelingt, **GDI_ERROR**. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel nicht aufgerufen **SetLayout** für ein Fenster. Stattdessen steuern die rechts-nach-links-Layout in einem Fenster durch Festlegen der [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md) wie z. B. **WS_EX_RTLREADING**. Dieses Layout ein Gerätekontext, z. B. einen Drucker oder eine Metadatei nicht geerbt. Die einzige Möglichkeit, den Gerätekontext festgelegt ein rechts-nach-links-Layout durch Aufrufen von **SetLayout**.  
  
 Wenn Sie aufrufen **SetLayout (LAYOUT_RTL** ), **SetLayout** automatisch ändert die Zuordnung zu `MM_ISOTROPIC`. Als Ergebnis ein nachfolgender Aufruf von [GetMapMode](#getmapmode) zurück **MM_ISOTROPIC** anstelle von `MM_TEXT`.  
  
 In einigen Fällen können z. B. mit vielen Bitmaps Sie die links-nach-rechts-Layout beibehalten möchten. In diesen Fällen rendern Sie das Bild durch Aufrufen von `BitBlt` oder `StretchBlt`, legen Sie die Bitmap-Steuerelement-Flag für `dwLayout` auf **LAYOUT_BITMAPORIENTATIONPRESERVED**.  
  
 Nachdem Sie das Layout mit ändern die **LAYOUT_RTL** zu kennzeichnen, die Flags, die normalerweise angeben rechts oder Links werden rückgängig gemacht. Um Verwirrung zu vermeiden, sollten Sie alternative Namen für die standard-Flags zu definieren. Eine Liste der vorgeschlagenen alternativen Flag Namen finden Sie unter [SetLayout](http://msdn.microsoft.com/library/windows/desktop/dd162979) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmapmodea--cdcsetmapmode"></a><a name="setmapmode"></a>CDC::SetMapMode  
 Legt den Zuordnungsmodus.  
  
```  
virtual int SetMapMode(int nMapMode);
```  
  
### <a name="parameters"></a>Parameter  
 `nMapMode`  
 Gibt das neue Zuordnung an. Einer der folgenden Werte sind möglich:  
  
- `MM_ANISOTROPIC`Logische Einheiten werden in beliebigen Einheiten mit willkürlich skalierte Achsen konvertiert. Wenn der Zuordnungsmodus auf `MM_ANISOTROPIC` ändert sich nicht auf die aktuelle Fenster oder der Viewport-Einstellungen. Ausrichtung und skalieren, rufen Sie zum Ändern der Einheiten der [SetWindowExt](#setwindowext) und [SetViewportExt](#setviewportext) Memberfunktionen.  
  
- `MM_HIENGLISH`Jede logische Einheit wird auf 0,001 Zoll konvertiert. Positive x ist auf der rechten Seite. positive y liegt.  
  
- `MM_HIMETRIC`Jede logische Einheit wird in 0,01 Millimeter konvertiert. Positive x ist auf der rechten Seite. positive y liegt.  
  
- `MM_ISOTROPIC`Logische Einheiten werden gleichmäßig skaliert Achsen in beliebigen Einheiten konvertiert. 1 Einheit der x-Achse entspricht, also 1 Einheit entlang der y-Achse. Verwenden der `SetWindowExt` und `SetViewportExt` Memberfunktionen der gewünschten Einheiten und die Ausrichtung der Achsen an. GDI zusammen, werden ggf. um sicherzustellen, dass die x- und y-Einheiten bleiben die gleiche Größe.  
  
- `MM_LOENGLISH`Jede logische Einheit auf 0,01 Zoll konvertiert. Positive x ist auf der rechten Seite. positive y liegt.  
  
- `MM_LOMETRIC`Jede logische Einheit ist in 0,1 Millimeter konvertiert. Positive x ist auf der rechten Seite. positive y liegt.  
  
- `MM_TEXT`Jede logische Einheit wird auf 1 Gerät Pixel konvertiert. Positive x ist auf der rechten Seite. positive y ist ausgefallen.  
  
- `MM_TWIPS`Jede logische Einheit wird in 1/20 Punkt konvertiert. (Da ein Punkt 1/72 Zoll ist, ist ein Twip 1/1440 Zoll). Positive x ist auf der rechten Seite. positive y liegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Zuordnungsmodus.  
  
### <a name="remarks"></a>Hinweise  
 Der Zuordnungsmodus definiert die Einheit mit der logische Einheiten Gerät Einheiten konvertiert. Außerdem wird die Ausrichtung des Geräts x- und y-Achse definiert. GDI verwendet den Zuordnungsmodus logische Koordinaten in das entsprechende Gerätekoordinaten konvertiert. Der `MM_TEXT` Modus ermöglicht es Clientanwendungen arbeiten in Pixeln, wobei 1 Einheit gleich 1 Pixel. Die physische Größe eines Pixels variiert je nach Gerät.  
  
 Die `MM_HIENGLISH`, `MM_HIMETRIC`, `MM_LOENGLISH`, `MM_LOMETRIC`, und `MM_TWIPS` Modi sind nützlich für Anwendungen, die in physisch sinnvoller Einheiten (z. B. Zoll oder Millimeter) zeichnen müssen. Der `MM_ISOTROPIC` Modus wird sichergestellt, eine 1:1-Seitenverhältnis, das ist nützlich, wenn es wichtig ist, die genaue Form eines Bildes beibehalten. Die `MM_ANISOTROPIC` im Modus für die x- und y-Koordinaten unabhängig voneinander angepasst werden können.  
  
> [!NOTE]
>  Wenn Sie aufrufen [SetLayout](#setlayout) so ändern Sie den DC (Gerätekontext) rechts-nach-links-Layout **SetLayout** automatisch ändert die Zuordnung zu `MM_ISOTROPIC`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc).  
  
##  <a name="a-namesetmapperflagsa--cdcsetmapperflags"></a><a name="setmapperflags"></a>CDC::SetMapperFlags  
 Ändert die Methode von Font Mapper verwendet werden, wenn eine logische Schriftart in einer physikalischen Schriftart konvertiert.  
  
```  
DWORD SetMapperFlags(DWORD dwFlag);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlag`  
 Gibt an, ob die Schriftartenmapper versucht, eine Schriftart Aspekt Höhe und Breite auf dem Gerät übereinstimmt. Wenn dieser Wert ist **ASPECT_FILTERING**, Mapper wählt nur Schriftarten, deren Aspect-X und y-Aspekt ist genau übereinstimmen, die von dem angegebenen Gerät.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Wert des Flags Schriftart-Mapper.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann mithilfe `SetMapperFlags` verursachen Font Mapper versucht, nur eine physische Schriftart auswählen, die genau das Seitenverhältnis des angegebenen Geräts übereinstimmt.  
  
 Können Sie eine Anwendung, die nur die Rasterschriftarten verwendet die `SetMapperFlags` Funktion, um sicherzustellen, dass die vom Schriftartenmapper ausgewählte Schriftart ansprechend und lesbar, auf dem angegebenen Gerät. Die skalierbare (TrueType) Schriftarten, in der Regel verwenden verwenden Sie keine `SetMapperFlags`.  
  
 Wenn keine physischen Schriftart ein Seitenverhältnis verfügt, die die logische Schriftart-Spezifikation entspricht, ist GDI wählt ein neues Seitenverhältnis und wählt eine Schriftart, die diese neuen Seitenverhältnis entspricht.  
  
##  <a name="a-namesetmiterlimita--cdcsetmiterlimit"></a><a name="setmiterlimit"></a>CDC::SetMiterLimit  
 Legt das Limit für die Länge der Gehrung Joins für den Gerätekontext.  
  
```  
BOOL SetMiterLimit(float fMiterLimit);
```  
  
### <a name="parameters"></a>Parameter  
 *fMiterLimit*  
 Gibt die neue Gehrungsgrenze für den Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Gehrungslänge ist definiert als die Entfernung aus der Schnittmenge der Zeile Wände innerhalb der Verknüpfung auf die Schnittmenge der Zeile Wände außerhalb des Joins. Die Gehrungsgrenze ist die maximal zulässige Quotient aus Gehrungslänge auf die Linienstärke. Die standardmäßige Gehrungsgrenze ist 10.0.  
  
##  <a name="a-namesetoutputdca--cdcsetoutputdc"></a><a name="setoutputdc"></a>CDC::SetOutputDC  
 Rufen Sie diese Memberfunktion zum Festlegen des Ausgabe-Gerätekontext `m_hDC`.  
  
```  
virtual void SetOutputDC(HDC hDC);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Einen Windows-Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion kann nur aufgerufen werden, wenn Sie ein Gerätekontext nicht zugeordnet wurde die `CDC` Objekt. Diese Memberfunktion legt `m_hDC` , den Gerätekontext, hängt jedoch die `CDC` Objekt.  
  
##  <a name="a-namesetpixela--cdcsetpixel"></a><a name="setpixel"></a>CDC::SetPixel  
 Legt die Pixel an der Stelle, an der angegebenen Farbe am nächsten Angleichung angegeben `crColor`.  
  
```  
COLORREF SetPixel(
    int x,  
    int y,  
    COLORREF crColor);

 
COLORREF SetPixel(
    POINT point,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Punktes, der festgelegt werden.  
  
 *y*  
 Gibt die logische y-Koordinate des Punktes, der festgelegt werden.  
  
 `crColor`  
 Ein **COLORREF** RGB-Wert, der angibt, die Farbe für den Punkt zu zeichnen. Finden Sie unter [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beschreibung dieses Werts.  
  
 `point`  
 Gibt die logische X - und y-Koordinaten des Punkts, der festgelegt werden. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 RGB-Wert für die Farbe, der Punkt tatsächlich gezeichnet wird. Dieser Wert kann von anderen `crColor` wird eine Angleichung dieser Farbe. Wenn die Funktion fehlschlägt (wenn der Punkt außerhalb des Clippingbereichs ist), ist der Rückgabewert –&1;.  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt muss in den Ausschneidebereich sein. Wenn der Punkt nicht in den Ausschneidebereich ist, bleibt die Funktion untätig.  
  
 Nicht alle Geräte unterstützen die `SetPixel`-Funktion. Zu bestimmen, ob ein Gerät unterstützt `SetPixel`, rufen Sie die `GetDeviceCaps` Memberfunktion mit der **RASTERCAPS** index, und überprüfen Sie den Rückgabewert für die **RC_BITBLT** Flag.  
  
##  <a name="a-namesetpixelva--cdcsetpixelv"></a><a name="setpixelv"></a>CDC::SetPixelV  
 Legt das Pixel an den angegebenen Koordinaten auf der nächsten Näherung der angegebenen Farbe fest.  
  
```  
BOOL SetPixelV(
    int x,  
    int y,  
    COLORREF crColor);

 
BOOL SetPixelV(
    POINT point,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die X-Koordinate, in logischen Einheiten des Punktes, der festgelegt werden.  
  
 *y*  
 Gibt die y-Koordinate, in logischen Einheiten des Punktes, der festgelegt werden.  
  
 `crColor`  
 Gibt die Farbe an, die verwendet werden, um den Punkt zu zeichnen.  
  
 `point`  
 Gibt die logische X - und y-Koordinaten des Punkts, der festgelegt werden. Übergeben Sie entweder ein [Punkt](../../mfc/reference/point-structure1.md) Datenstruktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt muss in den Ausschneidebereich und der sichtbare Teil des Geräteoberfläche sein. Nicht alle Geräte unterstützen die Member-Funktion. Weitere Informationen finden Sie unter der **RC_BITBLT** Funktion in der `CDC::GetDeviceCaps` Member-Funktion. `SetPixelV`ist schneller als `SetPixel` , da er nicht den Farbwert des Punkts tatsächlich gezeichnet zurückgeben muss.  
  
##  <a name="a-namesetpolyfillmodea--cdcsetpolyfillmode"></a><a name="setpolyfillmode"></a>CDC::SetPolyFillMode  
 Legt den Modus Polygon füllen.  
  
```  
int SetPolyFillMode(int nPolyFillMode);
```  
  
### <a name="parameters"></a>Parameter  
 `nPolyFillMode`  
 Gibt den neuen Füllmodus. Dieser Wert kann entweder sein **ALTERNATIVEN** oder **WICKLUNGSREIHENFOLGEN**. Der Standardmodus in Windows festgelegt ist **ALTERNATIVEN**.  
  
### <a name="return-value"></a>Rückgabewert  
 Den vorherigen Füllmodus, wenn erfolgreich; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Polygon-Füllmodus ist **ALTERNATIVEN**, das System füllt den Bereich zwischen ungerade und gerade Polygonseiten in jeder Scanzeile ein. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen dem dritten und vierten Seite usw.. Dieser Modus ist die Standardeinstellung.  
  
 Wenn die Polygon-Füllmodus ist **WICKLUNGSREIHENFOLGEN**, verwendet das System die Richtung, in der Abbildung, um festzustellen, ob das Ausfüllen eines Bereichs gezeichnet wurde. Jedes Liniensegment in einem Polygon wird im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn eine imaginäre Linie gezeichnet aus einem eingeschlossenen Bereich außerhalb einer Abbildung im Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl erhöht. Wenn die Zeile gegen den Uhrzeigersinn Liniensegment durchläuft, wird der Zähler verringert. Der Bereich wird ausgefüllt, wenn der Wert ungleich NULL ist, wenn die Zeile außerhalb der Abbildung erreicht.  
  
##  <a name="a-namesetrop2a--cdcsetrop2"></a><a name="setrop2"></a>CDC::SetROP2  
 Legt den aktuellen Zeichnungsmodus fest.  
  
```  
int SetROP2(int nDrawMode);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawMode`  
 Gibt den neuen Zeichnungsmodus. Die folgenden Werte sind möglich:  
  
- **R2_BLACK** Pixel ist immer Schwarz.  
  
- **R2_WHITE** Pixel ist immer weiß.  
  
- **R2_NOP** Pixel bleibt unverändert.  
  
- **R2_NOT** Pixel ist die Umkehrung der Bildschirmfarbe.  
  
- **R2_COPYPEN** Pixel ist die Stiftfarbe.  
  
- **R2_NOTCOPYPEN** Pixel ist die Umkehrung der Stiftfarbe.  
  
- **R2_MERGEPENNOT** Pixel ist eine Kombination der Stiftfarbe und die Umkehrung der Bildschirmfarbe (endgültige Pixel = (nicht in Bildschirmpixel) oder Stift).  
  
- **R2_MASKPENNOT** Pixel ist eine Kombination der Farben, die Stift und der Umkehrung des Bildschirms (endgültige Pixel = (nicht in Bildschirmpixel) und Stift).  
  
- **R2_MERGENOTPEN** Pixel ist eine Kombination der Bildschirmfarbe und der Umkehrung der Stiftfarbe (endgültige Pixel = (nicht Stift) oder Bildschirm Pixel).  
  
- **R2_MASKNOTPEN** Pixel ist eine Kombination der Farben auf dem Bildschirm und der Umkehrung des Stifts (endgültige Pixel = (nicht Stift) und Bildschirm Pixel).  
  
- **R2_MERGEPEN** Pixel ist eine Kombination der Stiftfarbe und der Bildschirmfarbe (endgültige Pixel = Stift oder Bildschirmpixel).  
  
- **R2_NOTMERGEPEN** Pixel ist die Umkehrung der **R2_MERGEPEN** Farbe (endgültige Pixel = nicht (Stift oder Bildschirmpixel)).  
  
- **R2_MASKPEN** Pixel ist eine Kombination der Farben, die Stift und der Bildschirm (endgültige Pixel = Stift und Bildschirmpixel).  
  
- **R2_NOTMASKPEN** Pixel ist die Umkehrung der **R2_MASKPEN** Farbe (endgültige Pixel = nicht (Stift und Bildschirmpixel)).  
  
- **R2_XORPEN** Pixel ist eine Kombination der Farben, die in den Stift oder auf dem Bildschirm, aber nicht in beiden sind (letzte Pixel = Stift XOR Bildschirmpixel).  
  
- **R2_NOTXORPEN** Pixel ist die Umkehrung der **R2_XORPEN** Farbe (endgültige Pixel = nicht (Stift XOR Bildschirmpixel)).  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Zeichenmodus.  
  
 Es kann eine von den Werten in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Zeichnungsmodus gibt an, wie die Farben des Stifts und das Innere eines ausgefüllten Objekte mit Farbe bereits auf der Anzeigeoberfläche kombiniert werden.  
  
 Zeichnungsmodus ist nur für Rastergeräte. Es gilt nicht für Geräte Vektor. Zeichnung Modi handelt es sich um binäre rastervorgang-Codes, die alle mögliche booleschen Kombinationen von zwei Variablen, die nicht mit binären Operatoren AND, OR und XOR (exklusives OR) und die unäre Operation darstellt.  
  
##  <a name="a-namesetstretchbltmodea--cdcsetstretchbltmode"></a><a name="setstretchbltmode"></a>CDC::SetStretchBltMode  
 Legt den Modus Dehnen von Bitmap für die `StretchBlt` -Memberfunktion.  
  
```  
int SetStretchBltMode(int nStretchMode);
```  
  
### <a name="parameters"></a>Parameter  
 *nStretchMode*  
 Gibt den streckmodus an. Die folgenden Werte sind möglich:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**BLACKONWHITE**|Führt eine boolesche AND-Operation für die gelöschte und vorhandene Pixel mit. Wenn die Bitmap eine monochrome Bitmap ist, wird dieser Modus schwarze Pixel auf Kosten der weißen Pixeln beibehalten.|  
|**COLORONCOLOR**|Löscht die Pixel. Dieser Modus löscht alle gelöschte Zeilen in der Pixel, ohne zu versuchen, ihre Daten zu erhalten.|  
|**HALBTON**|Ordnet das Quellrechteck Pixel in Blöcke Pixel in das Zielrechteck. Die durchschnittliche Farbe über den Zielblock der Pixel entspricht die Farbe der Pixel der Quelle.|  
||Nach dem Festlegen der **HALBTON** Dehnen Modus, muss eine Anwendung die Win32-Funktion aufrufen [SetBrushOrgEx](http://msdn.microsoft.com/library/windows/desktop/dd162967) Festlegen des Ursprungs Pinsel. Wenn sie nicht dazu, tritt auf, Pinsel einer.|  
|**STRETCH_ANDSCANS**|**Windows 95/98**: wie **BLACKONWHITE**|  
|**STRETCH_DELETESCANS**|**Windows 95/98**: wie **COLORONCOLOR**|  
|**STRETCH_HALFTONE**|**Windows 95/98**: wie **HALBTON**.|  
|**STRETCH_ORSCANS**|**Windows 95/98**: wie **WHITEONBLACK**|  
|**WHITEONBLACK**|Führt eine boolesche OR-Operation für die gelöschte und vorhandene Pixel mit. Wenn die Bitmap eine monochrome Bitmap ist, wird dieser Modus weißen Pixel auf Kosten der schwarze Pixel beibehalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige ausdehnen Modus. Es kann sein **STRETCH_ANDSCANS**, **STRETCH_DELETESCANS**, oder **STRETCH_ORSCANS**.  
  
### <a name="remarks"></a>Hinweise  
 Dehnen von Bitmap-Modus wird definiert, wie Informationen aus Bitmaps entfernt werden, die mithilfe der Funktion komprimiert werden.  
  
 Die **BLACKONWHITE** ( **STRETCH_ANDSCANS**) und **WHITEONBLACK** ( **STRETCH_ORSCANS**) Modi werden in der Regel verwendet, um Vordergrund Pixel monochrome Bitmaps beizubehalten. Die **COLORONCOLOR** ( **STRETCH_DELETESCANS**) Modus wird normalerweise verwendet, um Farbe in Farbbitmaps zu erhalten.  
  
 Die **HALBTON** Modus erfordert mehr Verarbeitungszeit des Quellbilds als die anderen drei Modi; es ist langsamer als die anderen, jedoch eine bessere Qualität der Bilder erzeugt. Beachten Sie, dass **SetBrushOrgEx** muss aufgerufen werden, nach dem Festlegen der **HALBTON** um Pinsel fehlausrichtung zu vermeiden.  
  
 Zusätzliche ausdehnen Modi möglicherweise auch abhängig von der Gerätetreiber zur Verfügung.  
  
##  <a name="a-namesettextaligna--cdcsettextalign"></a><a name="settextalign"></a>CDC::SetTextAlign  
 Legt die Ausrichtung Flags.  
  
```  
UINT SetTextAlign(UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `nFlags`  
 Gibt Flags Ausrichtung. Die Flags geben die Beziehung zwischen einem Punkt und ein Rechteck, das den Text umschließt. Der Punkt kann der aktuellen Position oder durch eine Textausgabe Funktion angegebenen Koordinaten. Das Rechteck, das den Text umschließende wird durch die Zellen angrenzenden Zeichen in der Zeichenfolge definiert. Die `nFlags` Parameter kann ein oder mehrere Flags aus den folgenden drei Kategorien sein. Wählen Sie nur ein Flag aus jeder Kategorie. Die erste Kategorie wirkt sich auf die Ausrichtung des Texts in der X-Richtung:  
  
- **TA_CENTER** richtet den Punkt mit der horizontalen Mitte des umschließenden Rechtecks.  
  
- **TA_LEFT** richtet den Punkt mit der linken Seite des umschließenden Rechtecks. Dies ist die Standardeinstellung.  
  
- **TA_RIGHT** richtet den Punkt mit der rechten Seite des umschließenden Rechtecks.  
  
 Die zweite Kategorie wirkt sich auf die Ausrichtung des Texts in der y-Richtung:  
  
- **TA_BASELINE** richtet den Punkt mit der Grundlinie der ausgewählten Schriftart.  
  
- **TA_BOTTOM** richtet den Punkt am unteren Rand das umschließende Rechteck.  
  
- **TA_TOP** richtet den Punkt am Rand des umschließenden Rechtecks. Dies ist die Standardeinstellung.  
  
 Die dritte Kategorie bestimmt, ob die aktuelle Position aktualisiert wird, wenn Text geschrieben wird:  
  
- **TA_NOUPDATECP** aktualisiert die aktuelle Position nicht nach jedem Aufruf einer Funktion für die Ausgabe von Text. Dies ist die Standardeinstellung.  
  
- **TA_UPDATECP** aktualisiert die aktuelle X-Position nach jedem Aufruf einer Funktion für die Ausgabe von Text. Die neue Position wird auf der rechten Seite des umschließenden Rechtecks für den Text. Wenn dieses Flag festgelegt ist, die in Aufrufe an angegebenen Koordinaten der `TextOut` Member-Funktion werden ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige-Ausrichtung-Einstellung, wenn erfolgreich. Das niedrige Byte enthält das horizontale und das höherwertige Byte enthält das vertikale. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `TextOut` und `ExtTextOut` -Memberfunktionen verwenden diese Flags, eine Zeichenfolge oder einem Anzeige zu positionieren. Die Flags geben die Beziehung zwischen einem bestimmten Zeitpunkt und ein Rechteck, das den Text umschließt. Die Koordinaten dieses Punkts werden als Parameter übergeben, der `TextOut` Member-Funktion. Das Rechteck, das den Text umschließende wird durch die Zellen angrenzenden Zeichen in der Textzeichenfolge gebildet wird.  
  
##  <a name="a-namesettextcharacterextraa--cdcsettextcharacterextra"></a><a name="settextcharacterextra"></a>CDC::SetTextCharacterExtra  
 Legt die Menge des Zeichenabstands fest.  
  
```  
int SetTextCharacterExtra(int nCharExtra);
```  
  
### <a name="parameters"></a>Parameter  
 `nCharExtra`  
 Gibt die zusätzlichen Speicherplatz (in logischen Einheiten) für jedes Zeichen hinzugefügt werden. Ist der aktuelle Zuordnungsmodus nicht `MM_TEXT`, `nCharExtra` transformiert und gerundet auf den nächsten Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Anteil der vorherigen Zeichenabstands.  
  
### <a name="remarks"></a>Hinweise  
 GDI hinzugefügt jedes Zeichen, einschließlich Zeilenumbruchzeichen unverändert, wenn sie eine Textzeile in den Gerätekontext schreibt diesen Abstand. Der Standardwert für den Zeichenabstands ist 0.  
  
##  <a name="a-namesettextcolora--cdcsettextcolor"></a><a name="settextcolor"></a>CDC::SetTextColor  
 Legt die Farbe des Texts auf die angegebene Farbe fest.  
  
```  
virtual COLORREF SetTextColor(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die Farbe des Texts als einen RGB-Farbwert an.  
  
### <a name="return-value"></a>Rückgabewert  
 Für die vorherigen Textfarbe RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Vom System wird diese Farbe verwendet, beim Schreiben von Text in den Gerätekontext und auch beim Konvertieren von Bitmaps zwischen Farbe und Schwarzweiß Gerätekontexte.  
  
 Wenn das Gerät die angegebene Farbe nicht darstellen kann, setzt das System die Farbe des Texts auf die nächstgelegene Farbe für die physischen. Die Hintergrundfarbe für ein Zeichen wird angegeben, indem die `SetBkColor` und `SetBkMode` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor).  
  
##  <a name="a-namesettextjustificationa--cdcsettextjustification"></a><a name="settextjustification"></a>CDC::SetTextJustification  
 Die Break-Zeichen in einer Zeichenfolge hinzugefügt Leerzeichen.  
  
```  
int SetTextJustification(
    int nBreakExtra,  
    int nBreakCount);
```  
  
### <a name="parameters"></a>Parameter  
 `nBreakExtra`  
 Gibt die zusätzlichen Speicherplatzes die Textzeile (in logischen Einheiten) hinzugefügt werden. Der aktuelle Zuordnungsmodus ist nicht `MM_TEXT`, der von diesem Parameter angegebene Wert wird in der aktuellen Zuordnungsmodus konvertiert und gerundet auf die nächste Gerät.  
  
 *nBreakCount*  
 Gibt die Anzahl der Zeichen für Zeilenumbrüche in der Zeile an.  
  
### <a name="return-value"></a>Rückgabewert  
 Eins, wenn die Funktion erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann mithilfe der `GetTextMetrics` Memberfunktionen zum Abrufen einer Schriftart unterbrechen Zeichen.  
  
 Nach der `SetTextJustification` -Memberfunktion aufgerufen wird, einen Aufruf einer Funktion für die Ausgabe von Text (z. B. `TextOut`) die angegebenen zusätzlichen Platz gleichmäßig auf die angegebene Anzahl von Zeichen für Zeilenumbrüche verteilt. Das Umbruchzeichen wird in der Regel das Leerzeichen (ASCII 32), aber möglicherweise von einer Schriftart als ein anderes Zeichen definiert.  
  
 Die Memberfunktion `GetTextExtent` wird normalerweise verwendet, mit `SetTextJustification`. `GetTextExtent`berechnet die Breite einer bestimmten Zeile vor dem ausrichten. Eine Anwendung kann bestimmen, wie viel Speicherplatz an, in der `nBreakExtra` Parameter durch Subtrahieren des von zurückgegebenen Werts `GetTextExtent` von der Breite der Zeichenfolge nach der Ausrichtung.  
  
 Die `SetTextJustification` -Funktion kann verwendet werden, um eine Linie auszurichten, die mehrere Testläufe in verschiedenen Schriftarten enthält. In diesem Fall muss die Zeile schrittweise durch das Ausrichten und Schreiben alle separat erstellt werden.  
  
 Da Rundungsfehler während Ausrichtung auftreten kann, hält das System ausgeführten Fehler Ausdruck, der den aktuellen Fehler definiert. Wenn eine Zeile ausrichten, die mehrere ausgeführt wird, enthält `GetTextExtent` automatisch diese Fehlerterm, wenn er das Ausmaß der nächsten Ausführung berechnet, verwendet. Dadurch wird die Ausgabe von Text-Funktion, die den Fehler in der neuen Ausführung blend.  
  
 Nach jeder Zeile ausgerichtet wurde, muss dieser Begriff Fehler deaktiviert werden, um zu verhindern, dass er in die nächste Zeile integriert wird. Der Begriff kann gelöscht werden, durch Aufrufen von `SetTextJustification` mit `nBreakExtra` auf 0 festgelegt.  
  
##  <a name="a-namesetviewportexta--cdcsetviewportext"></a><a name="setviewportext"></a>CDC::SetViewportExt  
 Legt die x und y-Blöcke des Viewports des Gerätekontexts.  
  
```  
virtual CSize SetViewportExt(
    int cx,  
    int cy);  
  
CSize SetViewportExt(SIZE size);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Gibt den X-Umfang des Viewports (in Geräteeinheiten).  
  
 `cy`  
 Gibt den y-Umfang des Viewports (in Geräteeinheiten).  
  
 `size`  
 Gibt die x und y-Blöcke von Viewport (im Geräteeinheiten) an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Blöcke des Viewports als ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt. Wenn ein Fehler auftritt, werden die x- und y-Koordinaten des zurückgegebenen `CSize` Objekt werden auf 0 festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Viewport zusammen mit den Gerätekontext Fenster definiert, wie GDI Punkte im logischen Koordinatensystem Punkt im Koordinatensystem des tatsächlichen Geräts zugeordnet. Also definieren sie, wie GDI logische Koordinaten in logische Koordinaten konvertiert.  
  
 Wenn die folgenden Zuordnungsmodi festgelegt sind, Aufrufe von `SetWindowExt` und `SetViewportExt` werden ignoriert:  
  
|MM_HIENGLISH|MM_LOMETRIC|  
|-------------------|------------------|  
|`MM_HIMETRIC`|`MM_TEXT`|  
|`MM_LOENGLISH`|`MM_TWIPS`|  
  
 Wenn `MM_ISOTROPIC` -Modus festgelegt ist, muss eine Anwendung aufrufen, die `SetWindowExt` Memberfunktion ruft dann `SetViewportExt`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc).  
  
##  <a name="a-namesetviewportorga--cdcsetviewportorg"></a><a name="setviewportorg"></a>CDC::SetViewportOrg  
 Legt den Ursprung des Ausschnitts des Gerätekontexts.  
  
```  
virtual CPoint SetViewportOrg(
    int x,  
    int y);  
  
CPoint SetViewportOrg(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die X-Koordinate (in Geräteeinheiten) der Herkunft des Viewports an. Der Wert muss innerhalb des Bereichs von Koordinatensystem des Geräts sein.  
  
 *y*  
 Gibt die y-Koordinate (in Geräteeinheiten) der Herkunft des Viewports an. Der Wert muss innerhalb des Bereichs von Koordinatensystem des Geräts sein.  
  
 `point`  
 Gibt die Herkunft des Viewports an. Die Werte müssen innerhalb des Bereichs von Koordinatensystem des Geräts sein. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Herkunft des Viewports (in logische Koordinaten) als ein `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Viewport zusammen mit den Gerätekontext Fenster definiert, wie GDI Punkte im logischen Koordinatensystem Punkt im Koordinatensystem des tatsächlichen Geräts zugeordnet. Also definieren sie, wie GDI logische Koordinaten in logische Koordinaten konvertiert.  
  
 Der Ursprung des Ausschnitts markiert den Zeitpunkt in der GDI Fensterursprung, einem Punkt in der angegebenen logischen Koordinatensystem zugeordnet Koordinatensystem des Geräts die **SetWindowOrg** Member-Funktion. GDI ordnet alle sonstigen Punkte, indem Sie die gleichen Verfahren erforderlich, um den Fensterursprung der Ursprung des Ausschnitts zuordnen. Beispielsweise werden alle Punkte in einem Kreis um den Punkt am Fensterursprung in einem Kreis um den Punkt an der Ursprung des Ausschnitts. Auf ähnliche Weise werden alle Punkte in einer Zeile, die den Fensterursprung werden in einer Zeile, die der Ursprung des Ausschnitts durchlaufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc).  
  
##  <a name="a-namesetwindowexta--cdcsetwindowext"></a><a name="setwindowext"></a>CDC::SetWindowExt  
 Legt die x und y-Blöcke im Fenster den Gerätekontext zugeordnet.  
  
```  
virtual CSize SetWindowExt(
    int cx,  
    int cy);  
  
CSize SetWindowExt(SIZE size);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Gibt den X-Umfang (in logischen Einheiten) des Fensters.  
  
 `cy`  
 Gibt den y-Umfang (in logischen Einheiten) des Fensters.  
  
 `size`  
 Gibt die X - und y-Blöcke (in logischen Einheiten) des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Blöcke des Fensters (in logischen Einheiten) als ein `CSize` Objekt. Wenn ein Fehler auftritt, die x- und y-Koordinaten des zurückgegebenen `CSize` Objekt werden auf 0 festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Im Fenster zusammen mit den Viewport Gerätekontext definiert, wie GDI Punkte im logischen Koordinatensystem Punkt im Koordinatensystem Geräts zugeordnet.  
  
 Wenn die folgenden Zuordnungsmodi festgelegt sind, Aufrufe von `SetWindowExt` und `SetViewportExt` Funktionen werden ignoriert:  
  
- `MM_HIENGLISH`  
  
- `MM_HIMETRIC`  
  
- `MM_LOENGLISH`  
  
- `MM_LOMETRIC`  
  
- `MM_TEXT`  
  
- `MM_TWIPS`  
  
 Wenn `MM_ISOTROPIC` -Modus festgelegt ist, muss eine Anwendung aufrufen, die `SetWindowExt` Member-Funktion vor dem Aufruf von `SetViewportExt`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc).  
  
##  <a name="a-namesetwindoworga--cdcsetwindoworg"></a><a name="setwindoworg"></a>CDC::SetWindowOrg  
 Legt den Fensterursprung im des Gerätekontexts.  
  
```  
CPoint SetWindowOrg(
    int x,  
    int y);  
  
CPoint SetWindowOrg(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Ursprungs neue Fenster an.  
  
 *y*  
 Gibt die logische y-Koordinate des Ursprungs neue Fenster an.  
  
 `point`  
 Gibt den logischen Koordinaten des Ursprungs neue Fenster an. Übergeben Sie entweder ein **Punkt** Struktur oder ein `CPoint` -Objekt für diesen Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Ursprung des Fensters als ein `CPoint` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Im Fenster zusammen mit den Viewport Gerätekontext definiert, wie GDI Punkte im logischen Koordinatensystem Punkt im Koordinatensystem Geräts zugeordnet.  
  
 Fensterursprung markiert den im logischen Koordinatensystem aus dem GDI der Ursprung des Ausschnitts, einem Punkt im Koordinatensystem Geräts anhand ordnet der **SetWindowOrg** Funktion. GDI ordnet alle sonstigen Punkte, indem Sie die gleichen Verfahren erforderlich, um den Fensterursprung der Ursprung des Ausschnitts zuordnen. Beispielsweise werden alle Punkte in einem Kreis um den Punkt am Fensterursprung in einem Kreis um den Punkt an der Ursprung des Ausschnitts. Auf ähnliche Weise werden alle Punkte in einer Zeile, die den Fensterursprung werden in einer Zeile, die der Ursprung des Ausschnitts durchlaufen.  
  
##  <a name="a-namesetworldtransforma--cdcsetworldtransform"></a><a name="setworldtransform"></a>CDC::SetWorldTransform  
 Legt eine lineare&2;D-Transformation zwischen Welt und Seite freien Speicherplatzes für den angegebenen Gerätekontext. Diese Transformation kann verwendet werden, zu skalieren, drehen, Verbiegen oder Grafikausgabe zu übersetzen.  
  
```  
BOOL SetWorldTransform(const XFORM& rXform);
```  
  
### <a name="parameters"></a>Parameter  
 `rXform`  
 Ein Verweis auf eine [XFORM](http://msdn.microsoft.com/library/windows/desktop/dd145228) -Struktur, die die Transformationsdaten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL bei Erfolg zurück.  
  
 Gibt 0 bei einem Fehler zurück.  
  
 Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode umschließt die Windows GDI-Funktion [SetWorldTransform](http://msdn.microsoft.com/library/windows/desktop/dd145104).  
  
##  <a name="a-namestartdoca--cdcstartdoc"></a><a name="startdoc"></a>CDC::StartDoc  
 Informiert den Treiber, der ein neuer Druckauftrag gestartet wird und dass alle nachfolgenden `StartPage` und `EndPage` Aufrufe sollte unter dem gleichen Auftrag erst gespoolt werden ein `EndDoc` Aufruf erfolgt.  
  
```  
int StartDoc(LPDOCINFO lpDocInfo);  
int StartDoc(LPCTSTR lpszDocName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDocInfo*  
 Verweist auf eine [DOCINFO](http://msdn.microsoft.com/library/windows/desktop/dd183574) -Struktur, die den Namen des Dokuments und den Namen der Ausgabedatei enthält.  
  
 *lpszDocName*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Dokuments enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert größer als&0; (null). Dieser Wert ist der Druckauftrag Bezeichner für das Dokument.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert kleiner oder gleich&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird sichergestellt, dass Dokumente, die mehr als eine Seite nicht mit anderen Aufträgen kombiniert werden können.  
  
 Für Windows-Versionen 3.1 und höher, diese Funktion ersetzt die **STARTDOC** Druckerescape. Mit dieser Funktion wird sichergestellt, dass alle Dokumente, die mehr als eine Seite mit anderen Druckaufträgen nicht kombiniert werden.  
  
 `StartDoc`sollte nicht in Metadateien verwendet werden.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment ruft den Standarddrucker öffnet einen Druckauftrag und spoolt eine Seite mit "Hello, World!" darauf. Da der zur Verfügung stehen, die von diesem Code ist nicht auf den Drucker, logische Einheiten skaliert haben, der Ausgabetext in eine solche kleinen Buchstaben möglicherweise das Ergebnis nicht lesbar ist. Die CDC-Funktionen, wie z. B. Skalierung `SetMapMode`, `SetViewportOrg`, und `SetWindowExt`, kann verwendet werden, um die Skalierung zu beheben.  
  
 [!code-cpp[NVC_MFCDocView&#41;](../../mfc/codesnippet/cpp/cdc-class_13.cpp)]  
  
##  <a name="a-namestartpagea--cdcstartpage"></a><a name="startpage"></a>CDC::StartPage  
 Rufen Sie diese Memberfunktion zum Vorbereiten des Druckertreibers, um Daten zu empfangen.  
  
```  
int StartPage();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Größer als oder gleich 0, wenn die Funktion erfolgreich ist, oder einen negativen Wert, wenn ein Fehler aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 `StartPage`hat Vorrang vor der **NEWFRAME** und **BANDINFO** mit Escapezeichen zu versehen.  
  
 Eine Übersicht über die Aufrufsequenz drucken, finden Sie unter der [StartDoc](#startdoc) Member-Funktion.  
  
 Deaktiviert das System die `ResetDC` Memberfunktion zwischen Aufrufen von `StartPage` und `EndPage`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC::StartDoc](#startdoc).  
  
##  <a name="a-namestretchblta--cdcstretchblt"></a><a name="stretchblt"></a>CDC::StretchBlt  
 Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck, wobei das Bitmap gestreckt oder komprimiert wird, falls dies notwendig ist, um zu den Maßen des Zielrechtecks zu passen.  
  
```  
BOOL StretchBlt(
    int x,  
    int y,  
    int nWidth,  
    int nHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nSrcWidth,  
    int nSrcHeight,  
    DWORD dwRop);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Zielrechtecks an.  
  
 *y*  
 Gibt die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Zielrechtecks an.  
  
 `nWidth`  
 Gibt die Breite (in logischen Einheiten) des Zielrechtecks an.  
  
 `nHeight`  
 Gibt die Höhe (in logischen Einheiten) des Zielrechtecks an.  
  
 `pSrcDC`  
 Gibt den Quellgerätekontext an.  
  
 `xSrc`  
 Gibt die x-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quellrechtecks an.  
  
 `ySrc`  
 Gibt die y-Koordinate (in logischen Einheiten) der oberen linken Ecke des Quellrechtecks an.  
  
 `nSrcWidth`  
 Gibt die Breite (in logischen Einheiten) des Quellrechtecks an.  
  
 `nSrcHeight`  
 Gibt die Höhe (in logischen Einheiten) des Quellrechtecks an.  
  
 *dwRop*  
 Gibt das Raster des auszuführenden Vorgangs an. Rastervorgangscode definiert, wie GDI Farben in Ausgabevorgängen kombiniert, an denen ein aktueller Pinsel, eine mögliche Quellbitmap und eine Zielbitmap beteiligt sind. Dieser Parameter kann möglicherweise einen der folgenden Werte aufweisen:  
  
- **BLACKNESS** Ausgabe Schwarz.  
  
- **DSTINVERT** Hierdurch wird die Zielbitmap.  
  
- **MERGECOPY** das Muster und die Quellbitmap mithilfe des booleschen AND-Operators kombiniert.  
  
- **MERGEPAINT** die umgekehrte Quellbitmap mit der Zielbitmap mithilfe des booleschen OR-Operators kombiniert.  
  
- **NOTSRCCOPY** die umgekehrte Quellbitmap in das Ziel kopiert.  
  
- **NOTSRCERASE** kehrt das Ergebnis der Ziel- und Quellbitmaps mithilfe des booleschen Operators OR zu kombinieren.  
  
- **PATCOPY** das Muster in die Zielbitmap kopiert.  
  
- **PATINVERT** das Zielbitmap mithilfe des booleschen XOR-Operators mit dem Muster kombiniert.  
  
- **PATPAINT** die umgekehrte Quellbitmap mithilfe des booleschen OR-Operators mit dem Muster kombiniert. Hierdurch wird das Ziel dieses Vorgangs mithilfe des booleschen OR-Operators mit dem Zielbitmap kombiniert.  
  
- **SRCAND** Pixel der Ziel- und Quellbitmaps mithilfe des booleschen AND-Operators kombiniert.  
  
- **SRCCOPY** die Quellbitmap in die Zielbitmap kopiert.  
  
- **SRCERASE** Hierdurch wird die Zielbitmap und das Ergebnis mit dem Quellbitmap mithilfe des booleschen AND-Operators kombiniert.  
  
- **SRCINVERT** Pixel der Ziel- und Quellbitmaps mithilfe des booleschen XOR-Operators kombiniert.  
  
- **SRCPAINT** Pixel der Ziel- und Quellbitmaps mithilfe des booleschen OR-Operators kombiniert.  
  
- **WHITENESS** Ausgabe weiß.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Bitmap gezeichnet wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion verwendet den Streckmodus des Zielgerätkontexts (durch `SetStretchBltMode` festgelegt), um zu bestimmen, wie die Bitmap gestreckt oder komprimiert werden soll.  
  
 Die `StretchBlt`-Funktion verschiebt die Bitmap vom Quellgerät, das durch `pSrcDC` angegeben ist, zum Zielgerät, das durch das Gerätkontextobjekt repräsentiert wird, dessen Memberfunktion aufgerufen wird. Die Parameter `xSrc`, `ySrc`, `nSrcWidth` und `nSrcHeight` definieren die linke obere Ecke und die Maße des Quellrechtecks. Die *x*, *y*, `nWidth`, und `nHeight` Parameter geben die linke obere Ecke und die Dimensionen des Zielrechtecks. Durch angegebene rastervorgang *DwRop* definiert, wie die Quellbitmap und die Bits bereits auf dem Zielgerät kombiniert werden.  
  
 Die Funktion `StretchBlt` erstellt ein Spiegelbild eines Bitmaps, wenn sich die Vorzeichen der Parameter `nSrcWidth` und `nWidth` oder `nSrcHeight` und `nHeight` unterscheiden. Wenn `nSrcWidth` und `nWidth` unterschiedliche Vorzeichen haben, erstellt die Funktion ein Spiegelbild der Bitmap entlang der x-Achse. Wenn `nSrcHeight` und `nHeight` unterschiedliche Vorzeichen haben, erstellt die Funktion ein Spiegelbild der Bitmap entlang der y-Achse.  
  
 Die Funktion `StretchBlt` streckt oder komprimiert die Quellbitmap im Speicher und kopiert dann das Ergebnis in das Ziel. Wenn ein Muster mit dem Ergebnis zusammengeführt werden soll, wird es erst zusammengeführt, wenn die gestreckte Quellbitmap in das Ziel kopiert wurde. Wenn ein Pinsel verwendet wird, ist es der ausgewählte Pinsel im Zielgerätekontext. Die Zielkoordinaten werden gemäß dem Zielgerätekontext umgewandelt. Die Quellkoordinaten werden gemäß dem Quellgerätekontext umgewandelt.  
  
 Wenn das Ziel, die Quelle und die Musterbitmaps nicht dasselbe Farbformat haben, konvertiert `StretchBlt` die Quelle und die Musterbitmaps so, dass sie mit den Zielbitmaps übereinstimmen. Die Vordergrund- und Hintergrundfarben des Zielgerätekontexts werden bei der Konvertierung verwendet.  
  
 Wenn `StretchBlt` eine monochrome Bitmap in eine farbige konvertiere muss, legt sie weiße Bits (1) für die Hintergrundfarbe und schwarze Bits (0) für die Vordergrundfarbe fest. Um Farbe in monochrom zu verwandeln, legt sie Pixel, die mit der Hintergrundfarbe übereinstimmen, auf weiß (1) fest und legt alle anderen Pixel auf schwarz (0) fest. Die Vordergrund- und Hintergrundfarben des Gerätekontexts mit Farbe werden verwendet.  
  
 Nicht alle Geräte unterstützen die `StretchBlt`-Funktion. Zu bestimmen, ob ein Gerät unterstützt `StretchBlt`, rufen Sie die `GetDeviceCaps` Memberfunktion mit der **RASTERCAPS** index, und überprüfen Sie den Rückgabewert für die **RC_STRETCHBLT** Flag.  
  
##  <a name="a-namestrokeandfillpatha--cdcstrokeandfillpath"></a><a name="strokeandfillpath"></a>CDC::StrokeAndFillPath  
 Schließt alle geöffneten Figuren in einem Pfad, den Umriss des Pfads mit dem aktuellen Stift Striche und inneren mit dem aktuellen Pinsel gefüllt.  
  
```  
BOOL StrokeAndFillPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Gerätekontext muss einen geschlossenen Pfad enthalten. Die `StrokeAndFillPath` Memberfunktion hat dieselbe Wirkung wie das Schließen aller geöffneten Figuren in den Pfad und Verlauf, und füllen den Pfad getrennt, mit der Ausnahme, dass der ausgefüllte Bereich die gestrichelte Region, auch wenn nicht überschneiden des Stifts breit.  
  
##  <a name="a-namestrokepatha--cdcstrokepath"></a><a name="strokepath"></a>CDC::StrokePath  
 Rendert den angegebenen Pfad mit dem aktuellen Stift.  
  
```  
BOOL StrokePath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Gerätekontext muss einen geschlossenen Pfad enthalten.  
  
##  <a name="a-nametabbedtextouta--cdctabbedtextout"></a><a name="tabbedtextout"></a>CDC::TabbedTextOut  
 Rufen Sie diese Memberfunktion zum Schreiben einer Zeichenfolge an der angegebenen Position, erweitern Registerkarten für die Werte im Array der Tabstopp Positionen.  
  
```  
virtual CSize TabbedTextOut(
    int x,  
    int y,  
    LPCTSTR lpszString,  
    int nCount,  
    int nTabPositions,  
    LPINT lpnTabStopPositions,  
    int nTabOrigin);

 
CSize TabbedTextOut(
    int x,  
    int y,  
    const CString& str,  
    int nTabPositions,  
    LPINT lpnTabStopPositions,  
    int nTabOrigin);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Anfangspunkts der Zeichenfolge an.  
  
 *y*  
 Gibt die logische y-Koordinate des Anfangspunkts der Zeichenfolge an.  
  
 `lpszString`  
 Verweist auf die Zeichenfolge zu zeichnen. Sie können entweder einen Zeiger auf ein Array von Zeichen übergeben oder ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt für diesen Parameter.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an. Wenn `nCount` –&1; ist, wird die Länge wird berechnet.  
  
 `nTabPositions`  
 Gibt die Anzahl der Werte im Array der Tabstopp Positionen an.  
  
 `lpnTabStopPositions`  
 Zeigt auf ein Array mit den Positionen-Tabstopp (in logischen Einheiten). Die Tabstopps müssen in aufsteigender Reihenfolge sortiert werden; der kleinste X-Wert sollte das erste Element im Array.  
  
 `nTabOrigin`  
 Gibt die X-Koordinate der Position des ersten aus der Registerkarten (in logischen Einheiten) erweitert werden.  
  
 `str`  
 Ein `CString` -Objekt, das die angegebenen Zeichen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Dimensionen der Zeichenfolge (in logischen Einheiten) als ein `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Text wird in der aktuell ausgewählten Schriftart geschrieben. Wenn `nTabPositions` ist 0 und `lpnTabStopPositions` ist **NULL**, Registerkarten auf acht Mal die durchschnittliche Zeichenbreite erweitert werden.  
  
 Wenn `nTabPositions` beträgt 1, der beendet von der durch den ersten Wert im angegebenen Abstand getrennt werden Registerkarte der `lpnTabStopPositions` Array. Wenn die `lpnTabStopPositions` Array enthält mehr als einen Wert, wird ein Tabstopp für jeden Wert im Array bis zur angegebenen Anzahl `nTabPositions`. Die `nTabOrigin` Parameter kann eine Anwendung aufrufen, die `TabbedTextOut` Funktion mehrmals für eine einzelne Zeile. Wenn die Anwendung die Funktion mit mehr als einmal aufruft der `nTabOrigin` jedes Mal auf denselben Wert festlegen, erweitert die Funktion alle Registerkarten relativ zu der Position `nTabOrigin`.  
  
 Standardmäßig wird die aktuelle Position von der Funktion nicht verwendet oder aktualisiert. Die Anwendung kann aufrufen, wenn eine Anwendung muss die aktuelle Position aktualisieren, wenn sie die Funktion aufruft, die [SetTextAlign](#settextalign) Memberfunktion mit `nFlags` festgelegt **TA_UPDATECP**. Wenn dieses Flag festgelegt ist, ignoriert Windows die *x* und *y* Parameter bei nachfolgenden Aufrufen von `TabbedTextOut`, verwenden Sie stattdessen die aktuelle Position.  
  
##  <a name="a-nametextouta--cdctextout"></a><a name="textout"></a>TextOut  
 Schreibt mithilfe der aktuell ausgewählten Schriftart eine Zeichenfolge an dem angegebenen Speicherort.  
  
```  
virtual BOOL TextOut(
    int x,  
    int y,  
    LPCTSTR lpszString,  
    int nCount);

 
BOOL TextOut(
    int x,
    int y,
    const CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische x-Koordinate des Anfangspunkts des Texts an.  
  
 *y*  
 Gibt die logische y-Koordinate des Anfangspunkts des Texts an.  
  
 `lpszString`  
 Zeigt auf die zu zeichnende Zeichenfolge.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen in der Zeichenfolge an.  
  
 `str`  
 Ein `CString`-Objekt, das die zu zeichnenden Zeichen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Zeichenursprünge befindet sich in der oberen linken Ecke der Zeichenzelle. Standardmäßig wird die aktuelle Position von der Funktion nicht verwendet oder aktualisiert.  
  
 Wenn eine Anwendung muss die aktuelle Position Aktualisieren beim Aufrufen von `TextOut`, kann die Anwendung Aufrufen der `SetTextAlign` Memberfunktion mit `nFlags` festgelegt **TA_UPDATECP**. Wenn dieses Flag festgelegt ist, ignoriert Windows die *x* und *y* Parameter bei nachfolgenden Aufrufen von `TextOut`, verwenden Sie stattdessen die aktuelle Position.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDC:: beginpath](#beginpath).  
  
##  <a name="a-nametransparentblta--cdctransparentblt"></a><a name="transparentblt"></a>CDC::TransparentBlt  
 Rufen Sie diese Memberfunktion zum Übertragen von eines Bit-Datenblocks die Farbe, die einem Rechteck aus Pixeln aus der angegebenen Quellgerätekontext einen Ziel-Gerätekontext entspricht.  
  
```  
BOOL TransparentBlt(
    int xDest,  
    int yDest,
    int nDestWidth,
    int nDestHeight,  
    CDC* pSrcDC,  
    int xSrc,  
    int ySrc,  
    int nSrcWidth,  
    int nSrcHeight,  
    UINT clrTransparent);
```  
  
### <a name="parameters"></a>Parameter  
 `xDest`  
 Gibt die X-Koordinate, in logischen Einheiten von der linken oberen Ecke des Zielrechtecks.  
  
 `yDest`  
 Gibt die y-Koordinate, in logischen Einheiten von der linken oberen Ecke des Zielrechtecks.  
  
 `nDestWidth`  
 Gibt die Breite in logischen Einheiten des Zielrechtecks an.  
  
 `nDestHeight`  
 Gibt die Höhe in logischen Einheiten des Zielrechtecks an.  
  
 `pSrcDC`  
 Ein Zeiger auf den Quellgerätekontext.  
  
 `xSrc`  
 Gibt die X-Koordinate, in logischen Einheiten des Quellrechtecks an.  
  
 `ySrc`  
 Gibt die y-Koordinate, in logischen Einheiten des Quellrechtecks an.  
  
 `nSrcWidth`  
 Gibt die Breite in logischen Einheiten des Quellrechtecks an.  
  
 `nSrcHeight`  
 Gibt die Höhe in logischen Einheiten des Quellrechtecks an.  
  
 `clrTransparent`  
 Die RGB-Farbe in die Quellbitmap als transparent behandelt.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 `TransparentBlt`Transparenz ermöglicht. d. h. die RGB-Farbe erkennbar `clrTransparent` für die Übertragung transparent gerendert wird.  
  
 Weitere Informationen finden Sie unter [TransparentBlt](http://msdn.microsoft.com/library/windows/desktop/dd145141) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameupdatecolorsa--cdcupdatecolors"></a><a name="updatecolors"></a>CDC::UpdateColors  
 Updates Farben der Clientbereich des Gerätekontexts durch Abgleichen den aktuellen im Clientbereich für die Systempalette auf x-Pixel-Basis.  
  
```  
void UpdateColors();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein inaktiver Fenster mit einer realisierten logischen Palette kann aufrufen, `UpdateColors` als Alternative zum Neuzeichnen Clientbereich, wenn die Systempalette ändert.  
  
 Weitere Informationen zur Verwendung von Farbpaletten finden Sie unter [UpdateColors](http://msdn.microsoft.com/library/windows/desktop/dd145166) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Die `UpdateColors` Memberfunktion aktualisiert in der Regel einen Clientbereich schneller als das Neuzeichnen Bereich. Da die Funktion die Übersetzung auf Farbe die Farbe jedes Pixels führt vor der Änderung der Systempalette Basis, führt jeder Aufruf dieser Funktion jedoch einige Farbtreue verloren gehen.  
  
##  <a name="a-namewidenpatha--cdcwidenpath"></a><a name="widenpath"></a>CDC::WidenPath  
 Definiert den aktuellen Pfad als der Bereich, der gezeichnet werden würde, wenn der Pfad mit dem aktuell ausgewählten im Gerätekontext Stift gezeichnet wurden.  
  
```  
BOOL WidenPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nur erfolgreich, wenn der aktuelle Stift eine geometrische Stift erstellt, indem die zweite Version ist `CreatePen` Member-Funktion, oder wenn der Stift, der erstellt wird, mit der ersten Version von `CreatePen` und verfügt über eine Breite in Geräteeinheiten, der größer als 1. Der Gerätekontext muss einen geschlossenen Pfad enthalten. Bzier Kurven im Pfad werden in Sequenzen von geraden Linien, Kurven verbreiterter annähern konvertiert. Daher keine Kurven Bzier verbleiben in der Pfad nach `WidenPath` aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPaintDC-Klasse](../../mfc/reference/cpaintdc-class.md)   
 [CWindowDC-Klasse](../../mfc/reference/cwindowdc-class.md)   
 [CClientDC-Klasse](../../mfc/reference/cclientdc-class.md)   
 [CMetaFileDC-Klasse](../../mfc/reference/cmetafiledc-class.md)

