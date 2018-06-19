---
title: CFontHolder Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
dev_langs:
- C++
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5cb28b738822b3e35aa840c731eb11bc2c2b83d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367515"
---
# <a name="cfontholder-class"></a>CFontHolder-Klasse
Implementiert die vordefinierte Schriftarteigenschaft und kapselt die Funktionalität eines Windows-Schriftartobjekts und der `IFont` -Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|Erstellt ein `CFontHolder`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|Ruft die Zeichenfolge in einen Container Eigenschaftenbrowser angezeigt.|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Gibt der Schriftart `IDispatch` Schnittstelle.|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Gibt ein Handle für eine Windows-Schriftart an.|  
|[CFontHolder::InitializeFont](#initializefont)|Initialisiert ein `CFontHolder` Objekt.|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Ruft Informationen für die zugehörige Schriftart ab.|  
|[CFontHolder::ReleaseFont](#releasefont)|Trennt die `CFontHolder` -Objekt aus der `IFont` und `IFontNotification` Schnittstellen.|  
|[CFontHolder::Select](#select)|Wählt eine Schriftartressource in einem Gerätekontext.|  
|[CFontHolder::SetFont](#setfont)|Verbindet die `CFontHolder` -Objekt an eine `IFont` Schnittstelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|Ein Zeiger auf die `CFontHolder` des Objekts `IFont` Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 `CFontHolder` eine Basisklasse verfügt nicht über.  
  
 Verwenden Sie diese Klasse, um benutzerdefinierte Schriftart-Eigenschaften für das Steuerelement zu implementieren. Informationen zum Erstellen von Eigenschaften finden Sie im Artikel [ActiveX-Steuerelemente: Verwenden von Schriftarten](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CFontHolder`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="cfontholder"></a>  CFontHolder::CFontHolder  
 Erstellt ein `CFontHolder`-Objekt.  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>Parameter  
 *pNotify*  
 Zeiger auf der Schriftart `IPropertyNotifySink` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `InitializeFont` das resultierende Objekt initialisiert werden, bevor Sie ihn verwenden.  
  
##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString  
 Ruft eine Zeichenfolge, die im Eigenschaftenbrowser des Containers angezeigt werden kann.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Parameter  
 `strValue`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) , halten Sie die Anzeigezeichenfolge liegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Zeichenfolge erfolgreich abgerufen wird; andernfalls 0.  
  
##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch  
 Rufen Sie diese Funktion, um einen Zeiger auf die Schriftart Dispatch-Schnittstelle abzurufen.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CFontHolder` des Objekts **IFontDisp** Schnittstelle. Beachten Sie, dass die Funktion aufruft `GetFontDispatch` müssen Aufrufen `IUnknown::Release` für diese Schnittstellenzeiger auf, wenn es nicht mehr benötigen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `InitializeFont` vor dem Aufruf `GetFontDispatch`.  
  
##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle  
 Rufen Sie diese Funktion, um ein Handle für einer Windows-Schriftart zu erhalten.  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Parameter  
 `cyLogical`  
 Höhe in logischen Einheiten, der das Rechteck, in dem das Steuerelement gezeichnet wird.  
  
 `cyHimetric`  
 Höhe im `MM_HIMETRIC` Einheiten des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die Schriftart-Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhältnis von `cyLogical` und `cyHimetric` dient zum Berechnen der Größe ordnungsgemäße Anzeige in logischen Einheiten für die Punktgröße der Schriftart in ausgedrückt `MM_HIMETRIC` Einheiten:  
  
 Anzeigegröße = ( `cyLogical`  /  `cyHimetric`) X Schriftgrad  
  
 Die Version ohne Parameter gibt ein Handle für eine Schriftart ordnungsgemäß dimensioniert wird, für den Bildschirm an.  
  
##  <a name="initializefont"></a>  CFontHolder::InitializeFont  
 Initialisiert ein `CFontHolder` Objekt.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pFontDesc`  
 Zeiger auf eine Schriftart Beschreibung-Struktur ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)), der Schriftmerkmale angibt.  
  
 `pFontDispAmbient`  
 Ein Zeiger auf den Container ambient-Font-Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pFontDispAmbient` ist nicht **NULL**, die `CFontHolder` -Objekt verbunden ist, um einen Klon der `IFont` Schnittstelle verwendet, die für den Container ambient-Font-Eigenschaft.  
  
 Wenn `pFontDispAmbient` ist **NULL**, ein neues Schriftartobjekt wird erstellt, entweder von der Schriftart Beschreibung verweist `pFontDesc` oder, wenn der `pFontDesc` ist **NULL**, aus einer standardbeschreibung.  
  
 Mit dieser Funktion wird nach dem Erstellen einer `CFontHolder` Objekt.  
  
##  <a name="m_pfont"></a>  CFontHolder::m_pFont  
 Ein Zeiger auf die `CFontHolder` des Objekts `IFont` Schnittstelle.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics  
 Ruft Informationen zu physischen Schriftart dargestellt durch die `CFontHolder` Objekt.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Parameter  
 `lptm`  
 Ein Zeiger auf eine [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) -Struktur, die die Informationen erhält.  
  
##  <a name="releasefont"></a>  CFontHolder::ReleaseFont  
 Diese Funktion trennt die `CFontHolder` -Objekt aus seiner `IFont` Schnittstelle.  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>  CFontHolder::Select  
 Mit dieser Funktion wird zum Auswählen des Steuerelements Schriftart in den angegebenen Gerätekontext.  
  
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
 Höhe in logischen Einheiten, der das Rechteck, in dem das Steuerelement gezeichnet wird.  
  
 `cyHimetric`  
 Höhe im `MM_HIMETRIC` Einheiten des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schriftart, die ersetzt wird.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [GetFontHandle](#getfonthandle) eine Erläuterung der `cyLogical` und `cyHimetric` Parameter.  
  
##  <a name="setfont"></a>  CFontHolder::SetFont  
 Alle vorhandenen Schriftarten freigegeben und eine Verbindung der `CFontHolder` -Objekt an eine `IFont` Schnittstelle.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewFont*  
 Zeiger auf die neue `IFont` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropExchange-Klasse](../../mfc/reference/cpropexchange-class.md)
