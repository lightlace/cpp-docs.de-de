---
title: "Grafikobjekte"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "HRGN"
  - "HFONT"
  - "HBITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitmaps [C++], Erstellen von Geräteinhalten"
  - "Pinsel, Erstellen von Gerätekontext"
  - "CBitmap-Klasse, HBITMAP-Handletyp"
  - "CBrush-Klasse, HBRUSH-Handletyp"
  - "CFont-Klasse, HFONT-Handletyp"
  - "CPalette-Klasse, HPALETTE-Handletyp"
  - "CPen-Klasse, HPEN-Handletyp"
  - "CRgn-Klasse, HRGN-Handletyp"
  - "Gerätekontexte, Grafikobjekte"
  - "Zeichnung, in Gerätekontexten"
  - "Schriftarten [C++], Erstellen von Gerätekontext"
  - "GDI [C++], Grafikobjektklassen"
  - "GDI-Objekte [C++]"
  - "GDI-Objekte [C++], Grafikobjektklassen"
  - "Grafikobjekte"
  - "Grafikobjekte, Erstellen von Gerätekontext"
  - "HBITMAP und Klassen-CBitmap"
  - "HBRUSH und Klassen-CBrush"
  - "HFONT und Klassen-CFont"
  - "HPALETTE und Klassen-CPalette"
  - "HPEN"
  - "HRGN"
  - "Bilder [C++], Grafikobjekte"
  - "Speicher [C++], Anzeigekontexte"
  - "MFC, Grafikobjekte"
  - "Objekte [C++], Grafik"
  - "Objekte [C++], Grafikobjekte"
  - "Pixelbild- und Gerätekontext"
  - "Palettenobjekte"
  - "Paletten, Erstellen von Gerätekontext"
  - "Zeichenstiftobjekte"
  - "Stifte, Erstellen von Gerätekontext"
  - "Bereichsobjekte"
  - "Bereiche, Erstellen von Gerätekontext"
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Grafikobjekte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows bietet eine Reihe von Zeichentools an, die in Gerätekontexten verwendet werden können.  Es bietet Stifte zum Zeichnen von Linien, Pinsel zum Auffüllen von Innenbereichen und Schriftarten zum Zeichnen von Text.  MFC stellt Grafikobjektklassen bereit, die den Zeichentools in Windows ähneln.  In der folgenden Tabelle werden die verfügbaren Klassen und die entsprechenden Windows\-GDI\-Handletypen \(Graphics Device Interface\) gezeigt.  
  
> [!NOTE]
>  GDI\+ ist in Windows XP enthalten und ist als verteilbare Komponente für Windows NT 4.0 SP6, Windows 2000, Windows 98 und Windows Me verfügbar.  Informationen zum Herunterladen der neuesten verteilbaren Komponente erhalten Sie unter [http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm).  Weitere Informationen finden Sie in der Dokumentation zu GDI\+ SDK bei MSDN: [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp).  
  
 Dieser Artikel beschreibt die Verwendung von diesen Grafikobjektklassen:  
  
### Klassen für Windows\-GDI\-Objekte  
  
|Klasse|Windows\-Handletypen|  
|------------|--------------------------|  
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|  
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|  
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|  
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|  
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|  
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|  
  
> [!NOTE]
>  Die Klasse [CImage](../atl-mfc-shared/reference/cimage-class.md) bietet eine erweiterte Bitmapunterstützung.  
  
 Jede Grafikobjektklasse in der Klassenbibliothek verfügt über einen Konstruktor, mit dem Sie grafische Objekte dieser Klasse erstellen können. Diese müssen Sie anschließend mit der entsprechenden „create“\-Funktion wie `CreatePen` initialisieren.  
  
 Jede Grafikobjektklasse in der Klassenbibliothek verfügt über einen „cast“\-Operator, der ein MFC\-Objekt zum zugehörigen Windows\-Handle umwandelt.  Das resultierende Handle ist gültig, bis das zugeordnete Objekt es trennt.  Verwenden Sie die Memberfunktion **Detach** des Objekts, um das Handle zu trennen.  
  
 Im folgenden Code wird ein `CPen`\-Objekt zu einem Windows\-Handle umgewandelt:  
  
 [!CODE [NVC_MFCDocViewSDI#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#5)]  
  
#### So erstellen Sie ein Grafikobjekt in einem Gerätekontext  
  
1.  Definieren Sie ein Grafikobjekt im Stapelrahmen.  Initialisieren Sie das Objekt mit der „type“\-spezifischen „create“\-Funktion wie `CreatePen`.  Initialisieren Sie alternativ das Objekt im Konstruktor.  Lesen Sie die Ausführungen unter [Ein\- und zweistufige Konstruktion von Objekten](../mfc/one-stage-and-two-stage-construction-of-objects.md). Dort finden Sie einen Beispielcode.  
  
2.  [Wählen Sie das Objekt aus, in dem der aktuelle Gerätekontext](../mfc/selecting-a-graphic-object-into-a-device-context.md) das alte, zuvor ausgewählte Grafikobjekt speichert.  
  
3.  Wenn Sie mit dem aktuellen Grafikobjekt fertig sind, wählen Sie das alte Grafikobjekt zurück im Gerätekontext aus, um dessen Status wiederherzustellen.  
  
4.  Ermöglichen Sie dem „frame“\-zugewiesenen Grafikobjekt, automatisch gelöscht zu werden, wenn der Bereich verlassen wird.  
  
> [!NOTE]
>  Wenn Sie ein Grafikobjekt wiederholt verwenden, können Sie es einmal zuordnen und es im Gerätekontext auswählen, sobald es benötigt wird.  Stellen Sie sicher, ein derartiges Objekt zu löschen, wenn Sie es nicht mehr benötigen.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Ein\- und zweistufige Konstruktion von Grafikobjekten](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Beispiel für das Erstellen eines Stifts in einer oder zwei Phasen](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Auswählen eines Grafikobjekts für einen Gerätekontext](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Einschränkungen für CImage in früheren Betriebssystemen](../mfc/cimage-limitations-with-earlier-operating-systems.md)  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)