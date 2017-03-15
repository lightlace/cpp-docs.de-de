---
title: "ATL Event Handling Summary | Microsoft Docs"
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
  - "Ereignisbehandlung, Implementieren"
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Event Handling Summary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Allgemeinen COM\-Ereignisse zu behandeln ist ein relativ einfacher Vorgang.  Es gibt drei Hauptschritte:  
  
-   Implementieren Sie die Ereignisschnittstelle für das Objekt.  
  
-   Melden Sie sich die Ereignisquelle an, dass das Objekt Ereignisse empfangen will.  
  
-   Melden Sie sich die Ereignisquelle wenn die Anforderungen des Objekts nicht mehr, Ereignisse empfangen ab.  
  
## Implementieren der Schnittstelle  
 Es gibt vier wichtige Möglichkeiten der Implementierung einer Schnittstelle mit ATL.  
  
|Ableitung von|Passend für Schnittstellentyp|Erfordert Sie, alle methods\* zu implementieren|Erfordert eine Typbibliothek zur Laufzeit|  
|-------------------|-----------------------------------|-----------------------------------------------------|-----------------------------------------------|  
|Die Schnittstelle|Ereignisse beim|Ja|Nein|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Dual|Ja|Ja|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispatchschnittstelle|Nein|Ja|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispatchschnittstelle|Nein|Nein|  
  
 \* Wenn Klassen der ATL\-Unterstützung, werden Sie nie benötigt, die **IUnknown** oder `IDispatch`\-Methoden manuell zu implementieren.  
  
## Die Ereignisquelle anmelden und abmeldend  
 Es gibt drei grundlegende Möglichkeiten des Anmeldens und des Abmeldens einer Ereignisquelle mit ATL.  
  
|Melden Sie sich Funktion an|Melden Sie sich Funktion ab|Am festgestellt werden zur Verwendung mit|Erfordert Sie, ein Cookie nachzuverfolgen?|Kommentare|  
|---------------------------------|---------------------------------|-----------------------------------------------|------------------------------------------------|----------------|  
|[AtlAdvise](../Topic/AtlAdvise.md), [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|[AtlUnadvise](../Topic/AtlUnadvise.md)|Ereignisse beim oder duale Schnittstellen|Ja|`AtlAdvise` ist eine globale ATL\-Funktion.  `CComPtrBase::Advise` wird durch [CComPtr](../atl/reference/ccomptr-class.md) und [CComQIPtr](../atl/reference/ccomqiptr-class.md) verwendet.|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) oder [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Nein|Weniger Parameter als `AtlAdvise`, da die Basisklasse mehr Arbeit durchgeführt.|  
|[CComCompositeControl::AdviseSinkMap \(TRUE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|[CComCompositeControl::AdviseSinkMap \(FALSE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|ActiveX\-Steuerelemente in den zusammengesetzten Steuerelementen|Nein|`CComCompositeControl::AdviseSinkMap` benachrichtigt alle Senkenzuordnung der Einträge im \- Ereignis an.  Dieselbe Funktion benachrichtigt die Einträge ab.  Diese Methode wird automatisch durch die `CComCompositeControl`\-Klasse aufgerufen.|  
|[CAxDialogImpl::AdviseSinkMap \(TRUE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|[CAxDialogImpl::AdviseSinkMap \(FALSE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|ActiveX\-Steuerelemente in einem Dialogfeld|Nein|`CAxDialogImpl::AdviseSinkMap` besagt und benachrichtigt alle ActiveX\-Steuerelemente in der Dialogfeldressource ab.  Dies wird automatisch für Sie fertig.|  
  
## Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)   
 [Supporting IDispEventImpl](../atl/supporting-idispeventimpl.md)