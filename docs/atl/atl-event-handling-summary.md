---
title: ATL-Ereignisbehandlung Zusammenfassung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb863f334c00569ef849167cc39d365e0588f666
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-event-handling-summary"></a>ATL-Behandlung Ereigniszusammenfassung
Im Allgemeinen ist die Behandlung von COM-Ereignissen ein relativ einfacher Vorgang. Es gibt drei Hauptschritte:  
  
-   Implementieren Sie die Schnittstelle für das Objekt.  
  
-   Informieren Sie der Ereignisquelle, Ihr Objekt Ereignisse empfangen möchte.  
  
-   Die Ereignisquelle senkereigniszuordnung, wenn Ihr Objekt nicht mehr benötigt wird, um Ereignisse zu empfangen.  
  
## <a name="implementing-the-interface"></a>Implementieren der Schnittstelle  
 Es gibt vier verschiedene Arten der Implementierung einer Schnittstelle mit ATL  
  
|Ableiten von|Eignet sich für Schnittstellentyp|Erfordert, dass Sie alle Methoden * implementieren|Erfordert eine Typbibliothek zur Laufzeit|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|Die Schnittstelle|Vtable|Ja|Nein|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Dual|Ja|Ja|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Disp-Schnittstelle|Nein|Ja|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Disp-Schnittstelle|Nein|Nein|  
  
 \*Wenn Sie ATL-Unterstützungsklassen verwenden zu können, müssen Sie nie implementieren die **IUnknown** oder `IDispatch` Methoden manuell.  
  
## <a name="advising-and-unadvising-the-event-source"></a>Anmelden und Abmelden von der Ereignisquelle  
 Es gibt drei verschiedene Arten von anmelden und Abmelden von einer Ereignisquelle mit ATL  
  
|Advise-Funktion|Senkereigniszuordnung-Funktion|Am besten geeigneten für die Verwendung mit|Erfordert, dass Sie zum Nachverfolgen ein Cookies|Kommentare|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|  

|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)| Vtable oder duale Schnittstellen | Ja | `AtlAdvise` ist eine globale ATL-Funktion. `CComPtrBase::Advise`Dient der [CComPtr](../atl/reference/ccomptr-class.md) und [CComQIPtr](../atl/reference/ccomqiptr-class.md). |  

|[IDispEventSimpleImpl:: DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) oder [ IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)| Nicht | Weniger Parameter als `AtlAdvise` , da die Basisklasse weitere Arbeit ausführt. |  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)| ActiveX-Steuerelementen in zusammengesetzten Steuerelementen | Nicht | `CComCompositeControl::AdviseSinkMap` Member-alle Einträge in der ereignismeldung sink Zuordnung. Die gleiche Funktion werden die Einträge abgemeldet. Diese Methode aufgerufen wird, automatisch von der `CComCompositeControl` Klasse. |  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)| ActiveX-Steuerelemente in einem Dialogfeld | Nicht | `CAxDialogImpl::AdviseSinkMap` Member- und alle ActiveX-Steuerelemente in die Dialogressource unadvises. Dies geschieht automatisch für Sie. |  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)   
 [Unterstützen von IDispEventImpl](../atl/supporting-idispeventimpl.md)

