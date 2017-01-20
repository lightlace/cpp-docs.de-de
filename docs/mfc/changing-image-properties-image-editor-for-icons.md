---
title: "Changing Image Properties (Image Editor for Icons)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "images [C++], properties"
  - "Image editor [C++], Properties window"
  - "Image editor [C++], image properties"
  - "Properties window, image editor"
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Changing Image Properties (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Eigenschaften eines Bildes können im [Eigenschaftenfenster](../Topic/Properties%20Window.md) festgelegt oder geändert werden.  
  
### So ändern Sie die Bildeigenschaften  
  
1.  Öffnen Sie das Bild im Grafik\-Editor.  
  
2.  Ändern Sie im **Eigenschaftenfenster** alle gewünschten Bildeigenschaften.  
  
    |Property|Beschreibung|  
    |--------------|------------------|  
    |**Farben**|Legt das Farbschema des Bildes fest.  Wählen Sie Monochrom, 16 Farben, 256 Farben oder True Color.  Wenn Sie das Bild bereits mit einer 16\-Farben\-Palette gezeichnet haben, ersetzt der Befehl Monochrom die Farben des Bildes durch Schwarzweißwerte.  Kontraste werden nicht immer beibehalten: So werden z. B. benachbarte Rot\-Grün\-Bereiche in Schwarz umgewandelt.|  
    |**Dateiname**|Gibt den Namen der Bilddatei an.  Standardmäßig weist Visual Studio einen Basisdateinamen zu, indem die ersten vier Zeichen \("IDB\_"\) des Standardressourcenbezeichners \(IDB\_BITMAP1\) entfernt werden und die entsprechende Erweiterung hinzugefügt wird.  Der Dateiname des Bildes in diesem Beispiel lautet **BITMAP1.bmp**.  Er kann in **MEINEBITMAP1.bmp** umbenannt werden.|  
    |**Höhe**|Gibt die Höhe des Bildes \(in Pixel\) an.  Der Standardwert ist 48.  Das Bild wird entweder zugeschnitten, oder unterhalb des Bildes wird ein leerer Bereich hinzugefügt.|  
    |**ID**|Legt den Ressourcenbezeichner fest.  Bei einem Bild weist Microsoft Visual Studio standardmäßig den nächsten verfügbaren Bezeichner einer Datenreihe zu: IDB\_BITMAP1, IDB\_BITMAP2 usw.  Für Symbole und Cursor werden ähnliche Namen verwendet.|  
    |**Palette**|Ändert die Farbeigenschaften.  Um eine Farbe auszuwählen und das [Dialogfeld "Benutzerdefinierte Farbauswahl"](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) zu öffnen, doppelklicken Sie auf eine Farbe.  Definieren Sie die Farbe, indem Sie RGB\- oder HSL\-Werte in die entsprechenden Textfelder eingeben.|  
    |**SaveCompressed**|Gibt an, ob das Bild in einem komprimierten Format gespeichert ist.  Diese Eigenschaft ist schreibgeschützt.  Das Speichern von Bildern in einem komprimierten Format wird von Visual Studio nicht unterstützt, sodass diese Eigenschaft für alle in Visual Studio erstellten Bilder **False** lautet.  Wenn Sie ein \(in einem anderen Programm erstelltes\) komprimiertes Bild in Visual Studio öffnen, lautet diese Eigenschaft **True**.  Wenn Sie ein komprimiertes Bild in Visual Studio speichern, wird es dekomprimiert, und die Eigenschaft nimmt wieder den Wert **False** an.|  
    |**Breite**|Gibt die Breite des Bildes \(in Pixel\) an.  Der Standardwert für Bitmaps ist 48 Pixel.  Das Bild wird entweder zugeschnitten, oder rechts vom vorhandenen Bild wird ein leerer Bereich hinzugefügt.|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)