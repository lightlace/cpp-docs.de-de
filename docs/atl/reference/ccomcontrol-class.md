---
title: CComControl Klasse | Microsoft Docs
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae81e2b6beac11f94f8d117b004da2f8d0db8724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcontrol-class"></a>CComControl-Klasse
Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL-Steuerelementen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
 Die Basisklasse, die Fensterfunktionen implementiert. Standardmäßig [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Erstellt ein Fenster für das Steuerelement.|  
|[CComControl::FireOnChanged](#fireonchanged)|Benachrichtigt den Container-Ereignissenke, die eine Steuerelementeigenschaft geändert wurde.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Benachrichtigt Senke für den Container, eine Steuerelementeigenschaft geändert wird, sodass das Objekt der Senke zum Fortsetzen des Vorgangs aufgefordert werden.|  
|[CComControl::MessageBox](#messagebox)|Rufen Sie diese Methode zum Erstellen, anzeigen und ein Meldungsfeld arbeiten.|  
  
## <a name="remarks"></a>Hinweise  
 `CComControl`ist eine Reihe von nützlichen Steuerelemente Hilfsfunktionen und wichtige Datenelemente für ATL-Steuerelementen. Wenn Sie ein standard-Steuerelement oder ein DHTML-Steuerelement mit der ATL-Steuerelement-Assistenten erstellen, leiten der Assistent automatisch eine Klasse von `CComControl`. `CComControl`leitet die meisten Methoden aus [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Weitere Informationen zum Erstellen eines Steuerelements finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md). Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
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
 Ruft die [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) -Konstruktors und übergibt die `m_hWnd` Datenmember über vererbt [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>CComControl::ControlQueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 `ppv`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`, oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Nur behandelt Schnittstellen in der COM-Zuordnungstabelle.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>CComControl::CreateControlWindow  
 Standardmäßig erstellt ein Fenster für das Steuerelement durch Aufrufen von `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Handle für das Fenster übergeordnete oder Besitzer. Ein gültiges Fensterhandle muss angegeben werden. Das Fenster des Steuerelements wird in den Bereich des übergeordneten Fensters beschränkt.  
  
 `rcPos`  
 [in] Die Anfangsgröße und die Position des Fensters erstellt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie etwas tun möchten anders als ein einziges Fenster zu erstellen, z. B. um zwei Fenster zu erstellen, von denen eine Symbolleiste für das Steuerelement wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>CComControl::FireOnChanged  
 Benachrichtigt den Container-Ereignissenke, die eine Steuerelementeigenschaft geändert wurde.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *dispID*  
 [in] Der Bezeichner der Eigenschaft, die geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Steuerelementklasse abgeleitet [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), diese Methode ruft [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) alle benachrichtigen verbunden `IPropertyNotifySink` Schnittstellen, die das angegebene Steuerelement -Eigenschaft geändert hat. Wenn die Steuerelementklasse nicht von abgeleitet ist `IPropertyNotifySink`, gibt diese Methode `S_OK`. 
  
 Diese Methode ist sicherer, anzurufen, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit  
 Benachrichtigt Senke für den Container, eine Steuerelementeigenschaft geändert wird, sodass das Objekt der Senke zum Fortsetzen des Vorgangs aufgefordert werden.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *dispID*  
 [in] Der Bezeichner für die Eigenschaft zu ändern.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Steuerelementklasse abgeleitet [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), diese Methode ruft [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) alle benachrichtigen verbunden `IPropertyNotifySink` Schnittstellen, die den angegebenen Steuerelementeigenschaft wird geändert. Wenn die Steuerelementklasse nicht von abgeleitet ist `IPropertyNotifySink`, gibt diese Methode `S_OK`.  

  
 Diese Methode ist sicherer, anzurufen, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>CComControl::MessageBox  
 Rufen Sie diese Methode zum Erstellen, anzeigen und ein Meldungsfeld arbeiten.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Der im Meldungsfenster anzuzeigende Text.  
  
 `lpszCaption`  
 Der Titel des Dateidialogfelds. Wenn NULL (Standardeinstellung), den Titel "Error" verwendet wird.  
  
 `nType`  
 Gibt den Inhalt und Verhalten des Dialogfelds. Finden Sie unter der [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Eintrag in das Windows SDK-Dokumentation für eine Liste der verschiedenen Meldungsfelder. Die Standardeinstellung bietet eine einfache **OK** Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen ganzzahligen Wert angeben, einen der aufgeführten Menüelement Werte [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) in das Windows SDK-Dokumentation.  
  
### <a name="remarks"></a>Hinweise  
 `MessageBox`eignet sich sowohl während der Entwicklung als auch eine einfache Möglichkeit, eine Warnung oder Fehlermeldung für den Benutzer anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [-Klasse](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl-Klasse](../../atl/reference/ccomcompositecontrol-class.md)
