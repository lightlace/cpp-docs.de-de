---
title: CComCompositeControl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
dev_langs:
- C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
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
ms.openlocfilehash: ab99b8682e8b529cc124fbda1e6facaac48d0927
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl-Klasse
Diese Klasse stellt die erforderlichen Methoden zur Implementierung eines zusammengesetzten Steuerelements.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das zusammengesetzte Steuerelement unterstützt werden soll.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Der Konstruktor.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[:: AdviseSinkMap](#advisesinkmap)|Rufen Sie diese Methode, um senkereigniszuordnung oder alle Steuerelemente, die durch das zusammengesetzte Steuerelement gehostet.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Rufen Sie diese Methode zum Berechnen der in **HIMETRIC** Einheiten der Ressource, die das zusammengesetzte Steuerelement zu hosten.|  
|[CComCompositeControl::Create](#create)|Diese Methode wird aufgerufen, um das Steuerelementfenster für das zusammengesetzte Steuerelement zu erstellen.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Rufen Sie diese Methode, um das Steuerelementfenster erstellen und informiert alle gehosteten Steuerelement.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Rufen Sie diese Methode, um die Hintergrundfarbe des zusammengesetzten Steuerelements mit der Container-Hintergrundfarbe festzulegen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Der Hintergrundpinsel.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Das Handle des Fensters, das gegenwärtig den Fokus besitzt.|  
  
## <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen von Klasse `CComCompositeControl` erben die Funktionalität eines zusammengesetzten Steuerelements. ActiveX-Steuerelemente, die von abgeleiteten `CComCompositeControl` von ein Standarddialogfeld gehostet werden. Diese Steuerelemente werden zusammengesetzte Steuerelemente bezeichnet, da sie andere Steuerelemente (systemeigene Windows-Steuerelemente und ActiveX-Steuerelemente) hosten können.  
  
 `CComCompositeControl`identifiziert die Ressource beim Erstellen des zusammengesetzten Steuerelements anhand der für einen enumerierten Datenmember in der untergeordneten Klasse verwendet. Das Element IDD dieser untergeordneten Klasse wird auf die Ressourcen-ID der Dialogfeldressource festgelegt, die als das Fenster des Steuerelements verwendet werden. Im folgenden ist ein Beispiel für das Datenelement, das von die Klasse abgeleitet `CComCompositeControl` sollte enthalten zum Identifizieren der Ressource für das Fenster des Steuerelements verwendet werden soll:  
  
 [!code-cpp[NVC_ATL_COM&#13;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Zusammengesetzte Steuerelemente werden immer im Fenstermodus, obwohl sie Fensterlose Steuerelemente enthalten können.  
  
 Ein Steuerelement implementiert, indem eine `CComCompositeControl`-abgeleitete Klasse verfügt über Standardverhalten integriert. Wenn das Steuerelement den Fokus erhält, indem wird im Registerformat in einer Anwendung enthält., verursacht der nacheinander durch Drücken der TAB-Taste den Fokus zum Durchlaufen aller das zusammengesetzte Steuerelement enthaltenen Steuerelemente, klicken Sie dann aus dem zusammengesetzten Steuerelement und dem nächsten Element in der Aktivierreihenfolge des Containers werden aus. Die Aktivierreihenfolge der Steuerelemente gehosteten richtet sich nach der Ressource und bestimmt die Reihenfolge, in welcher Tabulator-erfolgt.  
  
> [!NOTE]
>  In der Reihenfolge für Zugriffstasten ordnungsgemäß mit einer `CComCompositeControl`, es ist erforderlich, eine Zugriffstastentabelle zu laden, wie das Steuerelement erstellt wird, übergeben Sie das Handle und die Anzahl von Schnellinfos wieder [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), und schließlich in der Tabelle löschen, wenn das Steuerelement freigegeben wird.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&14;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="advisesinkmap"></a>:: AdviseSinkMap  
 Rufen Sie diese Methode, um senkereigniszuordnung oder alle Steuerelemente, die durch das zusammengesetzte Steuerelement gehostet.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 True, wenn alle Steuerelemente sind, darüber informiert zu werden. andernfalls False.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`  
 Alle Steuerelemente Sink-Zuordnung verbunden oder getrennt von der Quelle des Ereignisses erfolgreich waren.  
  
 **E_FAIL**  
 Nicht alle Steuerelemente Sink-Zuordnung verbunden oder getrennt von der Quelle des Ereignisses erfolgreich sein kann.  
  
 `E_POINTER`  
 Dieser Fehler gibt normalerweise an ein Problem mit einem Eintrag im Ereignis Sink-Zuordnung das Steuerelement oder ein Problem mit einem Vorlagenargument verwendet ein `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse.  
  
 **CONNECT_E_ADVISELIMIT**  
 Der Verbindungspunkt wurde bereits die maximale Anzahl von Verbindungen erreicht und kann nicht mehr akzeptiert.  
  
 **CONNECT_E_CANNOTCONNECT**  
 Die Senke unterstützt nicht die Schnittstelle, die von diesem Verbindungspunkt erforderlich.  
  
 **CONNECT_E_NOCONNECTION**  
 Der Wert des Cookies stellt keine gültige Verbindung dar. Dieser Fehler gibt normalerweise an ein Problem mit einem Eintrag im Ereignis Sink-Zuordnung das Steuerelement oder ein Problem mit einem Vorlagenargument verwendet ein `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Die basisimplementierung dieser Methode durchsucht die Einträge im Sink-Zuordnung. Anschließend Member- oder unadvises zeigt die Verbindung auf die COM-Objekte, die von dem Ereignis Sink-Zuordnung Senke Einträge beschrieben. Diese Membermethode verwendet auch die Tatsache, die eine Instanz die abgeleitete Klasse erbt `IDispEventImpl` für jedes Steuerelement in der Sink-Zuordnung, die empfohlen oder unadvised sein.  
  
##  <a name="calcextent"></a>CComCompositeControl::CalcExtent  
 Rufen Sie diese Methode zum Berechnen der in **HIMETRIC** Einheiten der Ressource, die das zusammengesetzte Steuerelement zu hosten.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Ein Verweis auf eine **Größe** Struktur mit dieser Methode gefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Steuerelement in einem Dialogfeld gehostet wird. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird zurückgegeben, der `size` Parameter.  
  
##  <a name="create"></a>CComCompositeControl::Create  
 Diese Methode wird aufgerufen, um das Steuerelementfenster für das zusammengesetzte Steuerelement zu erstellen.  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das übergeordnete Fenster des Steuerelements.  
  
 `rcPos`  
 Reserviert.  
  
 `dwInitParam`  
 Die Daten während der steuerelementerstellung das Steuerelement übergeben werden soll. Übergeben Sie die Daten als `dwInitParam` als angezeigt, der **LPARAM** Parameter von der [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) -Nachricht, die an das zusammengesetzte Steuerelement gesendet wird, wenn er erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das neu erstellte zusammengesetzte Steuerelement-Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird in der Regel während der direkten Aktivierung des Steuerelements aufgerufen.  
  
##  <a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl  
 Der Konstruktor.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die [CComCompositeControl::m_hbrBackground](#m_hbrbackground) und [CComCompositeControl::m_hWndFocus](#m_hwndfocus) -Datenmember auf NULL.  
  
##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl  
 Der Destruktor.  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht das Hintergrund-Objekt, falls vorhanden.  
  
##  <a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow  
 Rufen Sie diese Methode, um das Steuerelementfenster zu erstellen und alle gehosteten Steuerelemente empfehlen.  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das übergeordnete Fenster des Steuerelements.  
  
 `rcPos`  
 Das Positionsrechteck des zusammengesetzten Steuerelements im Client-Koordinaten relativ zum `hWndParent`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle auf das Dialogfeld neu erstellte zusammengesetzte Steuerelement zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CComCompositeControl::Create](#create) und [:: AdviseSinkMap](#advisesinkmap).  
  
##  <a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground  
 Der Hintergrundpinsel.  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus  
 Das Handle des Fensters, das gegenwärtig den Fokus besitzt.  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient  
 Rufen Sie diese Methode, um die Hintergrundfarbe des zusammengesetzten Steuerelements mit der Container-Hintergrundfarbe festzulegen.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

