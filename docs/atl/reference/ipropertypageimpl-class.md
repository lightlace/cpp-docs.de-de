---
title: IPropertyPageImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbc62bd72ee5a639e8df0ada365cd7baac7d0c31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl-Klasse
Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung von der [IPropertyPage-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms691246) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IPropertyPageImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPropertyPageImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPageImpl::Activate](#activate)|Das Dialogfeld für die Eigenschaftsseite "wird erstellt.|  
|[IPropertyPageImpl::Apply](#apply)|Die zugrunde liegenden Objekte, die durch die angegebenen aktuellen Eigenschaftswerte Seite betrifft `SetObjects`. Gibt die ATL-Implementierung `S_OK`.|  
|[IPropertyPageImpl::Deactivate](#deactivate)|Zerstört das Fenster mit erstellt **aktivieren**.|  
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Ruft Informationen über die Eigenschaftenseite.|  
|[IPropertyPageImpl::Help](#help)|Ruft die Windows-Hilfe für die Eigenschaftenseite.|  
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Gibt an, ob die Eigenschaftenseite geändert wurde, da er aktiviert wurde.|  
|[IPropertyPageImpl::Move](#move)|Positioniert, und ändert die Größe der Eigenschaftenseiten-Dialogfeld.|  
|[:: SetDirty](#setdirty)|Kennzeichnet die Eigenschaftenseite geänderten oder unveränderten Zustand.|  
|[IPropertyPageImpl::SetObjects](#setobjects)|Stellt ein Array von **IUnknown** Zeiger für die Eigenschaftenseite zugeordneten Objekte. Diese Objekte erhalten, die aktuellen Eigenschaftswerte für die Seite durch einen Aufruf von **übernehmen**.|  
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Die Eigenschaft wird auf der Seite mit einem `IPropertyPageSite` -Zeiger ist, über die Eigenschaftenseite, mit der Eigenschaft Frame kommuniziert.|  
|[IPropertyPageImpl::Show](#show)|Macht die Eigenschaftenseiten-Dialogfeld, ein- oder ausgeblendet.|  
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Verarbeitet eine Tastatureingabe angegebene.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Gibt an, ob die Eigenschaftenseite Status geändert wurde.|  
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Speichert den Ressourcenbezeichner, der die Textzeichenfolge, beschreibt die Eigenschaftsseite "zugeordnet.|  
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Speichert den Kontextbezeichner für das Hilfethema, das die Eigenschaftsseite "zugeordnet.|  
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Speichert den Ressourcenbezeichner, der den Namen der Hilfedatei, beschreibt die Eigenschaftsseite "zugeordnet.|  
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Speichert den Ressourcenbezeichner zugeordneten die Textzeichenfolge, die auf der Registerkarte der Eigenschaftenseite angezeigt wird.|  
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Speichert die Anzahl der Objekte, die die Eigenschaftsseite "zugeordnet.|  
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Verweist auf die `IPropertyPageSite` Schnittstelle, die über die Eigenschaftenseite, mit der Eigenschaft Frame kommuniziert.|  
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Verweist auf ein Array von **IUnknown** Zeiger auf die Eigenschaftenseite zugeordneten Objekte.|  
|[IPropertyPageImpl::m_size](#m_size)|Speichert die Höhe und Breite des Dialogfelds die Eigenschaftenseite in Pixel an.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPropertyPage-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms691246) Schnittstelle ermöglicht es, ein Objekt, das eine bestimmte Eigenschaft in einem Eigenschaftenblatt verwalten. Klasse `IPropertyPageImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="activate"></a>IPropertyPageImpl::Activate  
 Das Dialogfeld für die Eigenschaftsseite "wird erstellt.  
  
```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist das Dialogfeld immer unabhängig vom Wert von nicht modalen der *bModal* Parameter.  
  
 Finden Sie unter [IPropertyPage::Activate](http://msdn.microsoft.com/library/windows/desktop/ms682250) im Windows SDK.  
  
##  <a name="apply"></a>IPropertyPageImpl::Apply  
 Die zugrunde liegenden Objekte, die durch die angegebenen aktuellen Eigenschaftswerte Seite betrifft `SetObjects`.  
  
```
HRESULT Apply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Apply](http://msdn.microsoft.com/library/windows/desktop/ms691284) im Windows SDK.  
  
##  <a name="deactivate"></a>IPropertyPageImpl::Deactivate  
 Zerstört das Dialogfeld mit erstellt [aktivieren](#activate).  
  
```
HRESULT Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms682504) im Windows SDK.  
  
##  <a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo  
 Füllt die *pPageInfo* Struktur mit Informationen, die in der Datenmember enthalten sind.  
  
```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Hinweise  
 `GetPageInfo`Lädt die Zeichenfolgenressourcen zugeordneten [M_dwDocString](#m_dwdocstring), [M_dwHelpFile](#m_dwhelpfile), und [M_dwTitle](#m_dwtitle).  
  
 Finden Sie unter [IPropertyPage::GetPageInfo](http://msdn.microsoft.com/library/windows/desktop/ms680714) im Windows SDK.  
  
##  <a name="help"></a>IPropertyPageImpl::Help  
 Ruft die Windows-Hilfe für die Eigenschaftenseite.  
  
```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Help](http://msdn.microsoft.com/library/windows/desktop/ms691504) im Windows SDK.  
  
##  <a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl  
 Der Konstruktor.  
  
```
IPropertyPageImpl();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle Datenmember initialisiert.  
  
##  <a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty  
 Gibt an, ob die Eigenschaftenseite geändert wurde, da er aktiviert wurde.  
  
```
HRESULT IsPageDirty(void);
```  
  
### <a name="remarks"></a>Hinweise  
 `IsPageDirty`Gibt `S_OK` , wenn die Seite geändert wurde, seit er aktiviert wurde.  
  
##  <a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty  
 Gibt an, ob die Eigenschaftenseite Status geändert wurde.  
  
```
BOOL m_bDirty;
```  
  
##  <a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects  
 Speichert die Anzahl der Objekte, die die Eigenschaftsseite "zugeordnet.  
  
```
ULONG m_nObjects;
```  
  
##  <a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext  
 Speichert den Kontextbezeichner für das Hilfethema, das die Eigenschaftsseite "zugeordnet.  
  
```
DWORD m_dwHelpContext;
```  
  
##  <a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString  
 Speichert den Ressourcenbezeichner, der die Textzeichenfolge, beschreibt die Eigenschaftsseite "zugeordnet.  
  
```
UINT m_dwDocString;
```  
  
##  <a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile  
 Speichert den Ressourcenbezeichner, der den Namen der Hilfedatei, beschreibt die Eigenschaftsseite "zugeordnet.  
  
```
UINT m_dwHelpFile;
```  
  
##  <a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle  
 Speichert den Ressourcenbezeichner zugeordneten die Textzeichenfolge, die auf der Registerkarte der Eigenschaftenseite angezeigt wird.  
  
```
UINT m_dwTitle;
```  
  
##  <a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite  
 Verweist auf die [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) Schnittstelle, die über die Eigenschaftenseite, mit der Eigenschaft Frame kommuniziert.  
  
```
IPropertyPageSite* m_pPageSite;
```  
  
##  <a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk  
 Verweist auf ein Array von **IUnknown** Zeiger auf die Eigenschaftenseite zugeordneten Objekte.  
  
```
IUnknown** m_ppUnk;
```  
  
##  <a name="m_size"></a>IPropertyPageImpl::m_size  
 Speichert die Höhe und Breite des Dialogfelds die Eigenschaftenseite in Pixel an.  
  
```
SIZE m_size;
```  
  
##  <a name="move"></a>IPropertyPageImpl::Move  
 Positioniert, und ändert die Größe der Eigenschaftenseiten-Dialogfeld.  
  
```
HRESULT Move(LPCRECT pRect);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Move](http://msdn.microsoft.com/library/windows/desktop/ms680118) im Windows SDK.  
  
##  <a name="setdirty"></a>:: SetDirty  
 Kennzeichnet die Eigenschaftenseite Status als geänderten oder unveränderten, abhängig vom Wert `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Parameter  
 `bDirty`  
 [in] Wenn **"true"**, wird die Eigenschaftenseite Zustand als geändert markiert. Er ist, andernfalls gekennzeichnet als unverändert.  
  
### <a name="remarks"></a>Hinweise  
 Bei Bedarf `SetDirty` informiert den Frame, die die Eigenschaftenseite geändert wurde.  
  
##  <a name="setobjects"></a>IPropertyPageImpl::SetObjects  
 Stellt ein Array von **IUnknown** Zeiger für die Eigenschaftenseite zugeordneten Objekte.  
  
```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::SetObjects](http://msdn.microsoft.com/library/windows/desktop/ms678529) im Windows SDK.  
  
##  <a name="setpagesite"></a>IPropertyPageImpl::SetPageSite  
 Die Eigenschaft wird auf der Seite mit einem [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) -Zeiger ist, über die Eigenschaftenseite, mit der Eigenschaft Frame kommuniziert.  
  
```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::SetPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690413) im Windows SDK.  
  
##  <a name="show"></a>IPropertyPageImpl::Show  
 Macht die Eigenschaftenseiten-Dialogfeld, ein- oder ausgeblendet.  
  
```
HRESULT Show(UINT nCmdShow);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Show](http://msdn.microsoft.com/library/windows/desktop/ms694467) im Windows SDK.  
  
##  <a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator  
 Verarbeitet die Tastatureingabe im angegebenen `pMsg`.  
  
```
HRESULT TranslateAccelerator(MSG* pMsg);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms686603) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyPage2Impl-Klasse](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
