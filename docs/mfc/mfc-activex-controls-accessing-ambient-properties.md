---
title: "MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften | Microsoft Docs"
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
  - "MFC-ActiveX-Steuerelemente, Zugreifen auf Umgebungseigenschaften"
  - "Eigenschaften [MFC], Zugreifen auf die Umgebung"
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Zugreifen auf Umgebungseigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird erläutert, wie ein ActiveX\-Steuerelement in die des Steuerelementcontainers Ambient\-Eigenschaften zugreifen kann.  
  
 Ein Steuerelement kann Informationen über seinen Container abrufen, indem auf die Ambient\-Eigenschaften des Containers zugreift.  Diese Eigenschaften vornehmen visuelle Eigenschaften, wie die Hintergrundfarbe des Containers, die aktuelle Schriftart, die vom Container verwendet werden, und Betriebseigenschaften, wie Container verfügbar ob der gerade im Benutzermodus oder im Designermodus ist.  Ein Steuerelement kann Ambient\-Eigenschaften verwenden, um dessen Darstellung und Verhalten dem bestimmten Containers des, in das es eingebettet ist.  Es sollte ein Steuerelement nie davon ausgehen, dass der Container eine bestimmte Ambient\-Eigenschaft unterstützt.  Tatsächlich unterstützen mehrere Container möglicherweise keine Ambient\-Eigenschaften vorhanden.  In Ermangelung einer Ambient\-Eigenschaft sollte ein Steuerelement einen geeigneten Standardwert aufweisen.  
  
 Um auf eine Ambient\-Eigenschaft zugreifen, lassen Sie [COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md) einen Aufruf.  Diese Funktion erwartet die Dispatch\-ID für die Ambient\-Eigenschaft als ersten Parameter \(die Datei OLECTL.H definiert Dispatch\-IDs für den Standardsatz der Ambient\-Eigenschaften\).  
  
 Die Parameter der `GetAmbientProperty`\-Funktion sind die Dispatch\-ID, ein variantes Tag, das dem erwarteten Eigenschaftentyp an, und ein Zeiger auf den Speicher, in dem der Wert zurückgegeben werden soll.  Der Datentyp, auf den dieser Zeiger verweist, ist abhängig vom varianten Tag.  Die Funktion gibt **TRUE** zurück, wenn der Container die Eigenschaft unterstützt; andernfalls gibt er **FALSE** zurück.  
  
 Im folgenden Codebeispiel ruft den Wert der Ambient\-Eigenschaft, die aufgerufen wird UserMode "." Wenn die Eigenschaft nicht vom Container unterstützt wird, wird ein Standardwert von **TRUE** vorausgesetzt:  
  
 [!CODE [NVC_MFC_AxUI#30](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#30)]  
  
 Für Ihre halber stellt `COleControl` Hilfsfunktionen, die auf viele der häufig verwendeten Ambient\-Eigenschaften zugreifen und geeigneten Standardwert zurück, wenn die Eigenschaften nicht verfügbar sind.  Diese sind Hilfsfunktionen, wie folgt:  
  
-   [COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)  
  
-   [AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)  
  
-   [AmbientFont](../Topic/COleControl::AmbientFont.md)  
  
    > [!NOTE]
    >  Aufrufer muss **Release\( \)** für die zurückgegebene Schriftart aufrufen.  
  
-   [AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)  
  
-   [AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)  
  
-   [AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)  
  
-   [AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)  
  
-   [AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)  
  
-   [AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)  
  
-   [AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)  
  
-   [AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)  
  
 Wenn der Wert einer Ambient\-Eigenschaft \(durch Aktionen des Containers\) ändert, wird die **OnAmbientPropertyChanged**\-Memberfunktion des Steuerelements aufgerufen.  Überschreiben Sie diese Memberfunktion, um eine solche Benachrichtigung zu bearbeiten.  Der Parameter für **OnAmbientPropertyChanged** lautet die Dispatch\-ID der betroffenen Ambient\-Eigenschaft.  Der Wert dieser Dispatch\-ID kann **DISPID\_UNKNOWN**, die angibt, dass eine oder mehrere Ambient\-Eigenschaften geändert hat, jedoch Informationen darüber, welche Eigenschaften beeinflusst wurden, sind nicht verfügbar.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)