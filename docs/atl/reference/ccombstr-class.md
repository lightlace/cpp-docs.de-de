---
title: CComBSTR-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 604e3b9841ab628343a48e72612d2e50e85913f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccombstr-class"></a>CComBSTR-Klasse
Diese Klasse ist ein Wrapper für `BSTR`s.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComBSTR
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](#ccombstr)|Der Konstruktor.|  
|[CComBSTR:: ~ CComBSTR](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::Append](#append)|Fügt eine Zeichenfolge, die auf `m_str`.|  
|[CComBSTR::AppendBSTR](#appendbstr)|Fügt eine `BSTR` auf `m_str`.|  
|[CComBSTR::AppendBytes](#appendbytes)|Fügt eine angegebene Anzahl von Bytes, die `m_str`.|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Erstellt eine `BSTR` vom ersten Zeichen der einzelnen Elemente im Safearray und fügt es der `CComBSTR` Objekt.|  
|[CComBSTR::AssignBSTR](#assignbstr)|Weist eine `BSTR` auf `m_str`.|  
|[CComBSTR::Attach](#attach)|Fügt eine `BSTR` auf die `CComBSTR` Objekt.|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|Erstellt eine nullbasierte eindimensionale Safearray, wobei jedes Element des Arrays ist ein Zeichen aus dem `CComBSTR` Objekt.|  
|[CComBSTR::ByteLength](#bytelength)|Gibt die Länge des `m_str` in Bytes.|  
|[CComBSTR::Copy](#copy)|Gibt eine Kopie des `m_str`.|  
|[CComBSTR::CopyTo](#copyto)|Gibt eine Kopie des `m_str` über eine **[Out]** Parameter|  
|[CComBSTR::Detach](#detach)|Trennt `m_str` aus der `CComBSTR` Objekt.|  
|[CComBSTR::Empty](#empty)|Freigegeben `m_str`.|  
|[CComBSTR::Length](#length)|Gibt die Länge des `m_str`.|  
|[CComBSTR::LoadString](#loadstring)|Lädt eine Zeichenfolgenressource.|  
|[CComBSTR::ReadFromStream](#readfromstream)|Lädt eine `BSTR` Objekt aus einem Stream.|  
|[CComBSTR::ToLower](#tolower)|Konvertiert die Zeichenfolge in Kleinbuchstaben.|  
|[CComBSTR::ToUpper](#toupper)|Konvertiert die Zeichenfolge in Großbuchstaben konvertiert wurden.|  
|[CComBSTR::WriteToStream](#writetostream)|Speichert `m_str` in einen Stream.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](#operator_bstr)|Wandelt eine `CComBSTR` -Objekt an eine `BSTR`.|  
|[CComBSTR::operator!](#operator_not)|Gibt `true` oder `false`, je nachdem, ob `m_str`ist `NULL`.|  
|[CComBSTR::operator! =](#operator_neq)|Vergleicht eine `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator &](#operator_amp)|Gibt die Adresse des `m_str`.|  
|[CComBSTR::operator +=](#operator_add_eq)|Fügt eine `CComBSTR` auf das Objekt.|  
|[CComBSTR::operator <](#operator_lt)|Vergleicht eine `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator =](#operator_eq)|Ein Wert zugewiesen `m_str`.|  
|[CComBSTR::operator ==](#operator_eq_eq)|Vergleicht eine `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator >](#operator_gt)|Vergleicht eine `CComBSTR` mit einer Zeichenfolge.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|Enthält die `BSTR` zugeordneten der `CComBSTR` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CComBSTR` Klasse ist ein Wrapper für `BSTR`s aus, die Längenpräfix Zeichenfolgen sind. Die Länge wird als eine ganze Zahl an der Speicheradresse, die die Daten in der Zeichenfolge vor gespeichert.  
  
 Ein [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) ist Null-terminierte nach der letzten Zeichen gezählt, jedoch kann auch in die Zeichenfolge eingebettete Null-Zeichen enthalten. Die Länge der Zeichenfolge wird durch die Anzahl der Zeichen, nicht der ersten Null-Zeichen bestimmt.  
  
> [!NOTE]
>  Die `CComBSTR` -Klasse stellt eine Anzahl von Elementen (Konstruktoren, Zuweisungsoperatoren und Vergleichsoperatoren), die entweder den ANSI- oder Unicode-Zeichenfolgen als Argumente annehmen. Die ANSI-Versionen dieser Funktionen sind weniger effizient als ihre Unicode-Äquivalente, da temporäre Unicode-Zeichenfolgen intern häufig erstellt werden. Aus Effizienzgründen verwenden Sie möglichst die Unicode-Versionen.  
  
> [!NOTE]
>  Aufgrund der verbesserten Suchverhalten in Visual Studio .NET implementiert, wie z. B. code `bstr = L"String2" + bstr;`, die in früheren Versionen kompiliert haben möglicherweise sollte stattdessen als implementiert `bstr = CStringW(L"String2") + bstr`.  
  
 Eine Liste der Warnhinweise Verwendung `CComBSTR`, finden Sie unter [Programmieren mit CComBSTR](../../atl/programming-with-ccombstr-atl.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="append"></a>CComBSTR::Append  
 Fügt eine `lpsz` oder `BSTR` Mitglied `bstrSrc` auf [M_str](#m_str).  
  
```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bstrSrc`  
 [in] Ein `CComBSTR` anzufügende Objekt.  
  
 *CH*  
 [in] Ein Zeichen, angefügt werden soll.  
  
 `lpsz`  
 [in] Eine NULL-terminierte Zeichenfolge angefügt. Sie können eine Unicode-Zeichenfolge über übergeben der **LPCOLESTR** Überlastung oder einer ANSI-Zeichenfolge über die `LPCSTR` Version.  
  
 `nLen`  
 [in] Die Anzahl von Zeichen aus `lpsz` , angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein Standard, der `HRESULT` Fehlerwert.  
  
### <a name="remarks"></a>Hinweise  
 Eine ANSI-Zeichenfolge werden in Unicode konvertiert werden, bevor Sie angefügt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="appendbstr"></a>CComBSTR::AppendBSTR  
 Fügt das angegebene `BSTR` auf [M_str](#m_str).  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Ein `BSTR` , angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein Standard, der `HRESULT` Fehlerwert.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie eine gewöhnliche Breitzeichen-Zeichenfolge darf nicht an diese Methode werden. Der Compiler kann nicht den Fehler abfangen und zur Laufzeit Fehler auftreten, werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="appendbytes"></a>CComBSTR::AppendBytes  
 Fügt die angegebene Anzahl von Bytes, die [M_str](#m_str) ohne Konvertierung.  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 [in] Ein Zeiger auf ein Array von Bytes, die angefügt werden soll.  
  
 `p`  
 [in] Die Anzahl der Bytes, die angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein Standard, der `HRESULT` Fehlerwert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="arraytobstr"></a>CComBSTR::ArrayToBSTR  
 Freigegeben vorhandene Zeichenfolgen frei, die der `CComBSTR` -Objekt, und erstellt dann eine `BSTR` vom ersten Zeichen der einzelnen Elemente im Safearray und fügt es der `CComBSTR` Objekt.  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pSrc`  
 [in] Die Safearray mit Elementen verwendet, um die Zeichenfolge zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein Standard, der `HRESULT` Fehlerwert.  
  
##  <a name="assignbstr"></a>CComBSTR::AssignBSTR  
 Weist eine `BSTR` auf [M_str](#m_str).  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bstrSrc`  
 [in] Ein `BSTR` aktuellen zuzuweisende `CComBSTR` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein Standard, der `HRESULT` Fehlerwert.  
  
##  <a name="attach"></a>CComBSTR::Attach  
 Fügt eine `BSTR` auf die `CComBSTR` Objekt durch Festlegen der [M_str](#m_str) Element *Src*.  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 [in] Die `BSTR` , an das Objekt anzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie eine gewöhnliche Breitzeichen-Zeichenfolge darf nicht an diese Methode werden. Der Compiler kann nicht den Fehler abfangen und zur Laufzeit Fehler auftreten, werden.  
  
> [!NOTE]
>  Wenn diese Methode implementiert `m_str` nicht **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="bstrtoarray"></a>CComBSTR::BSTRToArray  
 Erstellt eine nullbasierte eindimensionale Safearray, wobei jedes Element des Arrays ist ein Zeichen aus dem `CComBSTR` Objekt.  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ppArray`  
 [out] Der Zeiger auf die SafeArray-Elements dar, das die Ergebnisse der Funktion enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder ein Standard, der `HRESULT` Fehlerwert.  
  
##  <a name="bytelength"></a>CComBSTR::ByteLength  
 Gibt die Anzahl der Bytes im `m_str`, ausgenommen das abschließende Nullzeichen.  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der [M_str](#m_str) Elements in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Gibt 0 zurück, wenn `m_str` ist **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="ccombstr"></a>CComBSTR::CComBSTR  
 Der Konstruktor. Der Standardkonstruktor legt die [M_str](#m_str) Element **NULL**.  
  
```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);  
CComBSTR(REFGUID  guid);  
CComBSTR(int nSize);  
CComBSTR(int nSize, LPCOLESTR sz);  
CComBSTR(int nSize, LPCSTR sz);  
CComBSTR(LPCOLESTR pSrc);  
CComBSTR(LPCSTR pSrc);  
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `nSize`  
 [in] Die Anzahl der zu kopierenden Zeichen aus `sz` oder die ursprüngliche Größe in Zeichen für `CComBSTR`.  
  
 `sz`  
 [in] Eine zu kopierende Zeichenfolge. Die Unicodeversion gibt ein **LPCOLESTR**; die ANSI-Version gibt ein `LPCSTR`.  
  
 `pSrc`  
 [in] Eine zu kopierende Zeichenfolge. Die Unicodeversion gibt ein **LPCOLESTR**; die ANSI-Version gibt ein `LPCSTR`.  
  
 *src*  
 [in] Ein `CComBSTR`-Objekt.  
  
 `guid`  
 [in] Ein Verweis auf eine **GUID** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Der Kopierkonstruktor legt `m_str` auf eine Kopie der `BSTR` Mitglied *Src*. Die **REFGUID** Konstruktor konvertiert die **GUID** in eine Zeichenfolge mit **StringFromGUID2** und speichert das Ergebnis.  
  
 Die anderen Konstruktoren legen `m_str` auf eine Kopie der angegebenen Zeichenfolge fest. Wenn Sie einen Wert für `nSize` übergeben, werden nur `nSize`-Zeichen kopiert, gefolgt von einem abschließenden NULL-Zeichen.  
  
 `CComBSTR` unterstützt die move-Semantik. Können Sie die Move-Konstruktor (des Konstruktors, der einen Rvalue-Verweis akzeptiert ( `&&`) um ein neues Objekt zu erstellen, die gleichen zugrunde liegenden Daten der alten als Argument, ohne den Aufwand für das Objekt kopieren im übergebenen Objekts verwendet.  
  
 Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]  
  
##  <a name="dtor"></a>CComBSTR:: ~ CComBSTR  
 Der Destruktor.  
  
```
~CComBSTR();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.  
  
##  <a name="copy"></a>CComBSTR::Copy  
 Zum Belegen und gibt eine Kopie des `m_str`.  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der [M_str](#m_str) Member. Wenn `m_str` ist **NULL**, gibt **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="copyto"></a>CComBSTR::CopyTo  
 Zum Belegen und gibt eine Kopie des [M_str](#m_str) über den Parameter.  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pbstr*  
 [out] Die Adresse von einem `BSTR` in dem die Zeichenfolge, die von dieser Methode belegten zurückgegeben.  
  
 `pvarDest`  
 [out] Die Adresse von einem **VARIANT** in dem die Zeichenfolge, die von dieser Methode belegten zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` Wert, der den Erfolg oder Misserfolg der Kopie.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufrufen dieser Methode die **VARIANT** verweist `pvarDest` vom Typ `VT_BSTR`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="detach"></a>CComBSTR::Detach  
 Trennt [M_str](#m_str) aus der `CComBSTR` -Objekt und stellt `m_str` auf **NULL**.  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `BSTR` zugeordneten der `CComBSTR` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]  
  
##  <a name="empty"></a>CComBSTR::Empty  
 Gibt die [M_str](#m_str) Member.  
  
```
void Empty() throw();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]  
  
##  <a name="length"></a>CComBSTR::Length  
 Gibt die Anzahl der Zeichen in `m_str`, ausgenommen das abschließende Nullzeichen.  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der [M_str](#m_str) Member.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="loadstring"></a>CComBSTR::LoadString  
 Lädt eine Zeichenfolgenressource gemäß `nID` und speichert sie in dieses Objekt.  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>Parameter  
 Finden Sie unter [LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** gibt zurück, wenn die Zeichenfolge erfolgreich geladen wurde; andernfalls ist, **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion lädt die Ressource aus dem Modul identifiziert, die von Ihnen über die `hInst` Parameter. Die zweite Funktion lädt die Ressource aus der zugeordneten Ressourcenmodul der [CComModule](../../atl/reference/ccommodule-class.md)-abgeleitetes Objekt in diesem Projekt verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="m_str"></a>CComBSTR::m_str  
 Enthält die `BSTR` zugeordneten der `CComBSTR` Objekt.  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="operator_bstr"></a>CComBSTR::operator BSTR  
 Wandelt eine `CComBSTR` -Objekt an eine `BSTR`.  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht Ihnen das übergeben `CComBSTR` Objekte an Funktionen mit **[in] BSTR** Parameter.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CComBSTR::m_str](#m_str).  
  
##  <a name="operator_not"></a>CComBSTR::operator!  
 Überprüft, ob `BSTR` Zeichenfolge ist NULL.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die [M_str](#m_str) angehört **NULL**ist, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator überprüft nur für einen NULL-Wert, nicht für eine leere Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="operator_neq"></a>CComBSTR::operator! =  
 Gibt das logische Gegenteil dieses [Operator ==](#operator_eq_eq).  
  
```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bstrSrc`  
 [in] Ein `CComBSTR`-Objekt.  
  
 `pszSrc`  
 [in] Eine NULL-terminierte Zeichenfolge.  
  
 `nNull`  
 [in] Muss **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das Element verglichenen nicht gleich der `CComBSTR` Objekt; andernfalls wird zurückgegeben **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 `CComBSTR`s im Kontext des Benutzers Standardgebietsschema Textbefehl verglichen werden. Der endgültige Vergleichsoperator vergleicht nur für die enthaltene Zeichenfolge **NULL**.  
  
##  <a name="operator_amp"></a>CComBSTR::operator&amp;  
 Gibt die Adresse des dem `BSTR` gespeichert, der [M_str](#m_str) Member.  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 `CComBstr operator &`verfügt über eine Assertion mit einer spezielle es zum Identifizieren von Arbeitsspeicherverlusten zugeordnet ist. Das Programm wird beim Bestätigen der `m_str` Member wird initialisiert. Diese Assertion wurde erstellt, um die Identifizierung von Situationen, in denen Programmierer verwendet, die `& operator` einen neuen Wert zuzuweisen `m_str` Member ohne Freigabe der ersten Zuweisung `m_str`. Wenn `m_str` gleich NULL ist, das Programm wird davon ausgegangen, M_str noch zugeordnet wurde nicht. In diesem Fall wird das Programm nicht bestätigen.  
  
 Diese Assertion ist standardmäßig nicht aktiviert. Definieren Sie `ATL_CCOMBSTR_ADDRESS_OF_ASSERT` So aktivieren Sie diese Assertion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]  
  
##  <a name="operator_add_eq"></a>CComBSTR::operator +=  
 Fügt eine Zeichenfolge, die die `CComBSTR` Objekt.  
  
```
CComBSTR& operator+= (const CComBSTR& bstrSrc);  
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `bstrSrc`  
 [in] Ein `CComBSTR` anzufügende Objekt.  
  
 `pszSrc`  
 [in] Eine NULL-terminierte Zeichenfolge angefügt.  
  
### <a name="remarks"></a>Hinweise  
 `CComBSTR`s im Kontext des Benutzers Standardgebietsschema Textbefehl verglichen werden. Die **LPCOLESTR** Vergleich erfolgt mit `memcmp` auf die unformatierten Daten in jeder Zeichenfolge. Die `LPCSTR` Vergleich erfolgt auf die gleiche Weise, sobald eine temporäre Unicode Kopie von `pszSrc` erstellt wurde. Der endgültige Vergleichsoperator vergleicht nur für die enthaltene Zeichenfolge **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]  
  
##  <a name="operator_lt"></a>CComBSTR::operator&lt;  
 Vergleicht eine `CComBSTR` mit einer Zeichenfolge.  
  
```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die verglichenen Element ist kleiner als das `CComBSTR` Objekt; andernfalls wird zurückgegeben **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich erfolgt mithilfe von Standard-Gebietsschema des Benutzers.  
  
##  <a name="operator_eq"></a>CComBSTR::operator =  
 Legt die [M_str](#m_str) Element um eine Kopie des `pSrc` oder auf eine Kopie der `BSTR` Mitglied *Src*. Verschiebt den bewegungszuweisungsoperator `src` ohne es zu kopieren.   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>Hinweise  
 Die `pSrc` Parameter gibt an, entweder eine **LPCOLESTR** für Unicode-Versionen oder `LPCSTR` für ANSI-Versionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CComBSTR::Copy](#copy).  
  
##  <a name="operator_eq_eq"></a>CComBSTR::operator ==  
 Vergleicht eine `CComBSTR` mit einer Zeichenfolge. `CComBSTR`s im Kontext des Benutzers Standardgebietsschema Textbefehl verglichen werden.  
  
```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bstrSrc`  
 [in] Ein `CComBSTR`-Objekt.  
  
 `pszSrc`  
 [in] Eine NULL-terminierte Zeichenfolge.  
  
 `nNull`  
 [in] Muss **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das Element verglichen wird, entspricht die `CComBSTR` Objekt; andernfalls wird zurückgegeben **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Der endgültige Vergleichsoperator vergleicht nur für die enthaltene Zeichenfolge **NULL**.  
  
##  <a name="operator_gt"></a>CComBSTR::operator&gt;  
 Vergleicht eine `CComBSTR` mit einer Zeichenfolge.  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das Element verglichenen größer als die `CComBSTR` Objekt; andernfalls wird zurückgegeben **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich erfolgt mithilfe von Standard-Gebietsschema des Benutzers.  
  
##  <a name="readfromstream"></a>CComBSTR::ReadFromStream  
 Legt die [M_str](#m_str) Member der `BSTR` enthalten, die im angegebenen Stream.  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle auf dem der Stream, der die Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **ReadToStream** erfordert den Inhalt des Streams an der aktuellen Position für die Kompatibilität mit dem Datenformat geschrieben, die durch einen Aufruf von [WriteToStream](#writetostream).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="tolower"></a>CComBSTR::ToLower  
 Konvertiert die darin enthaltenen Zeichenfolge in Kleinbuchstaben.  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter **CharLowerBuff** für Weitere Informationen dazu, wie die Konvertierung ausgeführt wird.  
  
##  <a name="toupper"></a>CComBSTR::ToUpper  
 Konvertiert die darin enthaltenen Zeichenfolge in Großbuchstaben konvertiert wurden.  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter **CharUpperBuff** für Weitere Informationen dazu, wie die Konvertierung ausgeführt wird.  
  
##  <a name="writetostream"></a>CComBSTR::WriteToStream  
 Speichert die [M_str](#m_str) Element in einen Stream.  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle für einen Datenstrom.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Kann neu erstellt einen BSTR aus dem Inhalt der Stream unter Verwendung der [ReadFromStream](#readfromstream) Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md)
