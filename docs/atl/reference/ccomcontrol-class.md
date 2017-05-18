---
title: CComControl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
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
ms.openlocfilehash: 387d38f89e8d783c7ae85c2ab960d5e59c1c4009
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontrol-class"></a>CComControl-Klasse
Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse zur Implementierung des Steuerelements.  
  
 *WinBase*  
 Die Basisklasse, die Windowing-Funktionen implementiert. Standardmäßig [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Erstellt ein Fenster für das Steuerelement.|  
|[CComControl::FireOnChanged](#fireonchanged)|Benachrichtigt den Container-Senke, die Eigenschaft eines Steuerelements geändert hat.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Benachrichtigt, dass eine Steuerelementeigenschaft geändert wird und das Objekt der Senke Vorgehensweise bittet Senke des Containers.|  
|[CComControl::MessageBox](#messagebox)|Rufen Sie diese Methode zum Erstellen, anzeigen und verwenden ein Meldungsfeld an.|  
  
## <a name="remarks"></a>Hinweise  
 `CComControl`ist eine Reihe von nützlichen Steuerelemente Hilfsfunktionen und wichtige Datenelemente für ATL-Steuerelementen. Wenn Sie ein standard-Steuerelement oder ein DHTML-Steuerelement mit der ATL-Steuerelement-Assistenten erstellen, leiten der Assistent automatisch eine Klasse von `CComControl`. `CComControl`leitet die meisten seiner Methoden vom [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Weitere Informationen zum Erstellen eines Steuerelements finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen über ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
 Eine Demonstration `CComControl` Methoden und Datenmember, finden Sie unter der [CIRC](../../visual-cpp-samples.md) Beispiel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="ccomcontrol"></a>CComControl::CComControl  
 Der Konstruktor.  
  
```
CComControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) Konstruktor auf und übergibt die `m_hWnd` -Datenmember über vererbt [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>CComControl::ControlQueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der angeforderten Schnittstelle.  
  
 `ppv`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`, oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Behandelt nur Schnittstellen im COM-Zuordnungstabelle.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#15;](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>CComControl::CreateControlWindow  
 Standardmäßig erstellt ein Fenster für das Steuerelement durch Aufrufen von `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Handle für das übergeordnete Fenster oder das Besitzer. Ein gültiges Fensterhandle muss angegeben werden. Das Steuerelementfenster ist auf den Bereich des übergeordneten Fensters beschränkt.  
  
 `rcPos`  
 [in] Die anfängliche Größe und Position des Fensters erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie etwas tun möchten als ein einziges Fenster zu erstellen, z. B. um zwei Fenster zu erstellen, von denen wird zu einer Symbolleiste für das Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM NR.&16;](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>CComControl::FireOnChanged  
 Benachrichtigt den Container-Senke, die Eigenschaft eines Steuerelements geändert hat.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *dispID*  
 [in] Der Bezeichner der Eigenschaft, die geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Klasse, die von abgeleitet ist [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), ruft diese Methode [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) benachrichtigt alle verbundenen `IPropertyNotifySink` Schnittstellen, die die angegebene Steuerelementeigenschaft geändert hat. Wenn eine Klasse nicht von abgeleitet ist `IPropertyNotifySink`, gibt diese Methode `S_OK`. 
  
 Diese Methode ist sicher aufgerufen werden, auch wenn das Steuerelement keine Verbindungspunkte unterstützt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&17;](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit  
 Benachrichtigt, dass eine Steuerelementeigenschaft geändert wird und das Objekt der Senke Vorgehensweise bittet Senke des Containers.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *dispID*  
 [in] Der Bezeichner der Eigenschaft zu ändern.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Klasse, die von abgeleitet ist [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), ruft diese Methode [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) benachrichtigt alle verbundenen `IPropertyNotifySink` Schnittstellen, die die angegebene Steuerelementeigenschaft geändert wird. Wenn eine Klasse nicht von abgeleitet ist `IPropertyNotifySink`, gibt diese Methode `S_OK`.  

  
 Diese Methode ist sicher aufgerufen werden, auch wenn das Steuerelement keine Verbindungspunkte unterstützt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&18;](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>CComControl::MessageBox  
 Rufen Sie diese Methode zum Erstellen, anzeigen und verwenden ein Meldungsfeld an.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Der im Meldungsfeld anzuzeigende Text.  
  
 `lpszCaption`  
 Der Titel des Dateidialogfelds. Wenn NULL (Standard), den Titel "Error" wird verwendet.  
  
 `nType`  
 Gibt den Inhalt und das Verhalten des Dialogfelds. Finden Sie unter der [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Eintrag in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Dokumentation für eine Liste der verschiedenen Meldungsfeldern verfügbar. Die Standardeinstellung bietet eine einfache **OK** Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen ganzzahligen Wert angeben, der unter aufgeführten Menüelement Werte [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Dokumentation.  
  
### <a name="remarks"></a>Hinweise  
 `MessageBox`eignet sich sowohl während der Entwicklung als auch als eine einfache Möglichkeit, eine Warnung oder Fehlermeldung für den Benutzer anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [-Klasse](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl-Klasse](../../atl/reference/ccomcompositecontrol-class.md)

