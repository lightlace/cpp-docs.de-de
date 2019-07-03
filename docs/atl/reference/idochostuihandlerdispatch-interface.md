---
title: IDocHostUIHandlerDispatch-Schnittstelle
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: a60c178eff1e02c3032e792f9a0420dfeab82388
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552166"
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
>  Die Links in der folgenden Tabelle sind die INet-SDK-Referenzthemen für die Mitglieder der [IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) Schnittstelle. `IDocHostUIHandlerDispatch` hat die gleiche Funktion wie `IDocUIHostHandler`, mit dem Unterschied, die `IDocHostUIHandlerDispatch` ist eine Disp-Schnittstelle, wohingegen `IDocUIHostHandler` ist eine benutzerdefinierte Schnittstelle.

|||
|-|-|
|[EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Auch aufgerufen, wenn MSHTML modale Benutzeroberfläche anzeigt.|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Wird aufgerufen, auf dem Host durch die MSHTML AUFGERUFEN, um dem Host MSHTMLs-Datenobjekt zu ersetzen.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Vom MSHTML aufgerufen wird, wenn es als Drop-Ziel verwendet wird, wird um dem Host eines alternativen [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Wird vom MSHTML beim Abrufen des Hosts IDispatch-Schnittstelle aufgerufen.|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|Ruft den Benutzeroberflächenfähigkeiten MSHTML-Hosts ab.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|Gibt den Registrierungsschlüssel, unter dem MSHTML benutzereinstellungen speichert.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|Wird aufgerufen, wenn MSHTML seine Menüs und Symbolleisten entfernt.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|Wird von MSHTML-Implementierung von [ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Wird aufgerufen, von der MSHTML AUFGERUFEN, um ein Kontextmenü anzuzeigen.|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|Ermöglicht dem Host MSHTML-Menüs und Symbolleisten zu ersetzen.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|Wird vom MSHTML aufgerufen, wenn [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) oder [IOleControlSite:: TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) aufgerufen wird.|
|[TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|Wird aufgerufen, durch die MSHTML AUFGERUFEN, um dem Host eine Möglichkeit zum Ändern der URL geladen werden.|
|[UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Benachrichtigt den Host, dass sich der Befehlsstatus geändert hat.|

## <a name="remarks"></a>Hinweise

Ein Host kann die Menüs, Symbolleisten und Kontextmenüs, die von Microsoft HTML-Analyse und -Rendering-Engine (MSHTML) verwendet wird, durch die Implementierung dieser Schnittstelle ersetzen.

## <a name="requirements"></a>Anforderungen

Die Definition dieser Schnittstelle ist als IDL oder C++ verfügbar, wie unten dargestellt.

|Definitionstyp|Datei|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Konnte IRegistrar (ebenfalls in ATLBase.h enthalten)|

## <a name="see-also"></a>Siehe auch

[IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
