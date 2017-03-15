---
title: IPropertyPageImpl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1179e13eb33f09a363c7a3f4425a9ebf13c73b91
ms.lasthandoff: 02/24/2017

---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl-Klasse
Diese Klasse implementiert **IUnknown** und enthält die standardmäßige Implementierung der [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IPropertyPageImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IPropertyPageImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPageImpl::Activate](#activate)|Wird das Dialogfeld für die Eigenschaftenseite erstellt.|  
|[IPropertyPageImpl::Apply](#apply)|Für die aktuellen Eigenschaftswerte Seite zugrunde liegenden Objekte über angegeben `SetObjects`. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IPropertyPageImpl::Deactivate](#deactivate)|Zerstört das Fenster erstellt wurde, mit **aktivieren**.|  
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Ruft Informationen über die Eigenschaftenseite.|  
|[IPropertyPageImpl::Help](#help)|Ruft die Windows-Hilfe für die Eigenschaftenseite.|  
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Gibt an, ob die Eigenschaftenseite geändert wurde, seit es aktiviert wurde.|  
|[IPropertyPageImpl::Move](#move)|Positioniert, und ändert die Größe der Eigenschaftenseiten-Dialogfeld.|  
|[:: SetDirty](#setdirty)|Flags, die Eigenschaftenseite Zustand als geändert oder nicht geändert.|  
|[IPropertyPageImpl::SetObjects](#setobjects)|Bietet eine Reihe von **IUnknown** Zeiger für die Objekte, die mit der Eigenschaftenseite verknüpft ist. Diese Objekte erhalten, die aktuellen Eigenschaftswerte für die Seite durch einen Aufruf von **übernehmen**.|  
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Die Eigenschaft wird auf der Seite mit einer `IPropertyPageSite` Zeiger, die auf der Seite der Kommunikation zwischen dem mit der Eigenschaft Frame.|  
|[IPropertyPageImpl::Show](#show)|Macht die Eigenschaftenseiten-Dialogfeld, sichtbar oder unsichtbar.|  
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Verarbeitet eine Tastatureingabe angegebene.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Gibt an, ob die Eigenschaftenseite Zustand geändert hat.|  
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Speichert den Ressourcenbezeichner, der die Zeichenfolge zur Beschreibung der Eigenschaftenseite zugeordnet.|  
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Speichert die Kontext-ID für das Hilfethema, das mit der Eigenschaftenseite verknüpft ist.|  
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Speichert den Ressourcenbezeichner, der den Namen der Hilfedatei zur Beschreibung der Eigenschaftenseite zugeordnet.|  
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Speichert den Ressourcenbezeichner zugeordnete Zeichenfolge, die auf der Registerkarte der Eigenschaftenseite angezeigt wird.|  
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Speichert die Anzahl der Objekte, die mit der Eigenschaftenseite verknüpft ist.|  
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Verweist auf die `IPropertyPageSite` Schnittstelle, die auf der Seite der Kommunikation zwischen dem mit der Eigenschaft Frame.|  
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Verweist auf ein Array von **IUnknown** Zeiger zu den Objekten, die mit der Eigenschaftenseite verknüpft ist.|  
|[IPropertyPageImpl::m_size](#m_size)|Speichert die Höhe und Breite des Dialogfelds die Eigenschaftenseite in Pixel.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) Schnittstelle ermöglicht es, ein Objekt, das eine bestimmte Eigenschaftenseite in einem Eigenschaftenblatt zu verwalten. Klasse `IPropertyPageImpl` bietet eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="a-nameactivatea--ipropertypageimplactivate"></a><a name="activate"></a>IPropertyPageImpl::Activate  
 Wird das Dialogfeld für die Eigenschaftenseite erstellt.  
  
```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld wird standardmäßig immer nicht modal, unabhängig vom Wert der *bModal* Parameter.  
  
 Finden Sie unter [IPropertyPage::Activate](http://msdn.microsoft.com/library/windows/desktop/ms682250) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameapplya--ipropertypageimplapply"></a><a name="apply"></a>IPropertyPageImpl::Apply  
 Für die aktuellen Eigenschaftswerte Seite zugrunde liegenden Objekte über angegeben `SetObjects`.  
  
```
HRESULT Apply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Apply](http://msdn.microsoft.com/library/windows/desktop/ms691284) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedeactivatea--ipropertypageimpldeactivate"></a><a name="deactivate"></a>IPropertyPageImpl::Deactivate  
 Zerstört das Dialogfeldfenster erstellt mit [aktivieren](#activate).  
  
```
HRESULT Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms682504) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpageinfoa--ipropertypageimplgetpageinfo"></a><a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo  
 Füllt die *pPageInfo* Struktur mit Daten in die Datenmember.  
  
```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Hinweise  
 `GetPageInfo`Lädt die Zeichenfolgenressourcen zugeordneten [M_dwDocString](#m_dwdocstring), [M_dwHelpFile](#m_dwhelpfile), und [M_dwTitle](#m_dwtitle).  
  
 Finden Sie unter [IPropertyPage::GetPageInfo](http://msdn.microsoft.com/library/windows/desktop/ms680714) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehelpa--ipropertypageimplhelp"></a><a name="help"></a>IPropertyPageImpl::Help  
 Ruft die Windows-Hilfe für die Eigenschaftenseite.  
  
```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Help](http://msdn.microsoft.com/library/windows/desktop/ms691504) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameipropertypageimpla--ipropertypageimplipropertypageimpl"></a><a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl  
 Der Konstruktor.  
  
```
IPropertyPageImpl();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert alle Datenmember.  
  
##  <a name="a-nameispagedirtya--ipropertypageimplispagedirty"></a><a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty  
 Gibt an, ob die Eigenschaftenseite geändert wurde, seit es aktiviert wurde.  
  
```
HRESULT IsPageDirty(void);
```  
  
### <a name="remarks"></a>Hinweise  
 `IsPageDirty`Gibt `S_OK` , wenn die Seite geändert wurde, seit es aktiviert wurde.  
  
##  <a name="a-namembdirtya--ipropertypageimplmbdirty"></a><a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty  
 Gibt an, ob die Eigenschaftenseite Zustand geändert hat.  
  
```
BOOL m_bDirty;
```  
  
##  <a name="a-namemnobjectsa--ipropertypageimplmnobjects"></a><a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects  
 Speichert die Anzahl der Objekte, die mit der Eigenschaftenseite verknüpft ist.  
  
```
ULONG m_nObjects;
```  
  
##  <a name="a-namemdwhelpcontexta--ipropertypageimplmdwhelpcontext"></a><a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext  
 Speichert die Kontext-ID für das Hilfethema, das mit der Eigenschaftenseite verknüpft ist.  
  
```
DWORD m_dwHelpContext;
```  
  
##  <a name="a-namemdwdocstringa--ipropertypageimplmdwdocstring"></a><a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString  
 Speichert den Ressourcenbezeichner, der die Zeichenfolge zur Beschreibung der Eigenschaftenseite zugeordnet.  
  
```
UINT m_dwDocString;
```  
  
##  <a name="a-namemdwhelpfilea--ipropertypageimplmdwhelpfile"></a><a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile  
 Speichert den Ressourcenbezeichner, der den Namen der Hilfedatei zur Beschreibung der Eigenschaftenseite zugeordnet.  
  
```
UINT m_dwHelpFile;
```  
  
##  <a name="a-namemdwtitlea--ipropertypageimplmdwtitle"></a><a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle  
 Speichert den Ressourcenbezeichner zugeordnete Zeichenfolge, die auf der Registerkarte der Eigenschaftenseite angezeigt wird.  
  
```
UINT m_dwTitle;
```  
  
##  <a name="a-namemppagesitea--ipropertypageimplmppagesite"></a><a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite  
 Verweist auf die [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) Schnittstelle, die auf der Seite der Kommunikation zwischen dem mit der Eigenschaft Frame.  
  
```
IPropertyPageSite* m_pPageSite;
```  
  
##  <a name="a-namemppunka--ipropertypageimplmppunk"></a><a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk  
 Verweist auf ein Array von **IUnknown** Zeiger zu den Objekten, die mit der Eigenschaftenseite verknüpft ist.  
  
```
IUnknown** m_ppUnk;
```  
  
##  <a name="a-namemsizea--ipropertypageimplmsize"></a><a name="m_size"></a>IPropertyPageImpl::m_size  
 Speichert die Höhe und Breite des Dialogfelds die Eigenschaftenseite in Pixel.  
  
```
SIZE m_size;
```  
  
##  <a name="a-namemovea--ipropertypageimplmove"></a><a name="move"></a>IPropertyPageImpl::Move  
 Positioniert, und ändert die Größe der Eigenschaftenseiten-Dialogfeld.  
  
```
HRESULT Move(LPCRECT pRect);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Move](http://msdn.microsoft.com/library/windows/desktop/ms680118) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetdirtya--ipropertypageimplsetdirty"></a><a name="setdirty"></a>:: SetDirty  
 Die Eigenschaftenseite Zustand als geändert oder nicht geändert, abhängig vom Wert des Flags `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Parameter  
 `bDirty`  
 [in] Wenn **TRUE**, die Eigenschaftenseite Zustand wird als geändert markiert. Andernfalls ist er markiert als unverändert.  
  
### <a name="remarks"></a>Hinweise  
 Bei Bedarf `SetDirty` informiert den Frame, der die Eigenschaftenseite geändert wurde.  
  
##  <a name="a-namesetobjectsa--ipropertypageimplsetobjects"></a><a name="setobjects"></a>IPropertyPageImpl::SetObjects  
 Bietet eine Reihe von **IUnknown** Zeiger für die Objekte, die mit der Eigenschaftenseite verknüpft ist.  
  
```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::SetObjects](http://msdn.microsoft.com/library/windows/desktop/ms678529) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetpagesitea--ipropertypageimplsetpagesite"></a><a name="setpagesite"></a>IPropertyPageImpl::SetPageSite  
 Die Eigenschaft wird auf der Seite mit einer [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) Zeiger, die auf der Seite der Kommunikation zwischen dem mit der Eigenschaft Frame.  
  
```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::SetPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690413) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowa--ipropertypageimplshow"></a><a name="show"></a>IPropertyPageImpl::Show  
 Macht die Eigenschaftenseiten-Dialogfeld, sichtbar oder unsichtbar.  
  
```
HRESULT Show(UINT nCmdShow);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::Show](http://msdn.microsoft.com/library/windows/desktop/ms694467) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nametranslateacceleratora--ipropertypageimpltranslateaccelerator"></a><a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator  
 Verarbeitet die Tastatureingabe im angegebenen `pMsg`.  
  
```
HRESULT TranslateAccelerator(MSG* pMsg);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms686603) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyPage2Impl-Klasse](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

