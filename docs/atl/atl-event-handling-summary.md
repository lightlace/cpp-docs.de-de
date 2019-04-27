---
title: Zusammenfassung der ATL-Ereignis behandeln
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: 0e3a47719e3160170ed1bfa64b315415ddc7a1c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252147"
---
# <a name="atl-event-handling-summary"></a>Zusammenfassung der ATL-Ereignis behandeln

Im Allgemeinen ist die Behandlung von COM-Ereignissen ein relativ einfacher Prozess. Es gibt drei Hauptschritte:

- Implementieren Sie die Schnittstelle für das Objekt an.

- Empfehlen Sie, dass das Objekt zum Empfangen von Ereignissen soll der Ereignisquelle.

- Abzumelden Sie die Ereignisquelle, wenn das Objekt nicht mehr benötigt wird, um Ereignisse zu empfangen.

## <a name="implementing-the-interface"></a>Implementieren der Schnittstelle

Es gibt vier verschiedene Arten der Implementierung einer Schnittstelle mit ATL

|Leiten Sie von|Eignet sich für den Schnittstellentyp|Erfordert, dass Sie alle Methoden * implementieren|Erfordert eine Typbibliothek zur Laufzeit|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|Die-Schnittstelle|Vtable|Ja|Nein|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Dual|Ja|Ja|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Disp-Schnittstelle|Nein|Ja|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Disp-Schnittstelle|Nein|Nein|

\* Wenn die ATL-Unterstützungsklassen verwenden zu können, nie müssen Sie zum Implementieren der `IUnknown` oder `IDispatch` Methoden manuell.

## <a name="advising-and-unadvising-the-event-source"></a>Anmelden und Abmelden von der Ereignisquelle

Es gibt drei Arten von anmelden und Abmelden von einer Ereignisquelle mit ATL

|Empfehlen Sie Funktion|Abzumelden-Funktion|Am besten geeigneten, für die Verwendung mit|Erfordert, dass Sie zum Nachverfolgen ein Cookies|Kommentare|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable oder duale Schnittstellen|Ja|`AtlAdvise` ist eine globale ATL-Funktion. `CComPtrBase::Advise` Dient der [CComPtr](../atl/reference/ccomptr-class.md) und [CComQIPtr](../atl/reference/ccomqiptr-class.md).|
|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) oder [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Nein|Weniger Parameter als `AtlAdvise` , da die Basisklasse für weitere funktioniert.|
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|ActiveX-Steuerelemente im zusammengesetzten Steuerelementen|Nein|`CComCompositeControl::AdviseSinkMap` empfiehlt, dass alle Einträge in dieser Zuordnung Senke an. Die gleiche Funktion werden die Einträge abgemeldet. Diese Methode aufgerufen wird, automatisch von der `CComCompositeControl` Klasse.|
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|ActiveX-Steuerelemente in einem Dialogfeld|Nein|`CAxDialogImpl::AdviseSinkMap` empfiehlt, und hebt Anweisungen für alle ActiveX-Steuerelemente in der Dialogfeldressource. Dies erfolgt automatisch für Sie.|

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)<br/>
[Unterstützen von IDispEventImpl](../atl/supporting-idispeventimpl.md)
