---
title: 'Vorgehensweise: Anpassen der Anwendungs Schaltfläche'
ms.date: 09/07/2019
helpviewer_keywords:
- application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
ms.openlocfilehash: 3a1d1625e80e6c6f4440864629a5123bed5744c7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907789"
---
# <a name="how-to-customize-the-application-button"></a>Vorgehensweise: Anpassen der Anwendungs Schaltfläche

Wenn Sie auf die Schaltfläche Anwendung klicken, wird ein Menü mit Befehlen angezeigt. In der Regel enthält das Menü Datei bezogene Befehle wie " **Öffnen**", " **Speichern**", " **Drucken**" und " **Beenden**".

![Schaltfläche zum MFC-Menüband](../mfc/media/application_button.png "Schaltfläche zum MFC-Menüband")

Um die Anwendungs Schaltfläche anzupassen, öffnen Sie Sie im **Eigenschaften** Fenster (in **Ressourcenansicht**), ändern Sie deren Eigenschaften, und klicken Sie dann in der Vorschau auf das Menü Band Steuerelement.

### <a name="to-open-the-application-button-in-the-properties-window"></a>So öffnen Sie die Anwendungs Schaltfläche im Eigenschaftenfenster

1. Klicken Sie in Visual Studio im Menü **Ansicht** auf **Ressourcenansicht**.

1. Doppelklicken Sie in **Ressourcenansicht**auf die Menüband-Ressource, um Sie auf der Entwurfs Oberfläche anzuzeigen.

1. Klicken Sie auf der Entwurfs Oberfläche mit der rechten Maustaste auf das Schaltflächen Menü Anwendung, und klicken Sie dann auf **Eigenschaften**

## <a name="application-button-properties"></a>Anwendungs Schaltflächen Eigenschaften

In der folgenden Tabelle werden die Eigenschaften der Anwendungs Schaltfläche definiert.

|Eigenschaft|Definition|
|--------------|----------------|
|**Schaltflächen**|Enthält die Auflistung von bis zu drei Schaltflächen, die in der rechten unteren Ecke des Anwendungs Menüs angezeigt werden.|
|**Beschriftung**|Gibt den Text des Steuer Elements an. Im Gegensatz zu anderen Menü Band Elementen zeigt die Anwendungs Schaltfläche nicht den Beschriftungs Text an. Stattdessen wird der Text für die Barrierefreiheit verwendet.|
|**Hdpi-Image**|Gibt den Bezeichner des Anwendungs Schaltflächen Symbols "High dots per inch" (hdpi) an. Wenn die Anwendung auf einem Monitor mit hoher dpi ausgeführt wird, wird das **hdpi-Image** anstelle von **Image**verwendet.|
|**Große hdpi-Images**|Gibt den Bezeichner der großen dpi-Bilder an. Wenn die Anwendung auf einem hohen dpi-Monitor ausgeführt wird, werden **hdpi Large Images** anstelle von **großen Images**verwendet.|
|**Hdpi Small-Images**|Gibt den Bezeichner der kleinen großen dpi-Bilder an. Wenn die Anwendung auf einem hohen dpi-Monitor ausgeführt wird, werden anstelle von **kleinen Abbildern** **hdpi Small Images** verwendet.|
|**ID**|Gibt den Bezeichner des Steuer Elements an.|
|**Image**|Gibt den Bezeichner des Anwendungs Schaltflächen Symbols an. Das Symbol ist eine 32-Bit-26x26-Bitmap mit Alpha Transparenz. Die transparenten Teile des Symbols werden hervorgehoben, wenn auf die Anwendungs Schaltfläche geklickt wird oder darauf gezeigt wird.|
|**Or**|Gibt die Zeichenfolge an, die angezeigt wird, wenn die Schlüssel Tipp Navigation aktiviert ist. Die Tastenkombination wird aktiviert, wenn Sie ALT drücken.|
|**Große Bilder**|Gibt den Bezeichner des Bilds an, das eine Reihe von 32 x 32 Symbolen enthält. Die Symbole werden von den Schaltflächen in der Auflistung der Hauptelemente verwendet.|
|**Hauptelemente**|Enthält eine Auflistung von Menü Elementen, die im Anwendungsmenü angezeigt werden.|
|**MRU-Beschriftung**|Gibt den Text an, der im letzten Listen Bereich angezeigt wird.|
|**Kleine Bilder**|Gibt den Bezeichner des Bilds an, das eine Reihe von 16x16-Symbolen enthält. Die Symbole werden von den Schaltflächen in der Buttons-Auflistung verwendet.|
|**Konsum**|Aktiviert oder deaktiviert den aktuellen Listen Bereich. Der aktuelle Listen Bereich wird im Anwendungsmenü angezeigt.|
|**Width**|Gibt die Breite des aktuellen Listen Bereichs in Pixel an.|

Das Anwendungsmenü wird nicht auf der Entwurfs Oberfläche angezeigt. Um dies anzuzeigen, müssen Sie entweder eine Vorschau der Multifunktionsleiste anzeigen oder die Anwendung ausführen.

#### <a name="to-preview-the-ribbon-control"></a>So können Sie eine Vorschau des Menüband

- Klicken Sie auf der **Symbolleiste des Menüband-Editors**auf **Menüband testen**

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)
