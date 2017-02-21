---
title: "Creating an Aggregated Object | Microsoft Docs"
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
  - "aggregate objects [C++], Erstellen"
  - "aggregation [C++], creating aggregated objects"
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Creating an Aggregated Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aggregation delegiert **IUnknown** Aufrufe und stellt einen Zeiger auf **IUnknown** des äußeren Objekts zum inneren Objekt bereit.  
  
### So fügen Sie ein zusammengesetztes Objekt erstellen  
  
1.  Fügen Sie einen **IUnknown** Zeiger dem Klassenobjekt hinzu und initialisieren Sie ihn zu **NULL** im Konstruktor.  
  
2.  Überschreiben [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md), um des Aggregats zu erstellen.  
  
3.  Verwenden Sie den **IUnknown** Zeiger definiert, in Schritt 1, als zweiten Parameter für die [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md)\-Makros.  
  
4.  Überschreiben [FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md), um das **IUnknown** Zeigers freizugeben.  
  
> [!NOTE]
>  Wenn Sie eine Schnittstelle in zusammengesetzten Objekt während `FinalConstruct` verwenden und freigeben, sollten Sie das Makro [DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md) der Definition des Klassenobjekts hinzufügen.  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)