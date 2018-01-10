---
title: "Vorgehensweise: Anpassen der Anwendungsschaltfläche | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a4a150985bd5c552b361620df87e34511ef8027
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-customize-the-application-button"></a>Gewusst wie: Anpassen der Anwendungsschaltfläche
Wenn Sie die Schaltfläche klicken, wird ein Menü mit Befehlen angezeigt. In der Regel das Menü enthält dateibezogene Befehle wie z. B. **öffnen**, **speichern**, **Drucken**, und **beenden**.  
  
 ![MFC-Anwendung Menübandschaltfläche](../mfc/media/application_button.png "Application_button")  
  
 Um die Anwendungsschaltfläche anpassen möchten, öffnen Sie es in der **Eigenschaften** , ihre Eigenschaften ändern, und klicken Sie dann das Steuerelement im Menüband in der Vorschau anzeigen.  
  
### <a name="to-open-the-application-button-in-the-properties-window"></a>Um die Anwendungsschaltfläche im Eigenschaftenfenster zu öffnen.  
  
1.  In Visual Studio auf die **Ansicht** Menü klicken Sie auf **Ressourcenansicht**.  
  
2.  In **Ressourcenansicht**, doppelklicken Sie auf die menübandressource für die Anzeige auf der Entwurfsoberfläche angezeigt.  
  
3.  Klicken Sie auf der Entwurfsoberfläche, mit der rechten Maustaste des anwendungsschaltflächenmenüs, und klicken Sie dann auf **Eigenschaften**.  
  
## <a name="application-button-properties"></a>Eigenschaften von Schaltflächen  
 In der folgenden Tabelle definiert die Eigenschaften der Anwendungsschaltfläche.  
  
|Eigenschaft|Definition|  
|--------------|----------------|  
|**Schaltflächen**|Enthält die Auflistung von bis zu drei Schaltflächen, die in der unten rechts auf der die Anwendung im Menü angezeigt werden.|  
|**Beschriftung**|Gibt den Text des Steuerelements. Im Gegensatz zu anderen Menübandelemente zeigt die Anwendungsschaltfläche keine Beschriftungstext. Stattdessen wird der Text für den Zugriff verwendet.|  
|**HDPI-Bild**|Gibt den Bezeichner für die hohe Punkte pro Zoll (HDPI) Anwendung Schaltflächensymbol. Beim Ausführen der Anwendung auf einen hohen DPI-Monitor **HDPI-Image** anstelle von **Image**.|  
|**HDPI große Bilder**|Gibt den Bezeichner der hohen DPI große Bilder. Beim Ausführen der Anwendung auf einen hohen DPI-Monitor **HDPI große Bilder** anstelle von **große Bilder**.|  
|**HDPI kleine Bilder**|Gibt den Bezeichner der hohen DPI kleine Bilder. Beim Ausführen der Anwendung auf einen hohen DPI-Monitor **HDPI kleine Bilder** anstelle von **kleine Bilder**.|  
|**ID**|Gibt den Bezeichner des Steuerelements.|  
|**Image**|Gibt den Bezeichner, der das Symbol für die Anwendung. Das Symbol "ist eine 32-Bit-26 x 26-Bitmap, die alpha-Transparenz aufweist. Die transparente Bereiche des Symbols werden hervorgehoben, wenn die Schaltfläche geklickt oder über bewegt wird.|  
|**Schlüssel**|Gibt die Zeichenfolge, die angezeigt wird, wenn der Schlüssel-Tipp Navigation aktiviert ist. Schlüssel Tipp Navigation wird aktiviert, wenn Sie ALT-Taste drücken.|  
|**Große Bilder**|Gibt den Bezeichner des Bildes, das eine Reihe von 32 x 32 Symbole enthält. Die Symbole werden von den Schaltflächen in der Main Items-Auflistung verwendet.|  
|**Main-Elemente**|Enthält eine Auflistung von Menüelementen, die die Anwendung im Menü angezeigt werden.|  
|**MRU-Beschriftung**|Gibt den Text im Bereich der Liste zuletzt geöffneter Wissensdatenbanken angezeigt.|  
|**Kleine Bilder**|Gibt den Bezeichner des Bildes, das eine Reihe von 16 x 16-Symbole enthält. Die Symbole werden von den Schaltflächen in der Auflistung Schaltflächen verwendet.|  
|**Verwendung**|Aktiviert oder deaktiviert den Bereich der Liste zuletzt geöffneter Wissensdatenbanken. Die Liste zuletzt verwendeter Bereich wird auf dem Anwendungsmenü angezeigt.|  
|**Breite**|Gibt die Breite in Pixeln im Bereich der Liste zuletzt geöffneter Wissensdatenbanken an.|  
  
 Anwendungsmenü wird nicht auf der Entwurfsoberfläche angezeigt. Um diese anzuzeigen, müssen Sie das Menüband in der Vorschau anzeigen oder die Anwendung ausführen.  
  
#### <a name="to-preview-the-ribbon-control"></a>Um das Steuerelement im Menüband in der Vorschau anzeigen  
  
-   Auf der **Ribbon-Editor-Symbolleiste**, klicken Sie auf **Ribbon testen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

