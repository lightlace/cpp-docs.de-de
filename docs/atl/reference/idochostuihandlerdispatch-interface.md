---
title: IDocHostUIHandlerDispatch-Schnittstelle
ms.date: 11/04/2016
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: 5bf405f66bdef54f354f9e6c230207d2933ee352
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483631"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch-Schnittstelle

Eine Schnittstelle, die Microsoft-HTML-Analyse- und -Rendering-Engine.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

> [!NOTE]
>  Die Links in der folgenden Tabelle sind die INet-SDK-Referenzthemen für die Mitglieder der [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) Schnittstelle. `IDocHostUIHandlerDispatch` hat die gleiche Funktion wie `IDocUIHostHandler`, mit dem Unterschied, die `IDocHostUIHandlerDispatch` ist eine Disp-Schnittstelle, wohingegen `IDocUIHostHandler` ist eine benutzerdefinierte Schnittstelle.

|||
|-|-|
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Auch aufgerufen, wenn MSHTML modale Benutzeroberfläche anzeigt.|
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Wird aufgerufen, auf dem Host durch die MSHTML AUFGERUFEN, um dem Host MSHTMLs-Datenobjekt zu ersetzen.|
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Vom MSHTML aufgerufen wird, wenn es als Drop-Ziel verwendet wird, wird um dem Host eines alternativen [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Wird vom MSHTML beim Abrufen des Hosts IDispatch-Schnittstelle aufgerufen.|
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|Ruft den Benutzeroberflächenfähigkeiten MSHTML-Hosts ab.|
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Gibt den Registrierungsschlüssel, unter dem MSHTML benutzereinstellungen speichert.|
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|Wird aufgerufen, wenn MSHTML seine Menüs und Symbolleisten entfernt.|
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|Wird von MSHTML-Implementierung von [ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Wird aufgerufen, von der MSHTML AUFGERUFEN, um ein Kontextmenü anzuzeigen.|
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|Ermöglicht dem Host MSHTML-Menüs und Symbolleisten zu ersetzen.|
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|Wird vom MSHTML aufgerufen, wenn [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) oder [IOleControlSite:: TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) aufgerufen wird.|
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|Wird aufgerufen, durch die MSHTML AUFGERUFEN, um dem Host eine Möglichkeit zum Ändern der URL geladen werden.|
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|Benachrichtigt den Host, dass sich der Befehlsstatus geändert hat.|

## <a name="remarks"></a>Hinweise

Ein Host kann die Menüs, Symbolleisten und Kontextmenüs, die von Microsoft HTML-Analyse und -Rendering-Engine (MSHTML) verwendet wird, durch die Implementierung dieser Schnittstelle ersetzen.

## <a name="requirements"></a>Anforderungen

Die Definition dieser Schnittstelle ist als IDL oder C++ verfügbar, wie unten dargestellt.

|Definitionstyp|Datei|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Konnte IRegistrar (ebenfalls in ATLBase.h enthalten)|

## <a name="see-also"></a>Siehe auch

[IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)

