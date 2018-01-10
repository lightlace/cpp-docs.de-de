---
title: CPictureHolder Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
dev_langs: C++
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90bc58ce3d56852b983a673968df97b55f4bdeab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cpictureholder-class"></a>CPictureHolder-Klasse
Implementiert eine Picture-Eigenschaft, die dem Benutzer ermöglicht, ein Bild im Steuerelement anzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPictureHolder  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPictureHolder::CPictureHolder](#cpictureholder)|Erstellt ein `CPictureHolder`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPictureHolder::CreateEmpty](#createempty)|Erstellt ein leeres `CPictureHolder`-Objekt.|  
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Erstellt eine `CPictureHolder` Objekt aus einer Bitmap.|  
|[CPictureHolder::CreateFromIcon](#createfromicon)|Erstellt eine `CPictureHolder` Objekt über ein Symbol.|  
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Erstellt eine `CPictureHolder` Objekt aus einer Metadatei.|  
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Ruft die Zeichenfolge in eine Steuerelementcontainer-Eigenschaftenbrowser angezeigt.|  
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Gibt die `CPictureHolder` des Objekts `IDispatch` Schnittstelle.|  
|[CPictureHolder::GetType](#gettype)|Informiert, ob die `CPictureHolder` Objekt ist eine Bitmap, ein Metadatei oder ein Symbol.|  
|[CPictureHolder](#render)|Rendert das Bild an.|  
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Legt die `CPictureHolder` des Objekts `IDispatch` Schnittstelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPictureHolder::m_pPict](#m_ppict)|Ein Zeiger auf ein Bildobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CPictureHolder`eine Basisklasse verfügt nicht über.  
  
 Mit den vordefinierten Picture-Eigenschaft kann der Entwickler eine Bitmap, Symbol oder Metadatei für die Anzeige angeben.  
  
 Informationen zum Erstellen von benutzerdefinierten Eigenschaften finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Verwenden von Bildern in einem ActiveX-Steuerelement](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CPictureHolder`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="cpictureholder"></a>CPictureHolder::CPictureHolder  
 Erstellt ein `CPictureHolder`-Objekt.  
  
```  
CPictureHolder();
```  
  
##  <a name="createempty"></a>CPictureHolder::CreateEmpty  
 Erstellt ein leeres `CPictureHolder` Objekt, und wird eine Verbindung zu einer `IPicture` Schnittstelle.  
  
```  
BOOL CreateEmpty();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
##  <a name="createfrombitmap"></a>CPictureHolder::CreateFromBitmap  
 Verwendet ein Bitmuster, zum Initialisieren des Bildobjekts in einem `CPictureHolder`.  
  
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
 Gibt an, ob das Bildobjekt der Besitz der Objekte mithilfe einer Bitmap und Palette ausgeführt wird.  
  
 `hbm`  
 Handle für die Bitmap, von dem aus die `CPictureHolder` Objekt erstellt wird.  
  
 `hpal`  
 Handle für die Palette für das Rendern der Bitmap verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTransferOwnership` ist **"true"**, der Aufrufer sollten nicht verwenden, die Bitmap oder Palettenobjekt in keiner Weise nach diesem Aufruf zurückgibt. Wenn `bTransferOwnership` ist **"false"**, der Aufrufer ist dafür verantwortlich, dass die Bitmap und Palette Objekte für die Lebensdauer des Objekts Grafik gültig bleiben.  
  
##  <a name="createfromicon"></a>CPictureHolder::CreateFromIcon  
 Verwendet ein Symbol, das zum Initialisieren des Bildobjekts in einem `CPictureHolder`.  
  
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
 Handle des Symbols an, von dem aus die `CPictureHolder` Objekt erstellt wird.  
  
 `bTransferOwnership`  
 Gibt an, ob das Bildobjekt Besitzer des Objekts Symbol ausgeführt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTransferOwnership` ist **"true"**, der Aufrufer sollte das Symbol "-Objekt nicht in keiner Weise verwendet werden, nach der Rückkehr dieses Aufrufs. Wenn `bTransferOwnership` ist **"false"**, der Aufrufer ist dafür verantwortlich, dass das Symbol "-Objekt für die Lebensdauer des Objekts Grafik gültig bleibt.  
  
##  <a name="createfrommetafile"></a>CPictureHolder::CreateFromMetafile  
 Verwendet eine Metadatei zum Initialisieren des Bildobjekts in einem `CPictureHolder`.  
  
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
 X Ausmaß des Bilds.  
  
 *yExt*  
 Y-Block des Bilds.  
  
 `bTransferOwnership`  
 Gibt an, ob das Bildobjekt Besitzer des Objekts Metadatei ausgeführt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bTransferOwnership` ist **"true"**, der Aufrufer sollten nicht das Metadatei-Objekt in keiner Weise nach dem Verwenden dieser Aufruf gibt. Wenn `bTransferOwnership` ist **"false"**, der Aufrufer ist dafür verantwortlich, dass das Metadatei-Objekt für die Lebensdauer des Objekts Grafik gültig bleibt.  
  
##  <a name="getdisplaystring"></a>CPictureHolder::GetDisplayString  
 Ruft die Zeichenfolge, die in einem Container Eigenschaftenbrowser angezeigt wird.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Parameter  
 `strValue`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) , halten Sie die Anzeigezeichenfolge liegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Zeichenfolge erfolgreich abgerufen wird; andernfalls 0.  
  
##  <a name="getpicturedispatch"></a>CPictureHolder::GetPictureDispatch  
 Diese Funktion gibt einen Zeiger auf die `CPictureHolder` des Objekts `IPictureDisp` Schnittstelle.  
  
```  
LPPICTUREDISP GetPictureDispatch();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CPictureHolder` des Objekts `IPictureDisp` Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Der Aufrufer muss Aufrufen **Version** für diesen Zeiger, wenn er nicht mehr benötigt.  
  
##  <a name="gettype"></a>CPictureHolder::GetType  
 Gibt an, ob das Bild eine Bitmap, Metadatei oder das Symbol ".  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, der des Typs des Bilds. Mögliche Werte und ihre Bedeutungen lauten:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**PICTYPE_UNINITIALIZED**|`CPictureHolder`Objekt ist unititialized.|  
|**PICTYPE_NONE**|`CPictureHolder`Objekt ist leer.|  
|**PICTYPE_BITMAP**|Bild ist eine Bitmap.|  
|**PICTYPE_METAFILE**|Bild ist eine Metadatei.|  
|**PICTYPE_ICON**|Bild ist ein Symbol an.|  
  
##  <a name="m_ppict"></a>CPictureHolder::m_pPict  
 Ein Zeiger auf die `CPictureHolder` des Objekts `IPicture` Schnittstelle.  
  
```  
LPPICTURE m_pPict;  
```  
  
##  <a name="render"></a>CPictureHolder  
 Rendert das Bild in das Rechteck verweist `rcRender`.  
  
```  
void Render(
    CDC* pDC,  
    const CRect& rcRender,  
    const CRect& rcWBounds);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Zeiger auf dem Anzeigekontext, in dem das Bild gerendert werden.  
  
 `rcRender`  
 Rechteck, in dem das Bild gerendert werden.  
  
 *rcWBounds*  
 Ein Rechteck, das das umschließende Rechteck des Objekts, rendern das Bild darstellt. Für ein Steuerelement dieses Rechteck ist der `rcBounds` Parameter zu übergeben, um eine Überschreibung der [COleControl:: OnDraw aufgerufen](../../mfc/reference/colecontrol-class.md#ondraw).  
  
##  <a name="setpicturedispatch"></a>CPictureHolder::SetPictureDispatch  
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
