---
title: "Ändern von Bildeigenschaften (Bildbearbeitung für Symbole) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Image editor [C++], image properties
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f7320d385976ecc401decb8551b420fe8b210b04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="changing-image-properties-image-editor-for-icons"></a>Ändern von Bildeigenschaften (Bildbearbeitung für Symbole)
Sie können festlegen oder Ändern der Eigenschaften eines Bilds mithilfe der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-change-an-images-properties"></a>So ändern Sie ein Image-Eigenschaften  
  
1.  Öffnen Sie das Bild in der **Image** Editor.  
  
2.  In der **Eigenschaften** Fenster einzelne oder alle Eigenschaften für das Bild zu ändern.  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |**Farben**|Gibt das Farbschema für das Bild an. Wählen Sie Monochrom, 16, 256, oder True Farbe. Wenn Sie bereits das Image mit einer 16-Farben-Palette gezeichnet wurden, führt dazu, dass auswählen Monochrom substitutionen Schwarz und weiß für die Farben in der Abbildung. Kontrast wird nicht immer beibehalten: z. B. angrenzende Bereichen Rot-Grün sind sowohl in Schwarz konvertiert.|  
    |**Filename**|Gibt den Namen der Bilddatei. Standardmäßig weist Visual Studio einen Basisdateinamen erstellt durch das Entfernen der ersten vier Zeichen ("IDB_") aus den Standard-Ressourcenbezeichner (IDB_BITMAP1) und die entsprechende Erweiterung hinzugefügt. Der Dateiname für das Bild in diesem Beispiel BITMAP1.bmp. Es kann in MEINEBITMAP1.bmp umbenannt werden.|  
    |**Höhe**|Legt die Höhe des Bilds (in Pixel) fest. Der Standardwert ist 48. Das Bild zugeschnitten wird, oder leeren Bereich unten das vorhandene Bild hinzugefügt wird.|  
    |**ID**|Legt die Ressourcen-ID fest. Für ein Bild, Microsoft Visual Studio, in der Standardeinstellung weist den nächsten verfügbaren Bezeichner in einer Reihe: IDB_BITMAP1, IDB_BITMAP2 usw. lauten. Ähnliche Namen werden für Symbole und Cursor verwendet.|  
    |**Palette**|Ändert die Farbeigenschaften. Doppelklicken Sie auf eine andere Farbe auswählen und Anzeigen der [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Definieren Sie die Farbe, indem Sie RGB- oder HSL-Werte in die entsprechenden Textfelder eingeben.|  
    |**SaveCompressed**|Gibt an, ob das Bild in einem komprimierten Format ist. Diese Eigenschaft ist schreibgeschützt. Visual Studio lässt Sie Bilder in einem komprimierten Format gespeichert werden jedoch nicht damit für alle Bilder in Visual Studio erstellt wurden, diese Eigenschaft werden **"false"**. Wenn Sie ein komprimiertes Bild (in einem anderen Programm erstellt) in Visual Studio öffnen, wird diese Eigenschaft werden **"true"**. Wenn Sie ein komprimiertes Bild in Visual Studio speichern, wird nicht komprimiert, und diese Eigenschaft wird auf zurückgesetzt **"false"**.|  
    |**Breite**|Legt die Breite des Bilds (in Pixel) fest. Der Standardwert für Bitmaps ist 48. Das Bild zugeschnitten wird, oder Leerzeichen rechts neben das vorhandene Bild hinzugefügt wird.|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](https://msdn.microsoft.com/library/f45fce5x.aspx) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](https://msdn.microsoft.com/library/xbx3z216.aspx). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Anforderungen  
  
 Keine  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

