---
title: IDocHostUIHandlerDispatch-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 936d9b30f18f5ef84c68c55a1607cfcd88d45525
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884612"
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
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115). Auch aufgerufen, wenn MSHTML modale Benutzeroberfläche anzeigt.|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Wird aufgerufen, auf dem Host durch die MSHTML AUFGERUFEN, um dem Host MSHTMLs-Datenobjekt zu ersetzen.|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Vom MSHTML aufgerufen wird, wenn es als Drop-Ziel verwendet wird, wird um dem Host eines alternativen [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Wird vom MSHTML beim Abrufen des Hosts IDispatch-Schnittstelle aufgerufen.|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|Ruft den Benutzeroberflächenfähigkeiten MSHTML-Hosts ab.|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Gibt den Registrierungsschlüssel, unter dem MSHTML benutzereinstellungen speichert.|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|Wird aufgerufen, wenn MSHTML seine Menüs und Symbolleisten entfernt.|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject:: OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|Wird von MSHTML-Implementierung von [IOleInPlaceActiveObject:: OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|Wird von MSHTML-Implementierung von [ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Wird aufgerufen, von der MSHTML AUFGERUFEN, um ein Kontextmenü anzuzeigen.|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|Ermöglicht dem Host MSHTML-Menüs und Symbolleisten zu ersetzen.|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|Wird vom MSHTML aufgerufen, wenn [IOleInPlaceActiveObject:: TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) oder [IOleControlSite:: TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) aufgerufen wird.|  
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









