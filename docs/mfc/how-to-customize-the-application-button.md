---
title: "Gewusst wie: Anpassen der Anwendungsschaltfl&#228;che | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsschaltfläche, Anpassen"
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gewusst wie: Anpassen der Anwendungsschaltfl&#228;che
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie auf die Anwendungsschaltfläche klicken, wird ein Menü von Befehlen angezeigt.  Normalerweise enthält das Menü dateibezogene Befehle wie **Öffnen**, **Speichern**, **Drucken** und **Beenden**.  
  
 ![Schaltfläche der MFC&#45;Menübandanwendung](../mfc/media/application_button.png "Application\_Button")  
  
 Um die Anwendungsschaltfläche anzupassen, öffnen Sie sie im Fenster **Eigenschaften**, ändern Sie die Eigenschaften, und zeigen Sie das Menüband in der Vorschau.  
  
### Um die Anwendung zu öffnen Sie im Eigenschaftenfenster "  
  
1.  In Visual Studio im Menü **Ansicht**, klicken Sie auf **Ressourcenansicht**.  
  
2.  Doppelklicken Sie in **Ressourcenansicht** auf die Menübandressource, um sie auf der Entwurfsoberfläche anzuzeigen.  
  
3.  Auf Entwurfsoberfläche klicken Sie auf das Anwendungsschaltflächenmenü mit der rechten Maustaste und klicken Sie dann auf **Eigenschaften**.  
  
## Anwendungs\-Schaltflächen\-Eigenschaften  
 In der folgenden Tabelle definiert die Eigenschaften der Anwendungsschaltfläche.  
  
|Eigenschaft|Definition|  
|-----------------|----------------|  
|**Schaltflächen**|Enthält die Auflistung von drei Schaltflächen, die in der rechten unteren Ecke vom Anwendungsmenü werden.|  
|**Beschriftung**|Gibt den Text des Steuerelements.  Anders als andere Menübandelemente werden die nicht Anwendungsschaltfläche Beschriftungstext an.  Stattdessen wird der Text für Barrierefreiheit verwendet.|  
|**HDPI Image**|Gibt den Bezeichner des hohen Punkt pro Zoll\- \(HDPI\)\- Anwendungsschaltflächensymbols an.  Wenn die Anwendung auf einen Monitor für hohe DPI\-Auflösungen ausgeführt wird, wird **HDPI Image** anstelle von **Bild** verwendet.|  
|**HDPI Large Images**|Gibt dem Bezeichner der großen Bilder für hohe DPI\-Auflösungen an.  Wenn die Anwendung auf einen Monitor für hohe DPI\-Auflösungen ausgeführt wird, wird **HDPI Large Images** anstelle von **Große Bilder** verwendet.|  
|**HDPI Small Images**|Gibt dem Bezeichner der kleinen Bilder für hohe DPI\-Auflösungen an.  Wenn die Anwendung auf einen Monitor für hohe DPI\-Auflösungen ausgeführt wird, wird **HDPI Small Images** anstelle von **Kleine Bilder** verwendet.|  
|**ID**|Gibt den Bezeichner des Steuerelements.|  
|**Bild**|Gibt den Bezeichner des Anwendungsschaltflächensymbols an.  Das Symbol ist eine Bitmap des 32\-Bits 26x26, die Alphatransparenz hat.  Die transparenten Teile des Symbols werden hervorgehoben, wenn auf die Anwendungsschaltfläche vorbei geklickt oder angezeigt wird.|  
|**Schlüssel**|Gibt die Zeichenfolge an, die angezeigt wird, wenn TasteTippnavigation aktiviert ist.  Taste\-Tippnavigation wird aktiviert, wenn Sie die ALT\-TASTE drücken.|  
|**Große Bilder**|Gibt den Bezeichner des Bildes, das eine Reihe von Symbolen 32x32 enthält.  Die Symbole werden über die Schaltflächen in der Hauptelementauflistung verwendet.|  
|**Hauptelemente**|Enthält eine Sammlung von Menüelementen, die das Anwendungsmenü werden.|  
|**MRU\-Beschriftung**|Gibt den Text an, der im neuen Listenbereich angezeigt wird.|  
|**Kleine Bilder**|Gibt den Bezeichner des Bildes, das eine Reihe von Symbolen 16x16 enthält.  Die Symbole werden über die Schaltflächen in der Schaltflächenauflistung verwendet.|  
|**Verwendung**|Aktiviert oder deaktiviert den neuen Listenbereich.  Der neue Listenbereich wird im Anwendungsmenü.|  
|**Breite**|Gibt die Breite in Pixel des neuen Listenbereichs an.|  
  
 Das Anwendungsmenü wird nicht auf der Entwurfsoberfläche.  Um es anzuzeigen, müssen Sie entweder das Menüband in der Vorschau anzeigen bzw. die Anwendung ausführen.  
  
#### So das Menüband in der Vorschau anzeigen  
  
-   Klicken Sie auf der **Menüband\-Editor\-SymbolleisteRibbon testen**.  
  
## Siehe auch  
 [Menüband\-Designer \(MFC\)](../mfc/ribbon-designer-mfc.md)