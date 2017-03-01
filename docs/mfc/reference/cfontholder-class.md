---
title: Klasse CFontHolder | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontHolder
dev_langs:
- C++
helpviewer_keywords:
- custom fonts
- CFontHolder class
- fonts, ActiveX controls
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fdfa16756ff218159087969f2a4967ed5e76a445
ms.lasthandoff: 02/24/2017

---
# <a name="cfontholder-class"></a>CFontHolder-Klasse
Implementiert die vordefinierte Schriftarteigenschaft und kapselt die Funktionalität eines Windows-Schriftartobjekts und der `IFont` -Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|Erstellt ein `CFontHolder`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|Ruft die Zeichenfolge in einen Container Eigenschaftenbrowser angezeigt.|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Gibt der Schriftart `IDispatch` Schnittstelle.|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Gibt ein Handle für eine Windows-Schriftart.|  
|[CFontHolder::InitializeFont](#initializefont)|Initialisiert ein `CFontHolder` Objekt.|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Ruft Informationen für die zugehörige Schriftart ab.|  
|[CFontHolder::ReleaseFont](#releasefont)|Trennt die `CFontHolder` -Objekt aus der `IFont` und `IFontNotification` Schnittstellen.|  
|[CFontHolder::Select](#select)|Wählt eine der Schriftartressource in einem Gerätekontext.|  
|[CFontHolder::SetFont](#setfont)|Verbindet die `CFontHolder` -Objekt an eine `IFont` Schnittstelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|Ein Zeiger auf die `CFontHolder` des Objekts `IFont` Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 `CFontHolder`eine Basisklasse keinen.  
  
 Verwenden Sie diese Klasse, um benutzerdefinierte Schriftart-Eigenschaften für das Steuerelement zu implementieren. Informationen zum Erstellen von Eigenschaften finden Sie im Artikel [ActiveX-Steuerelemente: Verwenden von Schriftarten](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CFontHolder`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="a-namecfontholdera--cfontholdercfontholder"></a><a name="cfontholder"></a>CFontHolder::CFontHolder  
 Erstellt ein `CFontHolder`-Objekt.  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>Parameter  
 *pNotify*  
 Zeiger auf der Schriftart `IPropertyNotifySink` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen `InitializeFont` das resultierende Objekt vor der Verwendung initialisiert werden.  
  
##  <a name="a-namegetdisplaystringa--cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a>CFontHolder::GetDisplayString  
 Ruft eine Zeichenfolge, die in einen Container Eigenschaftenbrowser angezeigt werden kann.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Parameter  
 `strValue`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die auf die Zeichenfolge enthalten ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Zeichenfolge erfolgreich abgerufen wird; andernfalls 0.  
  
##  <a name="a-namegetfontdispatcha--cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a>CFontHolder::GetFontDispatch  
 Rufen Sie diese Funktion, um einen Zeiger auf die Schriftart Dispatch-Schnittstelle abzurufen.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CFontHolder` des Objekts **IFontDisp** Schnittstelle. Beachten Sie, dass die Funktion aufruft `GetFontDispatch` müssen Aufrufen `IUnknown::Release` auf diesen Schnittstellenzeiger, wenn es nicht mehr.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `InitializeFont` vor dem Aufruf von `GetFontDispatch`.  
  
##  <a name="a-namegetfonthandlea--cfontholdergetfonthandle"></a><a name="getfonthandle"></a>CFontHolder::GetFontHandle  
 Rufen Sie diese Funktion, um ein Handle für einer Windows-Schriftart zu erhalten.  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Parameter  
 `cyLogical`  
 Höhe in logischen Einheiten des Rechtecks, in dem das Steuerelement gezeichnet wird.  
  
 `cyHimetric`  
 Höhe in `MM_HIMETRIC` Einheiten des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Font-Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhältnis der `cyLogical` und `cyHimetric` wird verwendet, um die richtige Größe, in logischen Einheiten berechnen für die Schriftgröße in ausgedrückt `MM_HIMETRIC` Einheiten:  
  
 Anzeigegröße = ( `cyLogical`  /  `cyHimetric`) X Schriftgrad  
  
 Die Version ohne Parameter gibt ein Handle für eine Schriftart für den Bildschirm ordnungsgemäß dimensioniert.  
  
##  <a name="a-nameinitializefonta--cfontholderinitializefont"></a><a name="initializefont"></a>CFontHolder::InitializeFont  
 Initialisiert ein `CFontHolder` Objekt.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pFontDesc`  
 Zeiger auf eine Beschreibung Schriftartstruktur ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)), der die Schriftart angibt.  
  
 `pFontDispAmbient`  
 Ein Zeiger auf den Container ambient-Font-Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pFontDispAmbient` ist nicht **NULL**, `CFontHolder` -Objekt verbunden ist, um einen Klon der `IFont` von des Containers ambient-Font-Eigenschaft verwendet wird.  
  
 Wenn `pFontDispAmbient` ist **NULL**, ein neues Font-Objekt wird erstellt, entweder von der Schriftart-Beschreibung, die auf den `pFontDesc` oder `pFontDesc` ist **NULL**, über eine standardmäßige Beschreibung.  
  
 Mit dieser Funktion wird nach dem Erstellen einer `CFontHolder` Objekt.  
  
##  <a name="a-namempfonta--cfontholdermpfont"></a><a name="m_pfont"></a>CFontHolder::m_pFont  
 Ein Zeiger auf die `CFontHolder` des Objekts `IFont` Schnittstelle.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="a-namequerytextmetricsa--cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics  
 Ruft Informationen zu der physischen Schriftart, dargestellt durch die `CFontHolder` Objekt.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Parameter  
 `lptm`  
 Ein Zeiger auf eine [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) -Struktur, die die Informationen zu erhalten.  
  
##  <a name="a-namereleasefonta--cfontholderreleasefont"></a><a name="releasefont"></a>CFontHolder::ReleaseFont  
 Diese Funktion trennt die `CFontHolder` -Objekt aus seiner `IFont` Schnittstelle.  
  
```  
void ReleaseFont();
```  
  
##  <a name="a-nameselecta--cfontholderselect"></a><a name="select"></a>CFontHolder::Select  
 Rufen Sie diese Funktion, um die Schriftart des Steuerelements in den angegebenen Gerätekontext auswählen.  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Gerätekontext, in dem die Schriftart ausgewählt ist.  
  
 `cyLogical`  
 Höhe in logischen Einheiten des Rechtecks, in dem das Steuerelement gezeichnet wird.  
  
 `cyHimetric`  
 Höhe in `MM_HIMETRIC` Einheiten des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schriftart, die ersetzt wird.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [GetFontHandle](#getfonthandle) eine Erläuterung der `cyLogical` und `cyHimetric` Parameter.  
  
##  <a name="a-namesetfonta--cfontholdersetfont"></a><a name="setfont"></a>CFontHolder::SetFont  
 Eine beliebige vorhandene Schriftart freigegeben und eine Verbindung der `CFontHolder` -Objekt an eine `IFont` Schnittstelle.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewFont*  
 Zeiger auf die neue `IFont` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropExchange-Klasse](../../mfc/reference/cpropexchange-class.md)

