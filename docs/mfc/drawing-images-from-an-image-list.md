---
title: "Darstellen von Bildern aus einer Bildliste"
ms.custom: na
ms.date: "12/14/2016"
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
  - "CImageList-Klasse, Bilder zeichnen aus"
  - "zeichnen, Bilder aus der Bilderliste"
  - "Bilderlisten [C++], Bilder zeichnen aus"
  - "Bilder [C++], zeichnen"
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Darstellen von Bildern aus einer Bildliste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein Bild zu zeichnen, verwenden Sie die [CImageList::Draw](../Topic/CImageList::Draw.md)\-Memberfunktion.  Sie geben einen Zeiger auf ein Gerätekontextobjekt, der Index des Bildes, um zu zeichnen, der Speicherort im Gerätekontext, an dem das Bild gezeichnet und ein Satz von Flags, um dem Zeichnungsformat anzugeben.  
  
 Wenn Sie dem Stil `ILD_TRANSPARENT` angeben, verwendet **Zeichnen** einen Vorgang in zwei Schritten, ein maskiertes Bild zu zeichnen.  Zuerst wird ein Vorgang des logischen AND\-Vorgangs auf den Bits des Bilds und den Bits der Maske aus.  Anschließend führt ein Vorgang LogischXOR auf dem Ergebnis des ersten Vorgangs und der Hintergrundbits des Zielgerätekontexts aus.  Dieser Prozess erstellt transparente Bereiche im resultierenden Bild; das bedeutet, dass jedes Bit weiße in der Maske das entsprechende Bit im resultierenden Bild, transparent sein.  
  
 Bevor Sie ein maskiertes Bild auf einem Volltonfarbenhintergrund zeichnen, können Sie die Memberfunktion [SetBkColor](../Topic/CImageList::SetBkColor.md) verwenden, um die Hintergrundfarbe der Bildliste auf die gleiche Farbe wie das Ziel festzulegen.  Das Festlegen der Farbe entfällt die Notwendigkeit, transparente Bereiche im Bild zu erstellen und aktiviert **Zeichnen**, um das Bild auf Zielgerätekontext, und einen beträchtlichen Anstiegs in der Leistung einfach zu kopieren.  Um das Bild zu zeichnen, geben Sie den `ILD_NORMAL` Format an wenn Sie **Zeichnen** aufrufen.  
  
 Sie können die Hintergrundfarbe für eine maskierte Bildliste \([CImageList](../mfc/reference/cimagelist-class.md)\) jederzeit festlegen, damit sie korrekt auf jedem ausgefüllten Hintergrund.  Das Festlegen der Hintergrundfarbe auf `CLR_NONE` bewirkt Bilder, standardmäßig transparent gezeichnet werden.  Wenn Sie die Hintergrundfarbe einer Bildliste abzurufen, verwenden Sie die [GetBkColor](../Topic/CImageList::GetBkColor.md)\-Memberfunktion.  
  
 Das `ILD_BLEND25` und `ILD_BLEND50` Formatzittern das Bild mit der Systemhervorhebungsfarbe.  Diese Formate sind nützlich, wenn Sie ein maskiertes Bild verwenden, um ein Objekt dargestellt, das der Benutzer auswählen kann.  Beispielsweise können Sie das Format `ILD_BLEND50` verwenden, um das Bild zu zeichnen, wenn der Benutzer es auswählen.  
  
 Ein nicht maskiertes Bild wird dem Zielgerätekontext mithilfe des **SRCCOPY** Rastervorgangs kopiert.  Die Farben im Bild werden identisch dargestellt unabhängig davon die Hintergrundfarbe des Gerätekontexts.  Die Zeichnungsformate, die in **Zeichnen** angegeben haben, werden auch keine Auswirkungen auf die Darstellung eines nicht maskierten Bilds.  
  
 Zusätzlich zur Memberfunktion Videofunktionen erweitert anderen Funktion, [DrawIndirect](../Topic/CImageList::DrawIndirect.md), die Fähigkeit, ein Bild zu rendern.  `DrawIndirect` akzeptiert, als Parameter, eine [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395)\-Struktur.  Diese Struktur kann verwendet werden, um das Rendern des Bilds aktuellen, einschließlich der Verwendung von Rastervorgangs\- \(ROP\)\- Code anpassen.  Weitere Informationen über Überrollschutzvorrichtungs\-Codes, finden Sie unter [Raster\-Operationscodes](http://msdn.microsoft.com/library/windows/desktop/dd162892) und [Bitmaps als Pinsel](http://msdn.microsoft.com/library/windows/desktop/dd183378) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)