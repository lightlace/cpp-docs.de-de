---
title: IQuickActivateImpl-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 9131a1cc1f8d0c66f2eb3616f4903db74ea4bdf0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881372"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl-Klasse
Diese Klasse kombiniert die Initialisierung des Container-Steuerelements in einem einzigen Aufruf.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IQuickActivateImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Ruft die aktuelle Größe für ein Steuerelement ausgeführt.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Führt eine schnelle Initialisierung von Steuerelementen, die geladen werden.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Benachrichtigt das Steuerelement, wie viel Speicherplatz der Container zugewiesen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) -Schnittstelle hilft, Container, die Verzögerungen zu vermeiden, wenn Steuerelemente geladen wird, durch die Kombination der Initialisierung in einem einzigen Aufruf. Die `QuickActivate` -Methode ermöglicht es den Container übergeben eines Zeigers auf eine [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) -Struktur, die Zeiger für sämtliche Schnittstellen, das Steuerelement enthält benötigt. Bei der Rückgabe des Steuerelements übergibt einen Zeiger auf eine [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) -Struktur, die Zeiger auf eine eigene Schnittstellen enthält, die vom Container verwendet werden. Klasse `IQuickActivateImpl` stellt eine Standardimplementierung von `IQuickActivate` und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent  
 Ruft die aktuelle Größe für ein Steuerelement ausgeführt.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe ist für eine vollständige Darstellung des Steuerelements und in HIMETRIC-Einheiten angegeben wird.  
  
 Finden Sie unter [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) in das Windows SDK.  
  
##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate  
 Führt eine schnelle Initialisierung von Steuerelementen, die geladen werden.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Struktur enthält Verweise auf die Schnittstellen, die durch das Steuerelement und die Werte für einige Umgebungseigenschaften. Bei der Rückgabe das Steuerelement übergibt einen Zeiger auf eine [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) Struktur, die Zeiger auf seine eigenen Schnittstellen, die der Container erforderlich sind und weitere Statusinformationen enthält.  
  
 Finden Sie unter [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) in das Windows SDK.  
  
##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent  
 Benachrichtigt das Steuerelement, wie viel Speicherplatz der Container zugewiesen wurde.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird in HIMETRIC-Einheiten angegeben.  
  
 Finden Sie unter [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
