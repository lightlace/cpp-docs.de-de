---
title: Klasse IQuickActivateImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4f6b75da64efa12e43fa160c57da4291acae03ca
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl-Klasse
Diese Klasse kombiniert die Initialisierung des Container-Steuerelements in einem einzigen Aufruf.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IQuickActivateImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Ruft die aktuelle Größe für ein Steuerelement ausgeführt.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Führt schnelle Initialisierung von Steuerelementen, die geladen werden.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Benachrichtigt das Steuerelement, wie viel Speicherplatz der Container zugewiesen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) Schnittstelle hilft Container Verzögerungen zu vermeiden, wenn Steuerelemente zu laden, durch die Kombination der Initialisierung in einem einzigen Aufruf. Die `QuickActivate` Methode ermöglicht dem Container übergeben Sie einen Zeiger auf eine [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) -Struktur, die Verweise auf alle Schnittstellen, das Steuerelement enthält benötigt. Bei der Rückgabe das Steuerelement übergibt einen Zeiger auf eine [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) -Struktur, die Zeiger auf seine eigenen Schnittstellen enthält, die vom Container verwendet werden. Klasse `IQuickActivateImpl` stellt eine Standardimplementierung der **IQuickActivate** und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 Ruft die aktuelle Größe für ein Steuerelement ausgeführt.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe ist für eine vollständige Darstellung des Steuerelements und in HIMETRIC-Einheiten angegeben wird.  
  
 Finden Sie unter [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 Führt schnelle Initialisierung von Steuerelementen, die geladen werden.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Struktur enthält Zeiger auf Schnittstellen, die durch das Steuerelement und die Werte einiger ambient-Eigenschaften. Bei der Rückgabe das Steuerelement übergibt einen Zeiger auf eine [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) -Struktur, die Zeiger auf seine eigenen Schnittstellen, die der Container erfordert und zusätzliche Informationen enthält.  
  
 Finden Sie unter [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 Benachrichtigt das Steuerelement, wie viel Speicherplatz der Container zugewiesen wurde.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird in HIMETRIC-Einheiten angegeben.  
  
 Finden Sie unter [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

