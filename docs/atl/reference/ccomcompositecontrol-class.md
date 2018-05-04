---
title: CComCompositeControl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 592eb6c897f47bede5aa0a09149aaf791e8cfbce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl-Klasse
Diese Klasse stellt die Methoden zur Implementierung eines zusammengesetzten Steuerelements erforderlich sind.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut ebenso andere Schnittstellen für das zusammengesetzte Steuerelement unterstützt werden soll.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Der Konstruktor.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[:: AdviseSinkMap](#advisesinkmap)|Rufen Sie diese Methode senkereigniszuordnung oder alle Steuerelemente, die von zusammengesetzten Steuerelementen gehostet wird.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Rufen Sie diese Methode zum Berechnen der Größe in **HIMETRIC** Einheiten des Dialog-Ressource, die zum Hosten von zusammengesetzten Steuerelementen verwendet.|  
|[CComCompositeControl::Create](#create)|Diese Methode wird aufgerufen, um das Fenster des Steuerelements für die zusammengesetztes Steuerelement zu erstellen.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Rufen Sie diese Methode, um das Fenster des Steuerelements zu erstellen und empfehlen jedes gehosteten Steuerelement.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Rufen Sie diese Methode, um die Farbe des Hintergrunds des zusammengesetzten Steuerelements mit Background-Farbe für den Container festlegen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Der Hintergrundpinsel.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Das Handle des Fensters, das gerade den Fokus besitzt.|  
  
## <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen von Klasse `CComCompositeControl` erben die Funktionalität eines zusammengesetzten ActiveX-Steuerelements. ActiveX-Steuerelemente abgeleitet `CComCompositeControl` von ein Standarddialogfeld gehostet werden. Diese Steuerelemente werden zusammengesetzte Steuerelemente bezeichnet, da sie andere Steuerelemente (systemeigene Windows-Steuerelemente und ActiveX-Steuerelemente) hosten können.  
  
 `CComCompositeControl` identifiziert die Dialogressource beim Erstellen der zusammengesetzten Steuerelements anhand der für einen enumerierten Datenmember in der untergeordneten Klasse an. Der Member dieser Klasse für die untergeordnete LEISTE wird auf die Ressourcen-ID der Dialogfeldressource festgelegt, die als das Fenster des Steuerelements verwendet werden. Im folgenden ist ein Beispiel für den Datenmember, die abgeleitete Klasse von `CComCompositeControl` zum Identifizieren der Dialogfeldressource für das Fenster des Steuerelements verwendet werden dürfen:  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Zusammengesetzte Steuerelemente werden immer im Fenstermodus, obwohl sie Fensterlose Steuerelemente enthalten können.  
  
 Ein Steuerelement implementiert, indem eine `CComCompositeControl`-abgeleitete Klasse verfügt über Standardverhalten integriert. Wenn das Steuerelement den Fokus erhält, durch wird im Registerkartenformat in einer Anwendung enthalten, nach und nach Drücken der TAB-Taste führt dazu, dass den Fokus zum Durchlaufen der zusammengesetztes Steuerelement enthaltenen Steuerelemente, und klicken Sie dann aus der zusammengesetzten Steuerelements und an das nächste Element im werden die die Aktivierreihenfolge des Containers. Die Aktivierreihenfolge des gehosteten Steuerelemente richtet sich nach der Dialogfeldressource und bestimmt die Reihenfolge, in welcher Tabulator-erfolgt.  
  
> [!NOTE]
>  In der Reihenfolge für Zugriffstasten ordnungsgemäß funktioniert mit einer `CComCompositeControl`, es ist notwendig, laden eine Zugriffstastentabelle, wie das Steuerelement erstellt wird, übergeben Sie das Handle und die Anzahl der Zugriffstasten wieder [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), und Zerstören Sie schließlich in der Tabelle, wenn das Steuerelement freigegeben wird.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="advisesinkmap"></a>  :: AdviseSinkMap  
 Rufen Sie diese Methode senkereigniszuordnung oder alle Steuerelemente, die von zusammengesetzten Steuerelementen gehostet wird.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 "True", wenn alle Steuerelemente sind, darüber informiert zu werden. andernfalls "false".  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`  
 Alle Steuerelemente im Ereignisprotokoll Senke Zuordnung verbunden oder von deren Ereignisquelle wurde erfolgreich getrennt wurden.  
  
 **E_FAIL**  
 Nicht alle Steuerelemente im Ereignisprotokoll Senke Karte verbunden oder getrennt von der Quelle des Ereignisses erfolgreich werden konnte.  
  
 `E_POINTER`  
 Dieser Fehler gibt normalerweise an ein Problem mit einem Eintrag in das Steuerelement Senke ereigniszuordnung oder ein Problem mit der ein Vorlagenargument in verwendet ein `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse.  
  
 **CONNECT_E_ADVISELIMIT**  
 Der Verbindungspunkt hat bereits die maximale Anzahl von Verbindungen erreicht und nicht mehr annehmen.  
  
 **CONNECT_E_CANNOTCONNECT**  
 Die Senke unterstützt nicht die Schnittstelle, die von diesem Verbindungspunkt erforderlich.  
  
 **CONNECT_E_NOCONNECTION**  
 Der Cookiewert stellt keine gültige Verbindung dar. Dieser Fehler gibt normalerweise an ein Problem mit einem Eintrag in das Steuerelement Senke ereigniszuordnung oder ein Problem mit der ein Vorlagenargument in verwendet ein `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Die grundlegende Implementierung dieser Methode durchsucht die Einträge in der ereignismeldung Sink-Zuordnung. Anschließend Member- oder unadvises die Verbindungspunkte an der COM-Objekte, die durch das Ereignis Sink-Zuordnung Senke Einträge beschrieben. Dieser Member-Methode stützt sich auch auf die Tatsache, dass die von einer Instanz die abgeleitete Klasse erbt `IDispEventImpl` für jedes Steuerelement in der Senke-Zuordnung, die empfohlen oder unadvised sein.  
  
##  <a name="calcextent"></a>  CComCompositeControl::CalcExtent  
 Rufen Sie diese Methode zum Berechnen der Größe in **HIMETRIC** Einheiten des Dialog-Ressource, die zum Hosten von zusammengesetzten Steuerelementen verwendet.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Ein Verweis auf eine **Größe** Struktur von dieser Methode gefüllt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Steuerelement durch ein Dialogfeld gehostet wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Die Größe wird zurückgegeben, der `size` Parameter.  
  
##  <a name="create"></a>  CComCompositeControl::Create  
 Diese Methode wird aufgerufen, um das Fenster des Steuerelements für die zusammengesetztes Steuerelement zu erstellen.  
  
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
 Daten, die während der steuerelementerstellung an das Steuerelement übergeben werden. Übergeben Sie die Daten als `dwInitParam` als angezeigt wird der **LPARAM** Parameter von der [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht, die an das zusammengesetztes Steuerelement gesendet wird, wenn es erstellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das neu erstellte zusammengesetztes Steuerelement-Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird in der Regel während der direkten Aktivierung des Steuerelements aufgerufen.  
  
##  <a name="ccomcompositecontrol"></a>  CComCompositeControl::CComCompositeControl  
 Der Konstruktor.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die [CComCompositeControl::m_hbrBackground](#m_hbrbackground) und [CComCompositeControl::m_hWndFocus](#m_hwndfocus) Datenmember auf NULL.  
  
##  <a name="dtor"></a>  CComCompositeControl:: ~ CComCompositeControl  
 Der Destruktor.  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht das Hintergrundobjekt im aus, falls vorhanden.  
  
##  <a name="createcontrolwindow"></a>  CComCompositeControl::CreateControlWindow  
 Rufen Sie diese Methode, um das Fenster des Steuerelements zu erstellen und alle gehosteten Steuerelemente empfehlen.  
  
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
 Gibt ein Handle auf das Dialogfeld für die neu erstellte zusammengesetzten Steuerelements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CComCompositeControl::Create](#create) und [:: AdviseSinkMap](#advisesinkmap).  
  
##  <a name="m_hbrbackground"></a>  CComCompositeControl::m_hbrBackground  
 Der Hintergrundpinsel.  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>  CComCompositeControl::m_hWndFocus  
 Das Handle des Fensters, das gerade den Fokus besitzt.  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>  CComCompositeControl::SetBackgroundColorFromAmbient  
 Rufen Sie diese Methode, um die Farbe des Hintergrunds des zusammengesetzten Steuerelements mit Background-Farbe für den Container festlegen.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
