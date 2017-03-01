---
title: "Standardroutinen Validierung für Dialogfelddaten | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 87cf0389b7b58579a8674d4075d2601186b1ae95
ms.lasthandoff: 02/24/2017

---
# <a name="standard-dialog-data-validation-routines"></a>Standardroutinen zur Validierung der Dialogfelddaten
In diesem Thema wird das Standarddialogfeld (DDV) datenvalidierungsroutine für allgemeine MFC-Dialogfeld-Steuerelemente verwendet.  
  
> [!NOTE]
>  Die standardmäßige dialogdatenaustauschroutinen werden in den Header-Datei afxdd_.h definiert. Allerdings sollten Applications afxwin.h enthalten.  
  
### <a name="ddv-functions"></a>DDV-Funktionen  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|Stellt sicher, dass die Anzahl der Zeichen in einem bestimmten Steuerelement nicht über eine festgelegte maximale überschreitet.|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **BYTE** Bereich.|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Überprüft, ob ein bestimmtes Steuerelementwert nicht mit einen bestimmten Zeitraum überschreitet.|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **doppelte** Bereich.|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **DWORD** Bereich.|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **Float** Bereich.|  
|[DDV_MinMaxInt](#ddv_minmaxint)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **Int** Bereich.|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **lang** Bereich.|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **LONGLONG** Bereich.|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Überprüft, ob ein bestimmtes Steuerelementwert nicht über einen bestimmten Zeitraum überschreitet.|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **kurze** Bereich.|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Überprüft, ob eine bestimmte Schieberegler-Steuerelement innerhalb des angegebenen Bereichs liegt.|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **UINT** Bereich.|  
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Überprüft, ob ein bestimmtes Steuerelement-Wert nicht überschreitet einen bestimmten **ULONGLONG** Bereich.|  
  

  
##  <a name="a-nameddvmaxcharsa--ddvmaxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars  
 Rufen Sie `DDV_MaxChars` zu überprüfen, ob die Anzahl der Zeichen im Steuerelement zugeordnete *Wert* nicht länger als *nChars*.  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `nChars`  
 Maximale Anzahl von Zeichen zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxbytea--ddvminmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte  
 Rufen Sie `DDV_MinMaxByte` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **BYTE**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **BYTE**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxdatetimea--ddvminmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime  
 Rufen Sie `DDV_MinMaxDateTime` zu überprüfen, ob der Datum/Uhrzeit-Wert in die Datums- und Zeitauswahl steuern ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) zugeordneten *RefValue* zwischen `refMinRange` und `refMaxRange`.  
  
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
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen dieses Objekt löschen.  
  
 *refValue*  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) eine Membervariable des Dialogfelds, Formularansicht oder Control-Objekt zugeordnete Objekt. Dieses Objekt enthält die Daten überprüft werden.  
  
 `refMinRange`  
 Minimale zulässige Wert für Datum/Uhrzeit.  
  
 `refMaxRange`  
 Zulässige maximale Datum/Uhrzeit-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxdoublea--ddvminmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble  
 Rufen Sie `DDV_MinMaxDouble` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **doppelte**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **doppelte**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxdworda--ddvminmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord  
 Rufen Sie `DDV_MinMaxDWord` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs `DWORD`) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs `DWORD`) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxfloata--ddvminmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat  
 Rufen Sie `DDV_MinMaxFloat` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **Float**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **Float**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxinta--ddvminmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt  
 Rufen Sie `DDV_MinMaxInt` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs `int`) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs `int`) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonga--ddvminmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong  
 Rufen Sie `DDV_MinMaxLong` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **lang**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **lang**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonglonga--ddvminmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong  
 Rufen Sie `DDV_MinMaxLongLong` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **LONGLONG**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **LONGLONG**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxmontha--ddvminmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth  
 Rufen Sie `DDV_MinMaxMonth` , stellen Sie sicher, dass die Datum/Uhrzeit-Wert im Monatskalender-Steuerelement ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) zugeordneten *RefValue* zwischen `refMinRange` und `refMaxRange`.  
  
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
 Ein Verweis auf ein Objekt vom Typ `CTime` oder `COleDateTime` eine Membervariable des Dialogfelds zugeordnet sind, Formularansicht oder Steuern von View-Objekt. Dieses Objekt enthält die Daten überprüft werden. MFC übergibt diese auf, wenn `DDV_MinMaxMonth` aufgerufen wird.  
  
 `refMinRange`  
 Minimale zulässige Wert für Datum/Uhrzeit.  
  
 `refMaxRange`  
 Zulässige maximale Datum/Uhrzeit-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxshorta--ddvminmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort  
 Rufen Sie `DDV_MinMaxShort` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **kurze**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **kurze**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxslidera--ddvminmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider  
 Rufen Sie `DDV_MinMaxSlider` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf die zu überprüfende Wert. Dieser Parameter enthält, oder legt das Schieberegler-Steuerelement aktuelle Thumb Position fest.  
  
 `minVal`  
 Minimal zulässige Wert.  
  
 `maxVal`  
 Maximal zulässige Wert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxuinta--ddvminmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt  
 Rufen Sie `DDV_MinMaxUInt` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **UINT**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **UINT**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddvminmaxulonglonga--ddvminmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong  
 Rufen Sie `DDV_MinMaxULongLong` zu überprüfen, ob der Wert im Steuerelement zugeordnete *Wert* zwischen `minVal` und `maxVal`.  
  
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
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten überprüft werden.  
  
 `minVal`  
 Mindestwert (des Typs **ULONGLONG**) zulässig.  
  
 `maxVal`  
 Maximalwert (des Typs **ULONGLONG**) zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
    
## <a name="see-also"></a>Siehe auch  
 [Standardmäßige Dialogdatenaustauschroutinen](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

