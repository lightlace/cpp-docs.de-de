---
title: CFontHolder-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: e6991d7ca545eef671720a38907088dc6a534d1a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216807"
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
|[CFontHolder::GetDisplayString](#getdisplaystring)|Ruft die Zeichenfolge, die im Eigenschaftenbrowser des Containers angezeigt.|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Gibt der Schriftart `IDispatch` Schnittstelle.|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Gibt ein Handle für eine Windows-Schriftart.|  
|[CFontHolder::InitializeFont](#initializefont)|Initialisiert eine `CFontHolder` Objekt.|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Ruft Informationen für die zugehörigen Schriftart ab.|  
|[CFontHolder::ReleaseFont](#releasefont)|Trennt die Verbindung der `CFontHolder` -Objekt aus der `IFont` und `IFontNotification` Schnittstellen.|  
|[CFontHolder::Select](#select)|Wählt eine Schriftartressource für einen Gerätekontext.|  
|[CFontHolder::SetFont](#setfont)|Verbindet die `CFontHolder` -Objekt an eine `IFont` Schnittstelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|Ein Zeiger auf die `CFontHolder` des Objekts `IFont` Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 `CFontHolder` eine Basisklasse keinen.  
  
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
 *strValue gespeichert*  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die Anzeigezeichenfolge enthalten ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Zeichenfolge erfolgreich abgerufen wird; andernfalls 0.  
  
##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch  
 Rufen Sie diese Funktion, um einen Zeiger auf die Dispatchschnittstelle der Schriftart abzurufen.  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CFontHolder` des Objekts `IFontDisp` Schnittstelle. Beachten Sie, dass die Funktion aufruft, `GetFontDispatch` müssen Aufrufen `IUnknown::Release` auf diesen Schnittstellenzeiger, wenn es nicht mehr benötigen.  
  
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
 *cyLogical*  
 Höhe in logischen Einheiten, der das Rechteck, in dem das Steuerelement gezeichnet wird.  
  
 *cyHimetric*  
 Höhe in MM_HIMETRIC Einheiten des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf das Objekt für die Schriftart andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Das Verhältnis von *CyLogical* und *CyHimetric* wird verwendet, um die ordnungsgemäße Anzeigegröße in logischen Einheiten, die Schriftart, Schriftgrad, MM_HIMETRIC Einheiten ausgedrückt berechnen:  
  
 Anzeigegröße = ( *CyLogical* / *CyHimetric*) X Schriftgrad  
  
 Die Version ohne Parameter gibt ein Handle für eine Schriftart für den Bildschirm ordnungsgemäß dimensioniert.  
  
##  <a name="initializefont"></a>  CFontHolder::InitializeFont  
 Initialisiert eine `CFontHolder` Objekt.  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pFontDesc*  
 Zeiger auf eine Schriftart Beschreibung ( [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc)), der Schriftmerkmale angibt.  
  
 *pFontDispAmbient*  
 Zeiger auf den Container ambient-Schriftart-Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *pFontDispAmbient* ist nicht NULL ist, die `CFontHolder` -Objekt verbunden ist, auf einen Klon der der `IFont` Schnittstelle, die durch den Container ambient-Schriftart-Eigenschaft verwendet.  
  
 Wenn *pFontDispAmbient* ist NULL, eine neue Schriftart-Objekt erstellt wird, entweder über die Schriftart Beschreibung verweist *pFontDesc* oder, wenn Sie *pFontDesc* NULL ist, eine Standardeinstellung aus die Beschreibung.  
  
 Mit dieser Funktion wird nach dem Erstellen einer `CFontHolder` Objekt.  
  
##  <a name="m_pfont"></a>  CFontHolder::m_pFont  
 Ein Zeiger auf die `CFontHolder` des Objekts `IFont` Schnittstelle.  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics  
 Ruft Informationen auf der physischen Schriftart dargestellt durch die `CFontHolder` Objekt.  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>Parameter  
 *lptm*  
 Ein Zeiger auf eine [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) -Struktur, die die Informationen zu erhalten.  
  
##  <a name="releasefont"></a>  CFontHolder::ReleaseFont  
 Diese Funktion trennt die `CFontHolder` -Objekt aus seiner `IFont` Schnittstelle.  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>  CFontHolder::Select  
 Rufen Sie diese Funktion, um die Schriftart des Steuerelements im angegebenen Gerätekontext wählen.  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Gerätekontext, die in die Schriftart ausgewählt ist.  
  
 *cyLogical*  
 Höhe in logischen Einheiten, der das Rechteck, in dem das Steuerelement gezeichnet wird.  
  
 *cyHimetric*  
 Höhe in MM_HIMETRIC Einheiten des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schriftart, die ersetzt wird.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [GetFontHandle](#getfonthandle) eine Erläuterung der *CyLogical* und *CyHimetric* Parameter.  
  
##  <a name="setfont"></a>  CFontHolder::SetFont  
 Alle vorhandenen Schriftarten frei und verbindet die `CFontHolder` -Objekt an ein `IFont` Schnittstelle.  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewFont*  
 Zeiger auf den neuen `IFont` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropExchange-Klasse](../../mfc/reference/cpropexchange-class.md)
