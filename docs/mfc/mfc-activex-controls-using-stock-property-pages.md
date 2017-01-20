---
title: "MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten"
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
  - "CLSID_CPicturePropPage"
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
  - "CLSID_CPicturePropPage"
  - "Farbbestand-Eigenschaftenseiten"
  - "Schriftarten, ActiveX-Steuerelemente"
  - "MFC-ActiveX-Steuerelemente, Eigenschaftenseiten"
  - "Bildbestand-Eigenschaftenseiten"
  - "Basiseigenschaften, Bestandseigenschaftenseiten"
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden die vordefinierten Eigenschaftenseiten, die für ActiveX\-Steuerelemente verfügbar sind und wie sie verwendet.  
  
 Weitere Informationen zur Verwendung von Eigenschaftenseiten in einem ActiveX\-Steuerelement, finden Sie:  
  
-   [MFC\-ActiveX\-Steuerelemente: Eigenschaftenseiten](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC stellt vordefinierte drei Eigenschaftenseiten für ActiveX\-Steuerelemente: **CLSID\_CColorPropPage**, **CLSID\_CFontPropPage** und **CLSID\_CPicturePropPage**.  Diese Seiten zeigen eine Benutzeroberfläche für vordefinierte Farbe, Schriftart und Bildeigenschaften, bzw. an.  
  
 Um diese Eigenschaftenseiten in ein Steuerelement zu erstellen, fügen Sie deren IDs den Code hinzu der das Array des Steuerelements von Eigenschaftenseite IDs initialisiert.  Im folgenden Beispiel initialisiert dieser Code, in der Steuerimplementierungsdatei \(.CPP\), das Array, um alle drei vordefinierten Eigenschaftenseiten und die Standardeigenschaftsseite enthalten soll \( `CMyPropPage`  in diesem Beispiel\):  
  
 [!CODE [NVC_MFC_AxOpt#21](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#21)]  
  
 Beachten Sie, dass die Anzahl von Eigenschaftenseiten, im Makro `BEGIN_PROPPAGEIDS`, ist. 4.  Dadurch wird die Anzahl der den Eigenschaftenseiten dar, die das ActiveX\-Steuerelement unterstützt werden.  
  
 Nachdem diese Änderungen vorgenommen wurden, erstellen Sie das Projekt neu.  Das Steuerelement hat jetzt Eigenschaftenseiten für die Schriftart, Image\- und die Farbeigenschaften.  
  
> [!NOTE]
>  Wenn auf die Sperrminoritätseigenschaftenseiten nicht zugegriffen werden können, kann es, da die MFC\-DLL \(MFCxx.DLL\) nicht ordnungsgemäß mit dem aktuellen Betriebssystem registriert wurde.  Dies ergibt sich normalerweise durch Installieren von Visual C\+\+ mit einem Betriebssystem, das auf dem derzeit ausgeführten unterscheidet.  
  
> [!TIP]
>  Wenn die vordefinierte Eigenschaftenseiten nicht \(siehe vorherigen Hinweis\), sichtbar sind, registrieren Sie die DLL, indem Sie RegSvr32.exe von der Befehlszeile mit den vollständigen Pfadnamen der DLL ausführen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften](../mfc/mfc-activex-controls-adding-stock-properties.md)