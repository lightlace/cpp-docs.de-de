---
title: ISpecifyPropertyPagesImpl Klasse | Microsoft Docs
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
ms.openlocfilehash: 74f10684c32cc5b1b4b07ac30406520c9ba41ddd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362231"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl-Klasse
Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung von der [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Füllt ein Array von UUID gezählt-Werte. Jede UUID entspricht die CLSID für eine der Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) Schnittstelle ermöglicht es einen Client zum Abrufen einer Liste von CLSIDs für Eigenschaftenseiten, die von einem Objekt unterstützt. Klasse `ISpecifyPropertyPagesImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
> [!NOTE]
>  Machen Sie nicht die **ISpecifyPropertyPages** Schnittstelle, wenn Ihr Objekt Eigenschaftenseiten nicht unterstützt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 Füllt das Array der [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) Struktur mit den CLSIDs für Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet der objektzuordnung-Eigenschaft, um jede CLSID abzurufen.  
  
 Finden Sie unter [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
