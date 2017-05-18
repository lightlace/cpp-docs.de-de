---
title: CComVariant-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4b01ca9da3d216603ea7efad228735edd1becbd3
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomvariant-class"></a>CComVariant-Klasse
Diese Klasse umschließt den `VARIANT` Typ, einen Member, der angibt, der Typ der gespeicherten Daten bereitstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|Der Konstruktor.|  
|[CComVariant:: ~ CComVariant](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|Fügt eine **VARIANT** an die `CComVariant` Objekt.|  
|[CComVariant::ChangeType](#changetype)|Konvertiert die `CComVariant` Objekt in einen neuen Typ.|  
|[CComVariant::Clear](#clear)|Löscht die `CComVariant` Objekt.|  
|[CComVariant::Copy](#copy)|Kopiert eine **VARIANT** an die `CComVariant` Objekt.|  
|[CComVariant::CopyTo](#copyto)|Kopiert den Inhalt der `CComVariant` Objekt.|  
|[CComVariant::Detach](#detach)|Trennt den zugrunde liegenden **VARIANT** aus der `CComVariant` Objekt.|  
|[CComVariant::GetSize](#getsize)|Gibt die Größe in Anzahl von Bytes des Inhalts der `CComVariant` Objekt.|  
|[CComVariant::ReadFromStream](#readfromstream)|Lädt eine **VARIANT** aus einem Stream.|  
|[CComVariant::SetByRef](#setbyref)|Initialisiert die `CComVariant` -Objekt und legt die **vt** Element **VT_BYREF**.|  
|[CComVariant:: WriteToStream](#writetostream)|Speichert die zugrunde liegende **VARIANT** in einen Stream.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|||  
|-|-|  
|[CComVariant](#operator_lt)|Gibt an, ob die `CComVariant` Objekt ist kleiner als der angegebene **VARIANT**.|  
|[CComVariant >](#operator_gt)|Gibt an, ob die `CComVariant` -Objekt ist größer als der angegebene **VARIANT**.|  
|[Operator! =](#operator_neq)|Gibt an, ob die `CComVariant` Objekt entspricht nicht dem angegebenen **VARIANT**.|  
|[Operator =](#operator_eq)|Weist einen Wert an das `CComVariant` Objekt.|  
|[Operator ==](#operator_eq_eq)|Gibt an, ob die `CComVariant` Objekt gleich dem angegebenen **VARIANT**.|  
  
## <a name="remarks"></a>Hinweise  
 `CComVariant`umschließt den `VARIANT and VARIANTARG` Typ, besteht eine Union und einen Member, der in der Union gespeicherten Daten angibt. **VARIANT**in der Regel bei der Automatisierung verwendet.  
  
 `CComVariant`leitet sich von der **VARIANT** geben, damit es sein kann, verwendet, wo ein **VARIANT** kann verwendet werden. Z. B. können Sie die **V_VT** Makro, um den Typ des zu extrahieren einer `CComVariant` oder auf Sie zugreifen die **vt** Member direkt wie können Sie eine **VARIANT**.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcomcli.h  
  
##  <a name="attach"></a>CComVariant::Attach  
 Sicher löscht den aktuellen Inhalt der der `CComVariant` Objekt, das kopiert den Inhalt des `pSrc` in dieses Objekt legt dann den Varianten-Typ der `pSrc` auf `VT_EMPTY`.  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `pSrc`  
 [in] Verweist auf die [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) an das Objekt angefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Daten frei, `pSrc` wird zum Übertragen der `CComVariant` Objekt.  
  
##  <a name="ccomvariant"></a>CComVariant::CComVariant  
 Jeder Konstruktor übernimmt die sichere Initialisierung von der `CComVariant` -Objekt durch Aufrufen der `VariantInit` Win32-Funktion oder durch Festlegen des Objekts Wert und Typ gemäß den übergebenen Parametern.  
  
```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *varSrc*  
 [in] Die `CComVariant` oder `VARIANT` zur Initialisierung der `CComVariant` Objekt. Der Inhalt der Quelle Variante werden an das Ziel ohne Konvertierung kopiert.  
  
 `lpszSrc`  
 [in] Die Zeichenfolge, die zum Initialisieren der `CComVariant` Objekt. Können Sie eine NULL-terminierte Breite (Unicode-) Zeichenfolge mit Zeichen übergeben der **LPCOLESTR** Version von dem Konstruktor oder eine ANSI-Zeichenfolge, die die `LPCSTR` Version. In beiden Fällen wird die Zeichenfolge in Unicode konvertiert `BSTR` mit reserviert **SysAllocString**. Der Typ, der die `CComVariant` Objekt `VT_BSTR`.  
  
 `bSrc`  
 [in] Die `bool` zur Initialisierung der `CComVariant` Objekt. Die `bool` Argument in konvertiert eine **VARIANT_BOOL** vor dem Speichern. Der Typ, der die `CComVariant` Objekt `VT_BOOL`.  
  
 `nSrc`  
 [in] Die `int`, **BYTE**, **kurze**, **lang**, **LONGLONG**, **ULONGLONG**, **kurz ohne Vorzeichen**, `unsigned long`, oder `unsigned int` zur Initialisierung der `CComVariant` Objekt. The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `vtSrc`  
 [in] Der Typ der Variante. Wenn der erste Parameter ist `int`, die gültigen Typen sind `VT_I4` und **VT_INT**. Wenn der erste Parameter ist **lang**, die gültigen Typen sind `VT_I4` und `VT_ERROR`. Wenn der erste Parameter ist **doppelte**, die gültigen Typen sind `VT_R8` und `VT_DATE`. Wenn der erste Parameter ist `unsigned int`, die gültigen Typen sind **VT_UI4** und **VT_UINT**.  
  
 `fltSrc`  
 [in] Die **Float** zur Initialisierung der `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_R4`.  
  
 `dblSrc`  
 [in] Die **doppelte** zur Initialisierung der `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_R8`.  
  
 `cySrc`  
 [in] Die **CY** zur Initialisierung der `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_CY`.  
  
 `pSrc`  
 [in] Die `IDispatch` oder **IUnknown** Zeiger, die zum Initialisieren der `CComVariant` Objekt. `AddRef`wird für den Schnittstellenzeiger aufgerufen werden. Der Typ, der die `CComVariant` Objekt **VT_DISPATCH** oder **VT_UNKNOWN**bzw..  
  
 Or **SAFERRAY** Zeiger, die zum Initialisieren der `CComVariant` Objekt. Eine Kopie der **SAFEARRAY** befindet sich in der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt ist eine Kombination aus den ursprünglichen Typ des wird die **SAFEARRAY** und **VT_ARRAY**.  
  
 `cSrc`  
 [in] Die `char` zur Initialisierung der `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt **VT_I1**.  
  
 `bstrSrc`  
 [in] BSTR zum Initialisieren verwendet die `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_BSTR`.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor verwaltet Bereinigung durch Aufrufen von [CComVariant::Clear](#clear).  
  
##  <a name="dtor"></a>CComVariant:: ~ CComVariant  
 Der Destruktor.  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwaltet Bereinigung durch Aufrufen von [CComVariant::Clear](#clear).  
  
##  <a name="changetype"></a>CComVariant::ChangeType  
 Konvertiert die `CComVariant` Objekt in einen neuen Typ.  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `vtNew`  
 [in] Der neue Typ für die `CComVariant` Objekt.  
  
 `pSrc`  
 [in] Ein Zeiger auf die `VARIANT` , deren Wert wird in den neuen Typ konvertiert werden. Der Standardwert ist **NULL**, d. h. die `CComVariant` -Objekt wird an Stelle konvertiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie keinen Wert, für die übergeben `pSrc`, `ChangeType` verwenden werden **VARIANT** als Quelle für die Konvertierung. Andernfalls die `CComVariant` Objekt ist die Ursache.  
  
##  <a name="clear"></a>CComVariant::Clear  
 Löscht die `CComVariant` -Objekt durch Aufrufen der `VariantClear` Win32-Funktion.  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Ruft der Destruktor automatisch **löschen**.  
  
##  <a name="copy"></a>CComVariant::Copy  
 Frei der `CComVariant` Objekt und weist es eine Kopie des angegebenen **VARIANT**.  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `pSrc`  
 [in] Ein Zeiger auf die [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="copyto"></a>CComVariant::CopyTo  
 Kopiert den Inhalt der `CComVariant` Objekt.  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrDest*  
 Verweist auf eine `BSTR` erhalten, die eine Kopie des Inhalts der `CComVariant` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die **CComVariant** Objekt muss vom Typ `VT_BSTR`.  
  
##  <a name="detach"></a>CComVariant::Detach  
 Trennt den zugrunde liegenden **VARIANT** aus der `CComVariant` -Objekt und legt den Typ des Objekts auf `VT_EMPTY`.  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 [out] Gibt den zugrunde liegenden `VARIANT` Wert des Objekts.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Inhalt des der `VARIANT` verweist `pDest` wird automatisch gelöscht werden, bevor Sie den Wert und Typ des aufrufenden zugewiesen werden **CComVariant** Objekt.  
  
##  <a name="getsize"></a>CComVariant::GetSize  
 Für einfache feste Größe `VARIANT`s, diese Methode gibt die `sizeof` den zugrunde liegenden Datentyp plus `sizeof(VARTYPE)`.  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe in Bytes, der den aktuellen Inhalt des dem `CComVariant` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `VARIANT` enthält einen Schnittstellenzeiger `GetSize` fragt `IPersistStream` oder `IPersistStreamInit`. Bei erfolgreicher der Rückgabewert die niederwertigen 32 Bits des Werts von zurückgegebenen `GetSizeMax` sowie die `sizeof` eine `CLSID` und `sizeof(VARTYPE)`. Wenn der Schnittstellenzeiger `NULL`, `GetSize` gibt die `sizeof` eine `CLSID` plus `sizeof(VARTYPE)`. Wenn die Gesamtgröße größer als `ULONG_MAX`, `GetSize` gibt `sizeof(VARTYPE)` gibt einen Fehler an.  
  
 In allen anderen Fällen eine temporäre `VARIANT` des Typs `VT_BSTR` wird aus dem aktuellen umgewandelt `VARIANT`. Die Länge dieses `BSTR` wird berechnet als die Größe der Länge der Zeichenfolge plus die Länge der Zeichenfolge selbst sowie die Größe des Null-Zeichens plus `sizeof(VARTYPE)`. Wenn die `VARIANT` kann nicht umgewandelt werden, um eine `VARIANT` des Typs `VT_BSTR`, `GetSize` gibt `sizeof(VARTYPE)`.  
  
 Die von dieser Methode zurückgegebene Größe entspricht der Anzahl der Bytes vom [CComVariant:: WriteToStream](#writetostream) unter Umständen erfolgreich.  
  
##  <a name="operator_eq"></a>CComVariant =  
 Weist einen Wert und der entsprechende Typ, der `CComVariant` Objekt.  
  
```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *varSrc*  
 [in] Die `CComVariant` oder [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) zugewiesen, die `CComVariant` Objekt. Der Inhalt der Quelle Variante werden an das Ziel ohne Konvertierung kopiert.  
  
 `bstrSrc`  
 [in] BSTR zugewiesen werden, die `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_BSTR`.  
  
 `lpszSrc`  
 [in] Die Zeichenfolge, zugewiesen werden, die `CComVariant` Objekt. Sie können eine NULL-terminierte Breite (Unicode-) Zeichenfolge mit Zeichen übergeben der **LPCOLESTR** Version der Operator oder eine ANSI-Zeichenfolge, die die `LPCSTR` Version. In beiden Fällen wird die Zeichenfolge in Unicode konvertiert `BSTR` mit reserviert **SysAllocString**. Der Typ, der die `CComVariant` Objekt `VT_BSTR`.  
  
 `bSrc`  
 [in] Die `bool` zugewiesen, die `CComVariant` Objekt. Die `bool` Argument in konvertiert eine **VARIANT_BOOL** vor dem Speichern. Der Typ, der die `CComVariant` Objekt `VT_BOOL`.  
  
 `nSrc`  
 [in] The `int`, **BYTE**, **short**, **long**, **LONGLONG**, **ULONGLONG**, **unsigned short**, `unsigned long`, or `unsigned int` to be assigned to the `CComVariant` object. The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `fltSrc`  
 [in] Die **Float** zugewiesen, die `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_R4`.  
  
 `dblSrc`  
 [in] Die **doppelte** zugewiesen, die `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_R8`.  
  
 `cySrc`  
 [in] Die **CY** zugewiesen, die `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt `VT_CY`.  
  
 `pSrc`  
 [in] Die `IDispatch` oder **IUnknown** Zeiger zugewiesen, der `CComVariant` Objekt. `AddRef`wird für den Schnittstellenzeiger aufgerufen werden. Der Typ, der die `CComVariant` Objekt **VT_DISPATCH** oder **VT_UNKNOWN**bzw..  
  
 Oder, und **SAFEARRAY** Zeiger zugewiesen, der `CComVariant` Objekt. Eine Kopie der **SAFEARRAY** befindet sich in der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt ist eine Kombination aus den ursprünglichen Typ des wird die **SAFEARRAY** und **VT_ARRAY**.  
  
 `cSrc`  
 [in] Das Zeichen zugewiesen werden die `CComVariant` Objekt. Der Typ, der die `CComVariant` Objekt **VT_I1**.  
  
##  <a name="operator_eq_eq"></a>CComVariant ==  
 Gibt an, ob die `CComVariant` Objekt gleich dem angegebenen **VARIANT**.  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **true** Wenn den Wert und Typ des *VarSrc* gleich dem Wert und Typ, bzw. die `CComVariant` Objekt. Andernfalls **false**. Der Operator verwendet Standardgebietsschema des Benutzers, um den Vergleich durchzuführen.  
  
 Der Operator vergleicht nur den Wert des Varianten-Typen. Es vergleicht Zeichenfolgen, Ganzzahlen und Gleitkomma Punkt jedoch keine Arrays oder Datensätze.  
  
##  <a name="operator_neq"></a>CComVariant! =  
 Gibt an, ob die `CComVariant` Objekt entspricht nicht dem angegebenen **VARIANT**.  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **true** Wenn den Wert oder die Art der *VarSrc* entspricht nicht dem Wert oder Typ bzw. die `CComVariant` Objekt. Andernfalls **false**. Der Operator verwendet Standardgebietsschema des Benutzers, um den Vergleich durchzuführen.  
  
 Der Operator vergleicht nur den Wert des Varianten-Typen. Es vergleicht Zeichenfolgen, Ganzzahlen und Gleitkomma Punkt jedoch keine Arrays oder Datensätze.  
  
##  <a name="operator_lt"></a>CComVariant&lt;  
 Gibt an, ob die `CComVariant` Objekt ist kleiner als der angegebene **VARIANT**.  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **true** Wenn der Wert der `CComVariant` Objekt ist kleiner als der Wert der *VarSrc*. Andernfalls **false**. Der Operator verwendet Standardgebietsschema des Benutzers, um den Vergleich durchzuführen.  
  
##  <a name="operator_gt"></a>CComVariant&gt;  
 Gibt an, ob die `CComVariant` -Objekt ist größer als der angegebene **VARIANT**.  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **true** Wenn der Wert der `CComVariant` -Objekt ist größer als der Wert der *VarSrc*. Andernfalls **false**. Der Operator verwendet Standardgebietsschema des Benutzers, um den Vergleich durchzuführen.  
  
##  <a name="readfromstream"></a>CComVariant::ReadFromStream  
 Legt den zugrunde liegenden **VARIANT** an der **VARIANT** im angegebenen Stream enthalten.  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle für den Stream, der Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **ReadToStream** erfordert einen vorherigen Aufruf [WriteToStream](#writetostream).  
  
##  <a name="setbyref"></a>CComVariant::SetByRef  
 Initialisiert die `CComVariant` -Objekt und legt die **vt** Element **VT_BYREF**.  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des **VARIANT**, z. B. `BSTR`, `int`, oder `char`.  
  
 *pT*  
 Der Zeiger zur Initialisierung der `CComVariant` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `SetByRef`Eine Funktionsvorlage, die initialisiert die `CComVariant` Objekt mit dem Mauszeiger *pT* und legt die **vt** Element **VT_BYREF**. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Utilities&#76;](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>CComVariant:: WriteToStream  
 Speichert die zugrunde liegende **VARIANT** in einen Stream.  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle in einem Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
