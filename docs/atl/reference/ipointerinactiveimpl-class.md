---
title: IPointerInactiveImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
dev_langs:
- C++
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c28eb8d6db520bd1c2d5de5642098263508c0f6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360331"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl-Klasse
Diese Klasse implementiert **IUnknown** und [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) Schnittstellenmethoden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPointerInactiveImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Ruft die aktuelle Aktivierungsrichtlinie für das Objekt ab. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Benachrichtigt, dass das Objekt, das der Mauszeiger darüber verschoben wurde, der angibt, des Objekts Mausereignisse ausgelöst werden kann. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Legt den Mauszeiger für die inaktiven Objekt fest. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Objekt inaktiv ist einfach geladen oder ausgeführt wird. Anders als ein aktives Objekt kann keinem inaktiven Objekt Windows Tastatur- und Nachrichten empfangen. Folglich inaktive Objekten weniger Ressourcen beansprucht und sind in der Regel effizienter.  
  
 Die [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) Schnittstelle ermöglicht es, ein Objekt, das ein mindestlevel an Mausinteraktionen in inaktiven verbleibende unterstützen. Diese Funktion ist besonders nützlich für Steuerelemente.  
  
 Klasse `IPointerInactiveImpl` implementiert die `IPointerInactive` Methoden durch eine einfache Rückkehr **E_NOTIMPL**. Allerdings implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy  
 Ruft die aktuelle Aktivierungsrichtlinie für das Objekt ab.  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470) im Windows SDK.  
  
##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove  
 Benachrichtigt, dass das Objekt, das der Mauszeiger darüber verschoben wurde, der angibt, des Objekts Mausereignisse ausgelöst werden kann.  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374) im Windows SDK.  
  
##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor  
 Legt den Mauszeiger für die inaktiven Objekt fest.  
  
```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
