---
title: Standardroutinen zur Validierung Dialogfelddaten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33566bcdfab1a618dc8ff79deb375b3f9d1221f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="standard-dialog-data-validation-routines"></a>Standardroutinen zur Validierung der Dialogfelddaten
Dieses Thema enthält die Standarddialog (DDV) datenvalidierungsroutine für allgemeine MFC-Dialogfeld-Steuerelemente verwendet werden.  
  
> [!NOTE]
>  Der standard dialogdatenaustauschroutinen werden in die Header-Datei afxdd_.h definiert. Allerdings sollten Anwendungen afxwin.h enthalten.  
  
### <a name="ddv-functions"></a>DDV-Funktionen  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|Stellt sicher, dass die Anzahl der Zeichen in einem bestimmten Steuerelement eine festgelegte maximale nicht überschreitet.|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **BYTE** Bereich.|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht mit einen bestimmten Zeitraum überschreitet.|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **doppelte** Bereich.|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **DWORD** Bereich.|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **"float"** Bereich.|  
|[DDV_MinMaxInt](#ddv_minmaxint)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **Int** Bereich.|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **lange** Bereich.|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **LONGLONG** Bereich.|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Überprüft, ob ein bestimmtes Steuerelementwert nicht über einen bestimmten Zeitraum überschreitet.|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **kurze** Bereich.|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Stellt sicher, dass der Wert einer angegebenen Schieberegler-Steuerelements innerhalb des angegebenen Bereichs liegt.|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **"uint"** Bereich.|  
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Überprüft, ob ein bestimmtes Steuerelementwert zwischen zwei angegebenen Werten liegt.| 
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **ULONGLONG** Bereich.|  
  

  
##  <a name="ddv_maxchars"></a>DDV_MaxChars  
 Rufen Sie `DDV_MaxChars` um sicherzustellen, dass die Anzahl der Zeichen im Steuerelement zugeordnete *Wert* nicht überschreitet *nChars*.  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `nChars`  
 Maximale Anzahl der zulässigen Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxbyte"></a>DDV_MinMaxByte  
 Rufen Sie `DDV_MinMaxByte` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,  
    BYTE value,  
    BYTE minVal,  
    BYTE maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **BYTE**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **BYTE**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime  
 Rufen Sie `DDV_MinMaxDateTime` um sicherzustellen, dass der Datums-/-Wert in der Datums- / Zeitauswahl gesteuert ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) zugeordneten *RefValue* liegt zwischen `refMinRange` und `refMaxRange`.  
  
```   
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen nicht das Objekt gelöscht werden.  
  
 *refValue*  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts zugeordnet. Dieses Objekt enthält die Daten überprüft werden.  
  
 `refMinRange`  
 Minimale Datum/Uhrzeit-Wert zulässig.  
  
 `refMaxRange`  
 Zulässige maximale Datum/Uhrzeit-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble  
 Rufen Sie `DDV_MinMaxDouble` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,  
    double const& value,  
    double minVal,  
    double maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **doppelte**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **doppelte**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxdword"></a>DDV_MinMaxDWord  
 Rufen Sie `DDV_MinMaxDWord` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,  
    DWORD const& value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs `DWORD`) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs `DWORD`) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat  
 Rufen Sie `DDV_MinMaxFloat` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,  
    float value,  
    float minVal,  
    float maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **"float"**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **"float"**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxint"></a>DDV_MinMaxInt  
 Rufen Sie `DDV_MinMaxInt` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,  
    int value,  
    int minVal,  
    int maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs `int`) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs `int`) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxlong"></a>DDV_MinMaxLong  
 Rufen Sie `DDV_MinMaxLong` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,  
    long value,  
    long minVal,  
    long maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **lange**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **lange**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong  
 Rufen Sie `DDV_MinMaxLongLong` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,  
    LONGLONG value,  
    LONGLONG minVal,  
    LONGLONG maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **LONGLONG**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **LONGLONG**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth  
 Rufen Sie `DDV_MinMaxMonth` , stellen Sie sicher, dass der Datums-/-Wert im Monatskalender-Steuerelement ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) zugeordneten *RefValue* liegt zwischen `refMinRange` und `refMaxRange`.  
  
```   
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *refValue*  
 Ein Verweis auf ein Objekt des Typs `CTime` oder `COleDateTime` zugeordnete eine Membervariable des Dialogfelds, Formularansicht oder Sichtobjekt steuern. Dieses Objekt enthält die Daten überprüft werden. MFC-übergibt, die diese auf, wenn `DDV_MinMaxMonth` aufgerufen wird.  
  
 `refMinRange`  
 Minimale Datum/Uhrzeit-Wert zulässig.  
  
 `refMaxRange`  
 Zulässige maximale Datum/Uhrzeit-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxshort"></a>DDV_MinMaxShort  
 Rufen Sie `DDV_MinMaxShort` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,  
    short value,  
    short minVal,  
    short maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **kurze**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **kurze**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxslider"></a>DDV_MinMaxSlider  
 Rufen Sie `DDV_MinMaxSlider` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,  
    DWORD value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf die zu überprüfende Wert. Dieser Parameter enthält, oder legt das Schieberegler-Steuerelement aktuelle Thumb Position fest.  
  
 `minVal`  
 Minimal zulässige Wert.  
  
 `maxVal`  
 Maximal zulässige Wert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxuint"></a>DDV_MinMaxUInt  
 Rufen Sie `DDV_MinMaxUInt` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,  
    UINT value,  
    UINT minVal,  
    UINT maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **"uint"**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **"uint"**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong  
 Rufen Sie `DDV_MinMaxULongLong` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,  
    ULONGLONG value,  
    ULONGLONG  minVal ,  
    ULONGLONG  maxVal); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **ULONGLONG**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **ULONGLONG**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
    
## <a name="see-also"></a>Siehe auch  
 [Standard Dialogdatenaustauschroutinen](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

 ## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned
Rufen Sie `DDV_MinMaxUnsigned` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen `minVal` und `maxVal`.  
   
### <a name="syntax"></a>Syntax    
```
   void AFXAPI DDV_MinMaxUnsigned(  
       CDataExchange* pDX,  
       unsigned value,  
       unsigned minVal,  
       unsigned maxVal );  
```
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.  
  
 `minVal`  
 Minimalwert (des Typs **ohne Vorzeichen** ) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **ohne Vorzeichen** ) zulässig.  
   
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../dialog-data-exchange-and-validation.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdd_.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [DDX_Slider](#ddx_slider)   
 [DDX_FieldSlider](#ddx_fieldslider)
 


