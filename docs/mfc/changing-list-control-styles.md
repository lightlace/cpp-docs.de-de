---
title: "&#196;ndern der Stile von Listensteuerelementen | Microsoft Docs"
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
  - "CListCtrl-Klasse, Ändern von Formaten"
  - "CListCtrl-Klasse, Stile"
  - "Stile, CListCtrl"
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# &#196;ndern der Stile von Listensteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können den Fensterstil eines Listensteuerelements \([Verwendung](../mfc/reference/clistctrl-class.md)\) jederzeit ändern, nachdem Sie sie erstellen.  Mit den Fensterstil ändern, ändern Sie die Art der Ansicht, die das Steuerelement verwendet.  Um beispielsweise den Explorer zu emulieren, können Sie Menüelemente oder Symbolleisten\-Schaltflächen für das Wechseln des Steuerelements zwischen verschiedenen Ansichten angezeigt: Symbolen, ListView, u. a.  
  
 Wenn der Benutzer das Menüelement auswählt, können Sie einen Aufruf das aktuelle Format des Steuerelements abrufen und dann [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) aufrufen lassen [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584), um das Format zurückzusetzen.  Weitere Informationen finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Verwenden der Listenansicht\-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
 Verfügbare Stile sind in [Erstellen](../Topic/CListCtrl::Create.md) aufgeführt.  Die Formate `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST` und `LVS_REPORT` legen die vier Listensteuerelementansichten fest.  
  
## Erweiterte Stile  
 Neben den Standardformaten für ein Listensteuerelement, gibt es einen anderen Satz, als erweiterte Stile.  Diese Formate, erläutert in [Erweiterte Listenansichts\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb774732) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], stellen eine Vielzahl nützlicher Funktionen, die das Verhalten des Listensteuerelements anpassen.  Um das Verhalten eines bestimmten Stils implementieren \(z Bewegung des Mauszeigerss\-Auswahl\), lassen Sie [CListCtrl::SetExtendedStyle](../Topic/CListCtrl::SetExtendedStyle.md) einen Aufruf und das erforderliche Format übergeben.  Im folgenden Beispiel wird den Funktionsaufruf:  
  
 [!CODE [NVC_MFCControlLadenDialog#22](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#22)]  
  
> [!NOTE]
>  Damit Bewegung des Mauszeigerss\-Auswahl funktioniert, müssen Sie **LVS\_EX\_ONECLICKACTIVATE** oder **LVS\_EX\_TWOCLICKACTIVATE** auch aktivieren können.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)