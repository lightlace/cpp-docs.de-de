---
title: "Dialogdatenaustausch Funktionen für OLE-Steuerelemente | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad97690ca948525e9a0920d087e4dfd617a11b4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>Dialogdatenaustausch-Funktionen für OLE-Steuerelemente
Dieses Thema listet die DDX_OC-Funktionen, die zum Austausch von Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, Formularansicht oder steuerungsansichtsobjekts und einen Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
### <a name="ddxoc-functions"></a>DDX_OC-Funktionen  
  
|||  
|-|-|  
|[DDX_OCBool](#ddx_ocbool)|Verwaltet die Übertragung von **BOOL** Daten zwischen einer Eigenschaft eines OLE-Steuerelements und ein **BOOL** -Datenmember.|  
|[DDX_OCBoolRO](#ddx_ocboolro)|Verwaltet die Übertragung von **BOOL** Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements und ein **BOOL** -Datenmember.|  
|[DDX_OCColor](#ddx_occolor)|Verwaltet die Übertragung von **OLE_COLOR** Daten zwischen einer Eigenschaft eines OLE-Steuerelements und ein **OLE_COLOR** -Datenmember.|  
|[DDX_OCColorRO](#ddx_occolorro)|Verwaltet die Übertragung von **OLE_COLOR** Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements und ein **OLE_COLOR** -Datenmember.|  
|[DDX_OCFloat](#ddx_ocfloat)|Verwaltet die Übertragung von **"float"** (oder **doppelte**) Daten zwischen einer Eigenschaft eines OLE-Steuerelements und ein **"float"** (oder **doppelte**)-Datenmember.|  
|[DDX_OCFloatRO](#ddx_ocfloatro)|Verwaltet die Übertragung von **"float"** (oder **doppelte**) Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements und ein **"float"** (oder **doppelte**) Daten Member.|  
|[DDX_OCInt](#ddx_ocint)|Verwaltet die Übertragung von `int` (oder **lange**) Daten zwischen einer Eigenschaft eines OLE-Steuerelements und ein `int` (oder **lange**)-Datenmember.|  
|[DDX_OCIntRO](#ddx_ocintro)|Verwaltet die Übertragung von `int` (oder **lange**) Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements und ein `int` (oder **lange**)-Datenmember.|  
|[DDX_OCShort](#ddx_ocshort)|Verwaltet die Übertragung von **kurze** Daten zwischen einer Eigenschaft eines OLE-Steuerelements und ein **kurze** -Datenmember.|  
|[DDX_OCShortRO](#ddx_ocshortro)|Verwaltet die Übertragung von **kurze** Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements und ein **kurze** -Datenmember.|  
|[DDX_OCText](#ddx_octext)|Verwaltet die Übertragung von **CString** Daten zwischen einer Eigenschaft eines OLE-Steuerelements und ein **CString** -Datenmember.|  
|[DDX_OCTextRO](#ddx_octextro)|Verwaltet die Übertragung von **CString** Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements und ein **CString** -Datenmember.|  
  
##  <a name="ddx_ocbool"></a>DDX_OCBool  
 Die `DDX_OCBool` -Funktion verwaltet die Übertragung von **BOOL** Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **BOOL** Datenmember im Dialogfeld die Formularansicht, oder Anzeigen des Steuerelementobjekts.  
  
```   
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header:** afxdisp.h  
  
##  <a name="ddx_ocboolro"></a>DDX_OCBoolRO  
 Die `DDX_OCBoolRO` -Funktion verwaltet die Übertragung von **BOOL** Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **BOOL** Datenmember im Dialogfeld Formularansichts- oder steuerungsansichtsobjekts.  
  
```   
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_occolor"></a>DDX_OCColor  
 Die `DDX_OCColor` -Funktion verwaltet die Übertragung von **OLE_COLOR** Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **OLE_COLOR** Datenmember im Dialogfeld Formularansichts- oder steuerungsansichtsobjekts.  
  
```   
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_occolorro"></a>DDX_OCColorRO  
 Die `DDX_OCColorRO` -Funktion verwaltet die Übertragung von **OLE_COLOR** Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **OLE_COLOR** Datenmember der Das Dialogfeld, Formularansicht oder steuerungsansichtsobjekt.  
  
```   
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_ocfloat"></a>DDX_OCFloat  
 Die `DDX_OCFloat` -Funktion verwaltet die Übertragung von **"float"** (oder **doppelte**) Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **"float"** (oder **doppelte**)-Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
```   
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_ocfloatro"></a>DDX_OCFloatRO  
 Die `DDX_OCFloatRO` -Funktion verwaltet die Übertragung von **"float"** (oder **doppelte**) Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem  **"float"** (oder **doppelte**)-Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
```   
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_ocint"></a>DDX_OCInt  
 Die `DDX_OCInt` -Funktion verwaltet die Übertragung von `int` (oder **lange**) Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` (oder **lang**)-Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
```   
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_ocintro"></a>DDX_OCIntRO  
 Die `DDX_OCIntRO` -Funktion verwaltet die Übertragung von `int` (oder **lange**) Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` (oder **lang** )-Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
```   
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_ocshort"></a>DDX_OCShort  
 Die `DDX_OCShort` -Funktion verwaltet die Übertragung von kurzen Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld Formularansicht oder steuerungsansichtsobjekts und einen kurzen Datenmember im Dialogfeld Formularansicht oder Ansichtsobjekt steuern.  
  
```   
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_ocshortro"></a>DDX_OCShortRO  
 Die `DDX_OCShortRO` -Funktion verwaltet die Übertragung von kurzen Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements in einem Dialogfeld Formularansicht oder steuerungsansichtsobjekts und einen kurzen Datenmember im Dialogfeld Formularansicht oder Ansichtsobjekt steuern.  
  
```   
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_octext"></a>DDX_OCText  
 Die **DDX_OCText** -Funktion verwaltet die Übertragung von **CString** Daten zwischen einer Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **CString** Daten Member des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
```   
void AFXAPI DDX_OCText(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine **CDataExchange** Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="ddx_octextro"></a>DDX_OCTextRO  
 Die `DDX_OCTextRO` -Funktion verwaltet die Übertragung von `CString` -Daten zwischen einer schreibgeschützten Eigenschaft eines OLE-Steuerelements in einem Dialogfeld, einem Formularansichts- oder Steuerungsansichtsobjekts und einem `CString` -Datenelement des Dialogfelds, des Formularansichts- oder Steuerungsansichtsobjekts.  
  
```  
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines OLE-Steuerelements im Dialogfeld, im Formularansichts- oder Steuerungsansichtsobjekt.  
  
 `dispid`  
 Die Verteiler-ID einer Eigenschaft des Steuerelements.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
