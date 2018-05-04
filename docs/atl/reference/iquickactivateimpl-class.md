---
title: IQuickActivateImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b87427408483a60cf33b46a1a670095d211b3d80
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl-Klasse
Diese Klasse verbindet Initialisierung Container des Steuerelements in einem einzigen Aufruf.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IQuickActivateImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Ruft die aktuelle Anzeigegröße für eine ausgeführte Steuerelement ab.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Führt eine schnelle Initialisierung von Steuerelementen, die geladen wird.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Benachrichtigt das Steuerelement wie viel Speicherplatz der Container zugewiesen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) Schnittstelle können Verzögerungen zu vermeiden, beim Laden von Steuerelementen durch Kombinieren der Initialisierung in einem einzigen Aufruf von Containern. Die `QuickActivate` -Methode ermöglicht es den Container zum Übergeben eines Zeigers auf eine [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) -Struktur, die Zeiger auf alle Schnittstellen, das Steuerelement enthält benötigt. Bei der Rückgabe, übergibt das Steuerelement wieder einen Zeiger auf eine [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) -Struktur, die Zeiger auf seine eigenen Schnittstellen enthält, die vom Container verwendet werden. Klasse `IQuickActivateImpl` stellt eine Standardimplementierung von **IQuickActivate** und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent  
 Ruft die aktuelle Anzeigegröße für eine ausgeführte Steuerelement ab.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird für eine vollständige Darstellung des Steuerelements und in HIMETRIC-Einheiten angegeben ist.  
  
 Finden Sie unter [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) im Windows SDK.  
  
##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate  
 Führt eine schnelle Initialisierung von Steuerelementen, die geladen wird.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Struktur enthält Zeiger auf die Schnittstellen, die durch das Steuerelement und die Werte einiger ambient-Eigenschaften. Nach der Rückgabe des Steuerelements übergibt einen Zeiger auf eine [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) -Struktur, die Zeiger auf seine eigenen Schnittstellen, die der Container erforderlich sind, und weitere Statusinformationen enthält.  
  
 Finden Sie unter [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) im Windows SDK.  
  
##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent  
 Benachrichtigt das Steuerelement wie viel Speicherplatz der Container zugewiesen wurde.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird in HIMETRIC-Einheiten angegeben.  
  
 Finden Sie unter [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
