---
title: CPictureHolder Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Picture
- CPictureHolder
dev_langs:
- C++
helpviewer_keywords:
- Picture property
- controls [MFC], OLE
- OLE controls, image
- CPictureHolder class
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
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
ms.openlocfilehash: 14a774e3edc8b5e160b287612d3709c3424503be
ms.lasthandoff: 02/24/2017

---
# <a name="cpictureholder-class"></a>CPictureHolder-Klasse
Implementiert eine Picture-Eigenschaft, die dem Benutzer ermöglicht, ein Bild in Ihrem Steuerelement anzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPictureHolder  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPictureHolder::CPictureHolder](#cpictureholder)|Erstellt ein `CPictureHolder`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPictureHolder::CreateEmpty](#createempty)|Erstellt ein leeres `CPictureHolder`-Objekt.|  
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Erstellt ein `CPictureHolder` Objekt aus einer Bitmap.|  
|[CPictureHolder::CreateFromIcon](#createfromicon)|Erstellt ein `CPictureHolder` Objekt über ein Symbol.|  
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Erstellt ein `CPictureHolder` Objekt aus einer Metadatei.|  
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Ruft die Zeichenfolge in eine Steuerelementcontainer-Eigenschaftenbrowser angezeigt.|  
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Gibt die `CPictureHolder` des Objekts `IDispatch` Schnittstelle.|  
|[CPictureHolder::GetType](#gettype)|Informiert, ob die `CPictureHolder` -Objekt ist eine Bitmap, eine Metadatei oder ein Symbol.|  
|[CPictureHolder:: Render](#render)|Rendert das Bild an.|  
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Legt die `CPictureHolder` des Objekts `IDispatch` Schnittstelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPictureHolder::m_pPict](#m_ppict)|Ein Zeiger auf ein Bildobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CPictureHolder`eine Basisklasse keinen.  
  
 Mit den vordefinierten Picture-Eigenschaft kann der Entwickler eine Bitmap, Symbol oder Metadatei für die Anzeige angeben.  
  
 Informationen zum Erstellen von benutzerdefinierten Eigenschaften finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Verwenden von Bildern in einem ActiveX-Steuerelement](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CPictureHolder`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="a-namecpictureholdera--cpictureholdercpictureholder"></a><a name="cpictureholder"></a>CPictureHolder::CPictureHolder  
 Erstellt ein `CPictureHolder`-Objekt.  
  
```  
CPictureHolder();
```  
  
##  <a name="a-namecreateemptya--cpictureholdercreateempty"></a><a name="createempty"></a>CPictureHolder::CreateEmpty  
 Erstellt ein leeres `CPictureHolder` -Objekt und verbindet ihn auf eine `IPicture` Schnittstelle.  
  
```  
BOOL CreateEmpty();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
##  <a name="a-namecreatefrombitmapa--cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a>CPictureHolder::CreateFromBitmap  
 Verwendet ein Bitmuster zur Initialisierung des Bildobjekts in einem `CPictureHolder`.  
  
```  
BOOL CreateFromBitmap(
    UINT idResource);

 
BOOL CreateFromBitmap(
    CBitmap* pBitmap,  
    CPalette* pPal = NULL,  
    BOOL bTransferOwnership = TRUE);

 
BOOL CreateFromBitmap(
    HBITMAP hbm,  
    HPALETTE hpal = NULL,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `idResource`  
 Ressourcen-ID einer Bitmap-Ressource.  
  
 `pBitmap`  
 Zeiger auf eine [CBitmap](../../mfc/reference/cbitmap-class.md) Objekt.  
  
 *pPal*  
 Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md) Objekt.  
  
 `bTransferOwnership`  
 Gibt an, ob das Bildobjekt der Besitz der Objekte Bitmap und Palette dauert.  
  
 `hbm`  
 Handle für die Bitmap, von dem aus der `CPictureHolder` Objekt wird erstellt.  
  
 `hpal`  
 Handle für die Palette, die zum Rendern der Bitmap.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTransferOwnership` ist **TRUE**, der Aufrufer sollte die Bitmap nicht verwenden oder Palettenobjekt in keiner Weise nach diesem Aufruf zurückgibt. Wenn `bTransferOwnership` ist **FALSE**, der Aufrufer ist dafür verantwortlich, dass die Bitmap und Palette Objekte für die Lebensdauer des Objekts Grafik gültig bleiben.  
  
##  <a name="a-namecreatefromicona--cpictureholdercreatefromicon"></a><a name="createfromicon"></a>CPictureHolder::CreateFromIcon  
 Verwendet ein Symbol zum Initialisieren des Picture-Objekts in einem `CPictureHolder`.  
  
```  
BOOL CreateFromIcon(
    UINT idResource);

 
BOOL CreateFromIcon(
    HICON hIcon,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `idResource`  
 Ressourcen-ID einer Bitmap-Ressource.  
  
 `hIcon`  
 Handle des Symbols an, von dem aus der `CPictureHolder` Objekt wird erstellt.  
  
 `bTransferOwnership`  
 Gibt an, ob das Bildobjekt Besitzer des Objekts Symbol gelangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTransferOwnership` ist **TRUE**, der Aufrufer sollte das Symbol-Objekt nicht in keiner Weise verwendet werden, nach diesem Aufruf zurückgegeben wird. Wenn `bTransferOwnership` ist **FALSE**, der Aufrufer ist dafür verantwortlich, dass das Symbol-Objekt für die Lebensdauer des Objekts Grafik gültig bleibt.  
  
##  <a name="a-namecreatefrommetafilea--cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a>CPictureHolder::CreateFromMetafile  
 Verwendet eine Metadatei zum Initialisieren des Picture-Objekts in einem `CPictureHolder`.  
  
```  
BOOL CreateFromMetafile(
    HMETAFILE hmf,  
    int xExt,  
    int yExt,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `hmf`  
 Handle für die Metadatei, die zum Erstellen der `CPictureHolder` Objekt.  
  
 *xExt*  
 X-Block des Bildes.  
  
 *yExt*  
 Y-Erweiterung des Bildes.  
  
 `bTransferOwnership`  
 Gibt an, ob das Bildobjekt Besitzer des Objekts Metadatei dauert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTransferOwnership` ist **TRUE**, der Aufrufer sollte nicht verwenden die Metadatei Objekt in keiner Weise nach diesem Aufruf zurückgegeben wird. Wenn `bTransferOwnership` ist **FALSE**, der Aufrufer ist dafür verantwortlich, dass die Metadatei-Objekt für die Lebensdauer des Objekts Grafik gültig bleibt.  
  
##  <a name="a-namegetdisplaystringa--cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a>CPictureHolder::GetDisplayString  
 Ruft die Zeichenfolge, die in einen Container Eigenschaftenbrowser angezeigt wird.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Parameter  
 `strValue`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die auf die Zeichenfolge enthalten ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Zeichenfolge erfolgreich abgerufen wird; andernfalls 0.  
  
##  <a name="a-namegetpicturedispatcha--cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a>CPictureHolder::GetPictureDispatch  
 Diese Funktion gibt einen Zeiger auf die `CPictureHolder` des Objekts `IPictureDisp` Schnittstelle.  
  
```  
LPPICTUREDISP GetPictureDispatch();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CPictureHolder` des Objekts `IPictureDisp` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Der Aufrufer muss Aufrufen **Version** für diesen Zeiger, wenn er nicht mehr benötigen.  
  
##  <a name="a-namegettypea--cpictureholdergettype"></a><a name="gettype"></a>CPictureHolder::GetType  
 Gibt an, ob das Bild eine Bitmap, eine Metadatei oder ein Symbol ist.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der das Bild angibt. Nachfolgend sind die möglichen Werte und ihre Bedeutung:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**PICTYPE_UNINITIALIZED**|`CPictureHolder`Objekt ist unititialized.|  
|**PICTYPE_NONE**|`CPictureHolder`ist leer.|  
|**PICTYPE_BITMAP**|Bild ist eine Bitmap.|  
|**PICTYPE_METAFILE**|Bild ist eine Metadatei.|  
|**PICTYPE_ICON**|Bild ist ein Symbol.|  
  
##  <a name="a-namemppicta--cpictureholdermppict"></a><a name="m_ppict"></a>CPictureHolder::m_pPict  
 Ein Zeiger auf die `CPictureHolder` des Objekts `IPicture` Schnittstelle.  
  
```  
LPPICTURE m_pPict;  
```  
  
##  <a name="a-namerendera--cpictureholderrender"></a><a name="render"></a>CPictureHolder:: Render  
 Rendert das Bild in das Rechteck auf die `rcRender`.  
  
```  
void Render(
    CDC* pDC,  
    const CRect& rcRender,  
    const CRect& rcWBounds);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf die Anzeigekontext, in dem das Bild gerendert werden.  
  
 `rcRender`  
 Rechteck, in dem das Bild gerendert werden.  
  
 *rcWBounds*  
 Ein Rechteck, das das umschließende Rechteck des Objekts rendern das Bild darstellt. Für ein Steuerelement dieses Rechteck ist die `rcBounds` übergebene Parameter eine Überschreibung der [COleControl:: OnDraw aufgerufen](../../mfc/reference/colecontrol-class.md#ondraw).  
  
##  <a name="a-namesetpicturedispatcha--cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a>CPictureHolder::SetPictureDispatch  
 Verbindet die `CPictureHolder` -Objekt an eine `IPictureDisp` Schnittstelle.  
  
```  
void SetPictureDispatch(LPPICTUREDISP pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 Zeiger auf die neue `IPictureDisp` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFontHolder-Klasse](../../mfc/reference/cfontholder-class.md)

