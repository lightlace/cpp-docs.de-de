---
title: 'MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs:
- C++
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb8dc1bbdc496072df829531b0f10aaaca069a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932194"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten
Dieser Artikel beschreibt die vordefinierten Eigenschaftenseiten für ActiveX-Steuerelemente und deren Verwendung zur Verfügung.  
  
 Weitere Informationen zum Verwenden von Eigenschaftenseiten in einem ActiveX-Steuerelement finden Sie unter den folgenden Artikeln:  
  
-   [MFC-ActiveX-Steuerelemente: Eigenschaftenseite](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC bietet drei vordefinierten Eigenschaftenseiten für die Verwendung mit ActiveX-Steuerelemente: `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, und `CLSID_CPicturePropPage`. Diese Seiten Anzeige einer Benutzeroberfläche für die vordefinierten Farbe, Schriftart und Bildeigenschaften, bzw. aus.  
  
 Um diese Eigenschaftenseiten in ein Steuerelement zu integrieren, fügen Sie ihre IDs Code hinzu, der die Steuerelementarray Eigenschaftenseiten IDs initialisiert. Im folgenden Beispiel befindet sich dieser Code in der Implementierungsdatei des Steuerelements (. CPP) initialisiert das Array, das alle drei vordefinierten Eigenschaftenseiten und die Standardseite für die Eigenschaft enthalten (mit dem Namen `CMyPropPage` in diesem Beispiel):  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 Beachten Sie, dass die Anzahl der Eigenschaftenseiten im BEGIN_PROPPAGEIDS-Makro 4 ist. Diese Zahl entspricht der Anzahl der Eigenschaftenseiten von ActiveX-Steuerelement unterstützt.  
  
 Nachdem diese Änderungen vorgenommen wurden, erstellen Sie das Projekt neu. Das Steuerelement hat jetzt die Eigenschaftenseiten für die Schriftart, Bild und Farbeigenschaften.  
  
> [!NOTE]
>  Wenn die vordefinierten Eigenschaftenseiten Steuerelement zugegriffen werden können, kann möglicherweise die MFC-DLL (MFCxx.DLL) mit dem aktuellen Betriebssystem nicht ordnungsgemäß registriert wurde. Dies führt in der Regel am Installieren von Visual C++ unter ein älteres Betriebssystem, die andere als die zurzeit ausgeführt.  
  
> [!TIP]
>  Wenn die vordefinierten Eigenschaftenseiten nicht sichtbar sind (siehe Hinweis oben), registrieren Sie Sie durch Ausführen von RegSvr32.exe über die Befehlszeile mit dem vollständigen Pfadnamen für die DLL.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC ActiveX Controls (MFC-ActiveX-Steuerelemente)](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md)

