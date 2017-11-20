---
title: "ATL Connection Point Example | Microsoft Docs"
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
  - "Verbindungspunkte [C++], Beispiele"
  - "examples [ATL]"
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ATL Connection Point Example
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird ein Objekt an, das [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) als Ausgangsschnittstelle unterstützt:  
  
 [!CODE [NVC_ATL_Windowing#84](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#84)]  
  
 Wenn Sie `IPropertyNotifySink` als Ausgangsschnittstelle angeben, können Sie [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)\-Klasse anstelle `IConnectionPointImpl` verwenden.  Beispiel:  
  
 [!CODE [NVC_ATL_Windowing#85](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#85)]  
  
## Siehe auch  
 [Verbindungspunkt](../atl/atl-connection-points.md)