---
title: 'Vorgehensweise: Anpassen der Anwendungsschaltfläche | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef82904a5c84847f3f0064cba6dee171c960f135
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401471"
---
# <a name="how-to-customize-the-application-button"></a>Gewusst wie: Anpassen der Anwendungsschaltfläche

Wenn Sie die Schaltfläche "Anwendung" klicken, wird ein Menü mit Befehlen angezeigt. In der Regel das Menü enthält dateibezogenen Befehle wie z. B. **öffnen**, **speichern**, **Drucken**, und **beenden**.

![MFC-Menüband-Schaltfläche "Anwendung"](../mfc/media/application_button.png "Application_button")

Um die Anwendungsschaltfläche anpassen möchten, öffnen Sie es in der **Eigenschaften** , ihre Eigenschaften ändern, und klicken Sie dann eine Vorschau des Menüband-Steuerelements.

### <a name="to-open-the-application-button-in-the-properties-window"></a>Öffnen Sie die Schaltfläche "Anwendung" im Eigenschaftenfenster

1. In Visual Studio auf die **Ansicht** Menü klicken Sie auf **Ressourcenansicht**.

1. In **Ressourcenansicht**, doppelklicken Sie auf die menübandressource, um sie auf der Entwurfsoberfläche anzuzeigen.

1. Klicken Sie auf die Entwurfsoberfläche, mit der rechten Maustaste in des anwendungsschaltflächenmenüs, und klicken Sie dann auf **Eigenschaften**.

## <a name="application-button-properties"></a>Schaltfläche Anwendungseigenschaften

In der folgende Tabelle werden die Eigenschaften der Anwendungsschaltfläche definiert.

|Eigenschaft|Definition|
|--------------|----------------|
|**Schaltflächen**|Enthält die Auflistung von bis zu drei Schaltflächen, die in der Ecke unten rechts von der Anwendung im Menü angezeigt werden.|
|**Beschriftung**|Gibt den Text des Steuerelements. Im Gegensatz zu anderen Menübandelemente zeigt die Schaltfläche "Anwendung" keine Beschriftungstext. Stattdessen wird der Text für die Barrierefreiheit verwendet.|
|**HDPI Image**|Gibt den Bezeichner, der die hohe DPI-Wert (HDPI) Anwendung Schaltflächensymbol. Beim Ausführen der Anwendung auf einen hohen DPI-Monitor **HDPI Image** anstelle **Image**.|
|**HDPI Large Images**|Gibt den Bezeichner der hohen DPI-Wert große Bilder. Beim Ausführen der Anwendung auf einen hohen DPI-Monitor **HDPI Large Images** anstelle **große Bilder**.|
|**HDPI Small Images**|Gibt den Bezeichner der hohen DPI-Wert kleine Bilder. Beim Ausführen der Anwendung auf einen hohen DPI-Monitor **HDPI Small Images** anstelle **kleine Bilder**.|
|**ID**|Gibt den Bezeichner des Steuerelements.|
|**Image**|Gibt den Bezeichner, der das Symbol für die Anwendung. Das Symbol ist eine 32-Bit-26 x 26-Bitmap, die alpha-Transparenz aufweist. Die transparenten Teile des Symbols werden hervorgehoben, wenn die Schaltfläche geklickt wird, oder Normalzustand.|
|**Schlüssel**|Gibt die Zeichenfolge, die angezeigt wird, wenn der Schlüssel-Tipp-Navigation aktiviert ist. Schlüssel-Tipp-Navigation ist aktiviert, wenn Sie die ALT-Taste drücken.|
|**Große Bilder**|Gibt den Bezeichner des Bilds, das eine Reihe von 32 x 32-Symbole enthält. Die Symbole werden von den Schaltflächen in der Main Items-Auflistung verwendet.|
|**Main Items**|Enthält eine Auflistung von Menüelementen, die auf dem Anwendungsmenü angezeigt werden.|
|**MRU Caption**|Gibt den Text in der Liste der zuletzt verwendeten Bereich angezeigt.|
|**Kleine Bilder**|Gibt den Bezeichner des Bilds, das eine Reihe von 16 x 16-Symbole enthält. Die Symbole werden von den Schaltflächen in der Auflistung von Schaltflächen verwendet.|
|**Verwendung**|Aktiviert oder deaktiviert die Liste der zuletzt verwendeten Bereich. Der Liste zuletzt verwendeter-Bereich, die auf dem Anwendungsmenü angezeigt wird.|
|**Breite**|Gibt die Breite in Pixel von der Liste der zuletzt verwendeten Bereich.|

Klicken Sie im Menü für die Anwendung wird nicht auf der Entwurfsoberfläche angezeigt. Um es anzuzeigen, müssen Sie eine Vorschau im Menüband oder führen Sie die Anwendung.

#### <a name="to-preview-the-ribbon-control"></a>Vorschau des Menüband-Steuerelements

- Auf der **Ribbon-Editor-Symbolleiste**, klicken Sie auf **Ribbon testen**.

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

