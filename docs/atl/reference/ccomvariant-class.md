---
title: CComVariant Klasse | Microsoft Docs
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67e5aeee2aaa96b143962beb0790e3854ff7de01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomvariant-class"></a>CComVariant-Klasse
Diese Klasse dient als Wrapper für die `VARIANT` Typ, einen Member, der angibt, der Typ der gespeicherten Daten bereitstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|Der Konstruktor.|  
|[CComVariant:: ~ CComVariant](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|Fügt eine **VARIANT** auf die `CComVariant` Objekt.|  
|[CComVariant::ChangeType](#changetype)|Konvertiert die `CComVariant` Objekt in einen neuen Typ.|  
|[CComVariant::Clear](#clear)|Löscht die `CComVariant` Objekt.|  
|[CComVariant::Copy](#copy)|Kopiert ein **VARIANT** auf die `CComVariant` Objekt.|  
|[CComVariant::CopyTo](#copyto)|Kopiert den Inhalt der `CComVariant` Objekt.|  
|[CComVariant::Detach](#detach)|Trennt den zugrunde liegenden **VARIANT** aus der `CComVariant` Objekt.|  
|[CComVariant::GetSize](#getsize)|Gibt die Größe in Anzahl von Bytes des Inhalts der `CComVariant` Objekt.|  
|[CComVariant::ReadFromStream](#readfromstream)|Lädt eine **VARIANT** aus einem Stream.|  
|[CComVariant::SetByRef](#setbyref)|Initialisiert die `CComVariant` -Objekt und stellt die **vt** Element **VT_BYREF**.|  
|[CComVariant:: WriteToStream](#writetostream)|Speichert die zugrunde liegende **VARIANT** in einen Stream.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|||  
|-|-|  
|[CComVariant <](#operator_lt)|Gibt an, ob die `CComVariant` -Objekts kleiner ist als das angegebene **VARIANT**.|  
|[CComVariant >](#operator_gt)|Gibt an, ob die `CComVariant` -Quellobjekt ist größer als der angegebene **VARIANT**.|  
|[Operator! =](#operator_neq)|Gibt an, ob die `CComVariant` Objekt entspricht nicht dem angegebenen **VARIANT**.|  
|[Operator =](#operator_eq)|Weist einen Wert, der `CComVariant` Objekt.|  
|[Operator ==](#operator_eq_eq)|Gibt an, ob die `CComVariant` Objekt gleich dem angegebenen **VARIANT**.|  
  
## <a name="remarks"></a>Hinweise  
 `CComVariant`Dient als Wrapper für die `VARIANT and VARIANTARG` -Typ, der besteht aus einer Union "und" ein Element, das den Typ der in der Union gespeicherten Daten angibt. **VARIANT**s dienen im Allgemeinen in Automation.  
  
 `CComVariant`leitet sich von der **VARIANT** geben, damit es sein kann überall verwendet eine **VARIANT** kann verwendet werden. Z. B. können Sie die **V_VT** Makro, um den Typ des zu extrahieren einer `CComVariant` oder Sie können den Zugriff auf die **vt** Member direkt wie können Sie eine **VARIANT**.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  
  
##  <a name="attach"></a>CComVariant::Attach  
 Sicher löscht den aktuellen Inhalt der der `CComVariant` Objekt, das kopiert den Inhalt des `pSrc` in dieses Objekt dann legt der variant-Typ der `pSrc` auf `VT_EMPTY`.  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `pSrc`  
 [in] Verweist auf die [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) an das Objekt angefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Daten von reservierten `pSrc` wird zum Übertragen der `CComVariant` Objekt.  
  
##  <a name="ccomvariant"></a>CComVariant::CComVariant  
 Jeder Konstruktor behandelt die sichere Initialisierung der `CComVariant` Objekt durch Aufrufen der `VariantInit` Win32-Funktion oder durch Festlegen des Objekts Wert und Typ gemäß den Parametern übergeben.  
  
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
 [in] Die Zeichenfolge, die zur Initialisierung der `CComVariant` Objekt. Sie können eine NULL-terminierte Breite (Unicode-) Zeichen Zeichenfolge übergeben der **LPCOLESTR** Version für den Konstruktor oder eine ANSI-Zeichenfolge, um die `LPCSTR` Version. In beiden Fällen wird die Zeichenfolge in einen Unicode konvertiert `BSTR` mit reserviert **SysAllocString**. Der Typ des der `CComVariant` wird `VT_BSTR`.  
  
 `bSrc`  
 [in] Die `bool` zur Initialisierung der `CComVariant` Objekt. Die `bool` Argument konvertiert eine **VARIANT_BOOL** vor dem Speichern. Der Typ des der `CComVariant` wird `VT_BOOL`.  
  
 `nSrc`  
 [in] Die `int`, **BYTE**, **kurze**, **lange**, **LONGLONG**, **ULONGLONG**, **kurz ohne Vorzeichen**, `unsigned long`, oder `unsigned int` zur Initialisierung der `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, oder **VT_UI4**zugeordnet.  
  
 `vtSrc`  
 [in] Der Typ der Variante. Wenn der erste Parameter ist `int`, gültige Typen sind `VT_I4` und **VT_INT**. Wenn der erste Parameter ist **lange**, gültige Typen sind `VT_I4` und `VT_ERROR`. Wenn der erste Parameter ist **doppelte**, gültige Typen sind `VT_R8` und `VT_DATE`. Wenn der erste Parameter ist `unsigned int`, gültige Typen sind **VT_UI4** und **VT_UINT**.  
  
 `fltSrc`  
 [in] Die **"float"** zur Initialisierung der `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_R4`.  
  
 `dblSrc`  
 [in] Die **doppelte** zur Initialisierung der `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_R8`.  
  
 `cySrc`  
 [in] Die **CY** zur Initialisierung der `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_CY`.  
  
 `pSrc`  
 [in] Die `IDispatch` oder **IUnknown** Zeiger zur Initialisierung der `CComVariant` Objekt. `AddRef`wird für den Schnittstellenzeiger aufgerufen werden. Der Typ des der `CComVariant` wird **VT_DISPATCH** oder **VT_UNKNOWN**zugeordnet.  
  
 Or **SAFERRAY** Zeiger zur Initialisierung der `CComVariant` Objekt. Eine Kopie der **SAFEARRAY** befindet sich in der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt ist eine Kombination aus den ursprünglichen Typ des wird die **SAFEARRAY** und **VT_ARRAY**.  
  
 `cSrc`  
 [in] Die `char` zur Initialisierung der `CComVariant` Objekt. Der Typ des der `CComVariant` wird **VT_I1**.  
  
 `bstrSrc`  
 [in] BSTR verwendet wird, zum Initialisieren der `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_BSTR`.  
  
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
 Wenn Sie einen Wert, für übergeben `pSrc`, `ChangeType` verwenden werden **VARIANT** als Quelle für die Konvertierung. Andernfalls die `CComVariant` Objekt ist die Quelle wird.  
  
##  <a name="clear"></a>CComVariant::Clear  
 Löscht die `CComVariant` Objekt durch Aufrufen der `VariantClear` Win32-Funktion.  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Ruft der Destruktor automatisch **löschen**.  
  
##  <a name="copy"></a>CComVariant::Copy  
 Gibt die `CComVariant` Objekt, und weist diesem dann eine Kopie des angegebenen **VARIANT**.  
  
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
 Beachten Sie, dass der Inhalt der `VARIANT` verwiesen wird, indem Sie `pDest` wird automatisch gelöscht werden, bevor Sie den Wert und Typ des aufrufenden zugewiesen wird **CComVariant** Objekt.  
  
##  <a name="getsize"></a>CComVariant::GetSize  
 Für einfache fester Größe `VARIANT`s, diese Methode gibt die `sizeof` plus dem zugrunde liegenden Datentyp `sizeof(VARTYPE)`.  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe in Bytes, der dem aktuellen Inhalt der `CComVariant` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `VARIANT` enthält einen Schnittstellenzeiger `GetSize` fragt nach `IPersistStream` oder `IPersistStreamInit`. Bei einer erfolgreichen der Rückgabewert die niedrige 32 Bits des Werts zurückgegebenes `GetSizeMax` plus dem `sizeof` eine `CLSID` und `sizeof(VARTYPE)`. Ist der Schnittstellenzeiger `NULL`, `GetSize` gibt die `sizeof` eine `CLSID` plus `sizeof(VARTYPE)`. Wenn die Gesamtgröße überschreitet `ULONG_MAX`, `GetSize` gibt `sizeof(VARTYPE)` gibt einen Fehler an.  
  
 In allen anderen Fällen, eine temporäre `VARIANT` des Typs `VT_BSTR` wird aus dem aktuellen umgewandelt `VARIANT`. Die Länge dieses `BSTR` wird berechnet als die Größe der die Länge der Zeichenfolge plus die Länge der Zeichenfolge selbst sowie die Größe des Null-Zeichens plus `sizeof(VARTYPE)`. Wenn die `VARIANT` kann nicht umgewandelt werden, um eine `VARIANT` des Typs `VT_BSTR`, `GetSize` gibt `sizeof(VARTYPE)`.  
  
 Die von dieser Methode zurückgegebene Größe entspricht die Anzahl der Bytes, die von verwendeten [CComVariant:: WriteToStream](#writetostream) erfolgreich ausgelastet.  
  
##  <a name="operator_eq"></a>CComVariant =  
 Weist einen Wert und den entsprechenden Typ, der `CComVariant` Objekt.  
  
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
 [in] Die `CComVariant` oder [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) zuzuweisenden das `CComVariant` Objekt. Der Inhalt der Quelle Variante werden an das Ziel ohne Konvertierung kopiert.  
  
 `bstrSrc`  
 [in] BSTR zuzuweisenden das `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_BSTR`.  
  
 `lpszSrc`  
 [in] Die Zeichenfolge, die zugewiesen werden, die `CComVariant` Objekt. Sie können eine NULL-terminierte Breite (Unicode-) Zeichen Zeichenfolge übergeben der **LPCOLESTR** Version des Operators oder eine ANSI-Zeichenfolge, um die `LPCSTR` Version. In beiden Fällen wird die Zeichenfolge in einen Unicode konvertiert `BSTR` mit reserviert **SysAllocString**. Der Typ des der `CComVariant` wird `VT_BSTR`.  
  
 `bSrc`  
 [in] Die `bool` zuzuweisenden das `CComVariant` Objekt. Die `bool` Argument konvertiert eine **VARIANT_BOOL** vor dem Speichern. Der Typ des der `CComVariant` wird `VT_BOOL`.  
  
 `nSrc`  
 [in] Die `int`, **BYTE**, **kurze**, **lange**, **LONGLONG**, **ULONGLONG**, **kurz ohne Vorzeichen**, `unsigned long`, oder `unsigned int` zuzuweisenden das `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, oder **VT_UI4**zugeordnet.  
  
 `fltSrc`  
 [in] Die **"float"** zuzuweisenden das `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_R4`.  
  
 `dblSrc`  
 [in] Die **doppelte** zuzuweisenden das `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_R8`.  
  
 `cySrc`  
 [in] Die **CY** zuzuweisenden das `CComVariant` Objekt. Der Typ des der `CComVariant` wird `VT_CY`.  
  
 `pSrc`  
 [in] Die `IDispatch` oder **IUnknown** Zeiger zuzuweisenden das `CComVariant` Objekt. `AddRef`wird für den Schnittstellenzeiger aufgerufen werden. Der Typ des der `CComVariant` wird **VT_DISPATCH** oder **VT_UNKNOWN**zugeordnet.  
  
 Oder, eine **SAFEARRAY** Zeiger zuzuweisenden das `CComVariant` Objekt. Eine Kopie der **SAFEARRAY** befindet sich in der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt ist eine Kombination aus den ursprünglichen Typ des wird die **SAFEARRAY** und **VT_ARRAY**.  
  
 `cSrc`  
 [in] Char zuzuweisenden das `CComVariant` Objekt. Der Typ des der `CComVariant` wird **VT_I1**.  
  
##  <a name="operator_eq_eq"></a>CComVariant ==  
 Gibt an, ob die `CComVariant` Objekt gleich dem angegebenen **VARIANT**.  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **"true"** Wenn der Wert und Typ des *VarSrc* gleich dem Wert und Typ, bzw. die `CComVariant` Objekt. andernfalls **"false"**. Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.  
  
 Der Operator vergleicht nur den Wert der Varianten-Typen. Es vergleicht Zeichenfolgen, Ganzzahlen und Gleitkomma Punkte, jedoch keine Arrays oder Datensätze.  
  
##  <a name="operator_neq"></a>CComVariant! =  
 Gibt an, ob die `CComVariant` Objekt entspricht nicht dem angegebenen **VARIANT**.  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **"true"** Wenn der Wert oder der Typ des *VarSrc* stimmt nicht mit dem Wert oder einen Typ, bzw. die `CComVariant` Objekt. andernfalls **"false"**. Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.  
  
 Der Operator vergleicht nur den Wert der Varianten-Typen. Es vergleicht Zeichenfolgen, Ganzzahlen und Gleitkomma Punkte, jedoch keine Arrays oder Datensätze.  
  
##  <a name="operator_lt"></a>CComVariant&lt;  
 Gibt an, ob die `CComVariant` -Objekts kleiner ist als das angegebene **VARIANT**.  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **"true"** Wenn der Wert der `CComVariant` -Objekts kleiner ist als der Wert der *VarSrc*. andernfalls **"false"**. Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.  
  
##  <a name="operator_gt"></a>CComVariant&gt;  
 Gibt an, ob die `CComVariant` -Quellobjekt ist größer als der angegebene **VARIANT**.  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt **"true"** Wenn der Wert der `CComVariant` -Quellobjekt ist größer als der Wert der *VarSrc*. andernfalls **"false"**. Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.  
  
##  <a name="readfromstream"></a>CComVariant::ReadFromStream  
 Legt den zugrunde liegenden **VARIANT** auf die **VARIANT** enthalten, die im angegebenen Stream.  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle auf dem der Stream, der die Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **ReadToStream** erfordert einen vorherigen Aufruf von [WriteToStream](#writetostream).  
  
##  <a name="setbyref"></a>CComVariant::SetByRef  
 Initialisiert die `CComVariant` -Objekt und stellt die **vt** Element **VT_BYREF**.  
  
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
 `SetByRef`Eine Funktionsvorlage, die initialisiert wird die `CComVariant` Objekt mit dem Mauszeiger *pT* und legt die **vt** Member **VT_BYREF**. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>CComVariant:: WriteToStream  
 Speichert die zugrunde liegende **VARIANT** in einen Stream.  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle für einen Datenstrom.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)