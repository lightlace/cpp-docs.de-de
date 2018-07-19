---
title: ISpecifyPropertyPagesImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b54b8e4fdfbbfd282475ed0ca6e221d826953cad
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879571"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl-Klasse
Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Füllt ein Array von UUID gezählt-Werte. Jede UUID entspricht die CLSID für eine der Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) Schnittstelle ermöglicht es einen Client zum Abrufen einer Liste von CLSIDs für die Eigenschaftenseiten, die von einem Objekt unterstützten. Klasse `ISpecifyPropertyPagesImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.  
  
> [!NOTE]
>  Machen Sie nicht die `ISpecifyPropertyPages` Schnittstelle, wenn das Objekt Eigenschaftenseiten nicht unterstützt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 Füllt das Array der [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) Struktur mit der CLSID für die Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet eigenschaftenzuordnung des Objekts, um jede CLSID abzurufen.  
  
 Finden Sie unter [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
