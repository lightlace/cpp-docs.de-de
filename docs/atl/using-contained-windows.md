---
title: "Using Contained Windows"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Fenster"
  - "contained windows in ATL"
  - "windows [C++], ATL"
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Using Contained Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL\-Werkzeuge enthielten Fenster mit [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md).  Ein enthaltendes Fenster stellt ein Fenster dar, das seine Meldungen in ein Containerobjekt, delegiert, anstatt sie in einer eigenen Klasse zu behandeln.  
  
> [!NOTE]
>  Sie müssen nicht, um eine Klasse von `CContainedWindowT` zu berechnen, um enthaltende Fenster zu verwenden.  
  
 Mit enthaltenden Fenstern können Sie jede übergeordnete Klasse eine vorhandene Windows\-Klasse oder ein vorhandenes Fenster unterzuordnen.  So fügen Sie ein Fenster erstellen, das übergeordnete Klasse eine vorhandene Windows\-Klasse, zuerst den vorhandenen Klassennamen im Konstruktor für das Objekt `CContainedWindowT` angeben.  Anschließend Aufruf `CContainedWindowT::Create`.  Um ein vorhandenes Fenster unterzuordnen, müssen Sie nicht um einen Windows\-Klassennamen \(an den Konstruktor übergeben **NULL** anzugeben\).  Rufen Sie einfach die `CContainedWindowT::SubclassWindow`\-Methode mit dem Handle für das Fenster auf, das als Unterklasse definiert ist.  
  
 Sie verwenden in der Regel enthaltende Fenster als Datenmember einer Containerklasse.  Der Container muss nicht, um ein Fenster befinden, muss jedoch von [CMessageMap](../atl/reference/cmessagemap-class.md) berechnen.  
  
 Ein enthaltendes Fenster kann alternative Meldungszuordnungen verwenden, um die Nachrichten zu bearbeiten.  Wenn Sie mehr als ein Containerelement Fenster haben, sollten Sie einige alternative Meldungszuordnungen, jede deklarieren entsprechend einem separaten enthaltenen Fenster.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Containerklasse mit zwei enthaltenden Fenstern:  
  
 [!CODE [NVC_ATL_Windowing#67](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#67)]  
  
 Weitere Informationen zu enthaltende Fenster, finden Sie im [STELLEN Sie auf](../top/visual-cpp-samples.md) Beispiel.  
  
## Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)