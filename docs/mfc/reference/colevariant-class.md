---
title: COleVariant-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
dev_langs: C++
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 45e3fde574dee564e126ae7fbbc42e8ee5a61442
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="colevariant-class"></a>COleVariant-Klasse
Kapselt den Datentyp [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) .  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|Erstellt ein `COleVariant`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|Fügt eine **VARIANT** zu einem `COleVariant`.|  
|[COleVariant::ChangeType](#changetype)|Ändert die Varianten-Typ dieses `COleVariant` Objekt.|  
|[COleVariant::Clear](#clear)|Löscht diese `COleVariant` Objekt.|  
|[COleVariant::Detach](#detach)|Trennt eine **VARIANT** aus einem `COleVariant` und gibt die **VARIANT**.|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Ruft ein Bytearray aus einem vorhandenen variant-Array ab.|  
|[COleVariant::SetString](#setstring)|Legt die Zeichenfolge für eine bestimmte Art, in der Regel ANSI.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Konvertiert eine `COleVariant` Wert in einer `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Konvertiert eine `COleVariant` -Objekt in ein `LPVARIANT`.|  
|[COleVariant::operator =](#operator_eq)|Kopiert ein `COleVariant` Wert.|  
|[COleVariant::operator ==](#operator_eq_eq)|Vergleicht zwei `COleVariant` Werte.|  
|[COleVariant::operator &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|Ausgaben einen `COleVariant` Wert `CArchive` oder `CDumpContext` und Eingaben ein `COleVariant` -Sitzungsobjekts `CArchive`.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Datentyp wird in der OLE-Automatisierung verwendet. Insbesondere die [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b) Struktur enthält einen Zeiger auf ein Array von **VARIANT** Strukturen. Ein **DISPPARAMS** Struktur wird verwendet, um zum Übergeben von Parametern [IDispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  Diese Klasse ist abgeleitet von der **VARIANT** Struktur. Dies bedeutet, Sie können übergeben, eine `COleVariant` in einem Parameter, der erfordert eine **VARIANT** und Datenmember der der **VARIANT** Struktur stehen zugegriffen werden die Datenmember der `COleVariant`.  
  
 Die beiden MFC-Klassen beziehen [COleCurrency](../../mfc/reference/colecurrency-class.md) und [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) kapseln die variant-Datentypen **Währung** ( `VT_CY`) und **Datum** ( `VT_DATE`). Die `COleVariant` Klasse umfassend in den DAO-Klassen verwendet wird, finden Sie diese Klassen für die typische Verwendung dieser Klasse, z. B. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b), und [IDispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) Einträge in das Windows SDK.  
  
 Weitere Informationen zu den `COleVariant` Klasse und ihre Verwendung in der OLE-Automatisierung finden Sie unter "Übergeben von Parametern in OLE-Automatisierung" im Artikel [Automatisierung](../../mfc/automation.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="attach"></a>COleVariant::Attach  
 Mit dieser Funktion werden zum Anfügen der angegebenen [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Objekt mit dem aktuellen `COleVariant` Objekt.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *varSrc*  
 Eine vorhandene **VARIANT** Objekt mit dem aktuellen anzufügenden `COleVariant` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion legt die [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) von *VarSrc* auf `VT_EMPTY`.  
  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) und [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) Einträge in das Windows SDK.  
  
##  <a name="colevariant"></a>COleVariant::COleVariant  
 Erstellt ein `COleVariant`-Objekt.  
  
```  
COleVariant(); 
COleVariant(const VARIANT& varSrc); 
COleVariant(const COleVariant& varSrc); 
COleVariant(LPCVARIANT pSrc); 
COleVariant(LPCTSTR lpszSrc); 
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc); 
COleVariant(CString& strSrc); 
COleVariant(BYTE nSrc); 
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2); 
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4); 
COleVariant(const COleCurrency& curSrc); 
COleVariant(float fltSrc); 
COleVariant(double dblSrc); 
COleVariant(const COleDateTime& timeSrc); 
COleVariant(const CByteArray& arrSrc); 
COleVariant(const CLongBinary& lbSrc); 
COleVariant(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 *varSrc*  
 Eine vorhandene `COleVariant` oder **VARIANT** -Objekt, in das neue kopiert werden `COleVariant` Objekt.  
  
 `pSrc`  
 Ein Zeiger auf eine **VARIANT** -Objekt, das in das neue kopiert werden `COleVariant` Objekt.  
  
 `lpszSrc`  
 Eine Null-terminierte Zeichenfolge in das neue kopiert werden `COleVariant` Objekt.  
  
 `vtSrc`  
 Die `VARTYPE` für die neue `COleVariant` Objekt.  
  
 `strSrc`  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, in das neue kopiert werden `COleVariant` Objekt.  
  
 `nSrc`, `lSrc`  
 Ein in das neue `COleVariant`-Objekt zu kopierender numerischer Wert.  
  
 `vtSrc`  
 Die `VARTYPE` für die neue `COleVariant` Objekt.  
  
 `curSrc`  
 Ein [COleCurrency](../../mfc/reference/colecurrency-class.md) -Objekt, in das neue kopiert werden `COleVariant` Objekt.  
  
 `fltSrc`, `dblSrc`  
 Ein in das neue `COleVariant`-Objekt zu kopierender numerischer Wert.  
  
 `timeSrc`  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, in das neue kopiert werden `COleVariant` Objekt.  
  
 `arrSrc`  
 Ein [CByteArray](../../mfc/reference/cbytearray-class.md) -Objekt, in das neue kopiert werden `COleVariant` Objekt.  
  
 `lbSrc`  
 Ein [CLongBinary](../../mfc/reference/clongbinary-class.md) -Objekt, in das neue kopiert werden `COleVariant` Objekt.  
  
 `pidl`  
 Ein Zeiger auf eine [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) Struktur an, in die neue kopiert werden `COleVariant` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen Sie eine neue `COleVariant` Objekte, die auf den angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt.  
  
- **COleVariant ()** erstellt ein leeres `COleVariant` Objekt `VT_EMPTY`.  
  
- **COleVariant (** *VarSrc* **)** kopiert eine vorhandene **VARIANT** oder `COleVariant` Objekt. Der Varianttyp wird beibehalten.  
  
- **COleVariant (** `pSrc` **)** kopiert eine vorhandene **VARIANT** oder `COleVariant` Objekt. Der Varianttyp wird beibehalten.  
  
- **COleVariant (** `lpszSrc` **)** kopiert eine Zeichenfolge in das neue Objekt `VT_BSTR` (UNICODE).  
  
- **COleVariant (** `lpszSrc` **,** `vtSrc` **)** kopiert eine Zeichenfolge in das neue Objekt. Der Parameter `vtSrc` muss `VT_BSTR` (UNICODE) oder `VT_BSTRT` (ANSI).  
  
- **COleVariant (** `strSrc` **)** kopiert eine Zeichenfolge in das neue Objekt **"VT_BSTR"** (UNICODE).  
  
- **COleVariant (** `nSrc` **)** eine 8-Bit-Ganzzahl in das neue Objekt kopiert `VT_UI1`.  
  
- **COleVariant (** `nSrc` **,** `vtSrc` **)** eine 16-Bit-Ganzzahl (oder ein boolescher Wert) in das neue Objekt kopiert. Der Parameter `vtSrc` muss `VT_I2` oder `VT_BOOL`.  
  
- **COleVariant (** `lSrc` **,** `vtSrc` **)** kopiert eine 32-Bit-Ganzzahl (oder `SCODE` Wert) in das neue Objekt. Der Parameter `vtSrc` muss `VT_I4`, `VT_ERROR`, oder `VT_BOOL`.  
  
- **COleVariant (** `curSrc` **)** Kopien einer **COleCurrency** Wert in das neue Objekt `VT_CY`.  
  
- **COleVariant (** `fltSrc` **)** eine 32-Bit-Gleitkommawert in das neue Objekt kopiert `VT_R4`.  
  
- **COleVariant (** `dblSrc` **)** eine 64-Bit-Gleitkommawert in das neue Objekt kopiert `VT_R8`.  
  
- **COleVariant (** `timeSrc` **)** Kopien einer `COleDateTime` Wert in das neue Objekt `VT_DATE`.  
  
- **COleVariant (** `arrSrc` **)** Kopien einer `CByteArray` Objekt in das neue Objekt `VT_EMPTY`.  
  
- **COleVariant (** `lbSrc` **)** Kopien einer `CLongBinary` Objekt in das neue Objekt `VT_EMPTY`.  
  
 Weitere Informationen zu `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) im Windows SDK.  
  
##  <a name="changetype"></a>COleVariant::ChangeType  
 Konvertiert den Typ des variant-Wert in diesem `COleVariant` Objekt.  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `vartype`  
 Die [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) dafür `COleVariant` Objekt.  
  
 `pSrc`  
 Ein Zeiger auf die [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) zu konvertierende Objekt. Wenn dieser Wert ist **NULL**, gibt diese `COleVariant` Objekt dient als Quelle für die Konvertierung.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), und [VariantChangeType](http://msdn.microsoft.com/en-us/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) Einträge in das Windows SDK.  
  
##  <a name="clear"></a>COleVariant::Clear  
 Löscht die **VARIANT**.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird die **VARTYPE** für dieses Objekt zu `VT_EMPTY`. Die `COleVariant` Destruktor ruft diese Funktion.  
  
 Weitere Informationen finden Sie unter der `VARIANT`, `VARTYPE`, und `VariantClear` Einträge in das Windows SDK.  
  
##  <a name="detach"></a>COleVariant::Detach  
 Trennt den zugrunde liegenden [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) -Objekt von diesem `COleVariant` Objekt.  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion legt die [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) für diesen `COleVariant` -Objekt `VT_EMPTY`.  
  
> [!NOTE]
>  Nach dem Aufruf **trennen**, rufen Sie in der Verantwortung des Aufrufers wird **VariantClear** für die resultierende **VARIANT** Struktur.  
  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), und [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) Einträge in das Windows SDK.  
  
##  <a name="getbytearrayfromvariantarray"></a>COleVariant::GetByteArrayFromVariantArray  
 Ruft ein Bytearray aus einem vorhandenen variant-array  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Parameter  
 `bytes`  
 Ein Verweis auf ein vorhandenes [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt.  
  
##  <a name="operator_lpcvariant"></a>COleVariant::operator LPCVARIANT  
 Dieser Umwandlungsoperator gibt eine `VARIANT` -Struktur, deren Wert wird aus dieser kopiert `COleVariant` Objekt.  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="operator_lpvariant"></a>COleVariant::operator LPVARIANT  
 Rufen Sie diese Typumwandlungsoperator, um Zugriff auf die zugrunde liegenden `VARIANT` Struktur für dieses `COleVariant` Objekt.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Ändern des Werts in der **VARIANT** zugegriffen wird, die von dieser Funktion zurückgegebenen Zeiger Struktur ändert sich den Wert dieses `COleVariant` Objekt.  
  
##  <a name="operator_eq"></a>COleVariant::operator =  
 Diese überladenen Zuweisungsoperatoren kopieren den Quellwert in diese `COleVariant` Objekt.  
  
```  
const COleVariant& operator=(const VARIANT& varSrc); 
const COleVariant& operator=(LPCVARIANT pSrc); 
const COleVariant& operator=(const COleVariant& varSrc); 
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc); 
const COleVariant& operator=(BYTE nSrc); 
const COleVariant& operator=(short nSrc); 
const COleVariant& operator=(long lSrc); 
const COleVariant& operator=(const COleCurrency& curSrc); 
const COleVariant& operator=(float fltSrc); 
const COleVariant& operator=(double dblSrc); 
const COleVariant& operator=(const COleDateTime& dateSrc); 
const COleVariant& operator=(const CByteArray& arrSrc); 
const COleVariant& operator=(const CLongBinary& lbSrc);
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung der einzelnen Operatoren lautet folgendermaßen:  
  
- **Operator = (** *VarSrc***)** kopiert eine vorhandene **VARIANT** oder `COleVariant` -Objekts in dieses Objekt.  
  
- **Operator = (** `pSrc` **)** Kopien der **VARIANT** Objekt zugreift `pSrc` in dieses Objekt.  
  
- **Operator = (** `lpszSrc` **)** eine Null-terminierte Zeichenfolge in dieses Objekt übernimmt und legt die **VARTYPE** auf `VT_BSTR`.  
  
- **Operator = (** `strSrc` **)** Kopien einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekts in dieses Objekt und legt die **VARTYPE** auf `VT_BSTR`.  
  
- **Operator = (** `nSrc` **)** 8 oder 16-Bit-Ganzzahlwert mit diesem Objekt kopiert. Wenn `nSrc` ist ein 8-Bit-Wert, der **VARTYPE** der dies festgelegt ist `VT_UI1`. Wenn `nSrc` ist ein 16-Bit-Wert und die **VARTYPE** wird dieses `VT_BOOL`, beibehalten werden; andernfalls ist er festgelegt, `VT_I2`.  
  
- **Operator = (** `lSrc` **)** kopiert einen 32-Bit-Ganzzahl-Wert in dieses Objekt. Wenn die **VARTYPE** wird dieses `VT_ERROR`, beibehalten werden; andernfalls ist er festgelegt, `VT_I4`.  
  
- **Operator = (** `curSrc` **)** Kopien einer [COleCurrency](../../mfc/reference/colecurrency-class.md) -Objekts in dieses Objekt und legt die **VARTYPE** auf `VT_CY`.  
  
- **Operator = (** `fltSrc` **)** eine 32-Bit-Gleitkommawert in dieses Objekt übernimmt und legt die **VARTYPE** auf `VT_R4`.  
  
- **Operator = (** `dblSrc` **)** eine 64-Bit-Gleitkommawert in dieses Objekt übernimmt und legt die **VARTYPE** auf `VT_R8`.  
  
- **Operator = (** `dateSrc` **)** Kopien einer [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekts in dieses Objekt und legt die **VARTYPE** auf `VT_DATE`.  
  
- **Operator = (** `arrSrc` **)** Kopien einer [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt in diese `COleVariant` Objekt.  
  
- **Operator = (** `lbSrc` **)** Kopien einer [CLongBinary](../../mfc/reference/clongbinary-class.md) Objekt in diese `COleVariant` Objekt.  
  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) und [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) Einträge in das Windows SDK.  
  
##  <a name="operator_eq_eq"></a>COleVariant::operator ==  
 Dieser Operator vergleicht zwei variant-Werte und gibt einen Wert ungleich NULL, wenn sie gleich sind; andernfalls 0.  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>COleVariant::operator &lt; &lt;,&gt;&gt;  
 Ausgaben einen `COleVariant` Wert `CArchive` oder **CdumpContext** und Eingaben ein `COleVariant` -Sitzungsobjekts `CArchive`.  
  
```  
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,  
    OleVariant varSrc);
 
friend CArchive& AFXAPI operator<<(
    CArchive& ar,  
    COleVariant varSrc);
 
friend CArchive& AFXAPI operator>>(
    CArchive& ar,  
    COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Hinweise  
 Die `COleVariant` einfügen (  **< \<** ) Operator unterstützt Diagnose-Dump-Sicherungen und das Speichern in ein Archiv. Die Extrahierung (  **>>** ) Operator unterstützt das Laden aus einem Archiv.  
  
##  <a name="setstring"></a>COleVariant::SetString  
 Legt die Zeichenfolge in einen bestimmten Typ an.  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSrc`  
 Eine Null-terminierte Zeichenfolge in das neue kopiert werden `COleVariant` Objekt.  
  
 *VtSrc*  
 Die **VARTYPE** für die neue `COleVariant` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `vtSrc` muss `VT_BSTR` (UNICODE) oder `VT_BSTRT` (ANSI). `SetString`dient normalerweise zum Festlegen von Zeichenfolgen in ANSI, seit der Standard für die [COleVariant::COleVariant](#colevariant) Konstruktor mit einer Zeichenfolge oder Zeichenfolge Zeigerparameter und keine **VARTYPE** Unicode-Format vorliegt.  
  
 Ein DAO-Recordset in einem nicht-Unicode-Build erwartet Zeichenfolgen in ANSI sein. Folglich für DAO-Funktionen, bei denen `COleVariant` Objekte, wenn Sie eine Unicode-Recordset nicht erstellen, müssen Sie verwenden die **COleVariant::COleVariant (** `lpszSrc` **,** `vtSrc` **)**  Form der Konstruktor mit `vtSrc` festgelegt `VT_BSTRT` (ANSI), oder verwenden Sie `SetString` mit `vtSrc` festgelegt `VT_BSTRT` zu ANSI-Zeichenfolgen. Z. B. die `CDaoRecordset` Funktionen [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) und [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) verwenden `COleVariant` -Objekte als Parameter. Diese Objekte müssen ANSI sein, wenn DAO-Recordsets nicht um UNICODE handelt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



