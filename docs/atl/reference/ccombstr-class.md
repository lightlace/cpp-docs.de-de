---
title: CComBSTR-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComBSTR
- CComBSTR
- ATL.CComBSTR
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 21
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: e7b61a5826836e7d26a0d470631d7230f7b7be56
ms.lasthandoff: 02/24/2017

---
# <a name="ccombstr-class"></a>CComBSTR-Klasse
Diese Klasse ist ein Wrapper für `BSTR`s.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComBSTR
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](#ccombstr)|Der Konstruktor.|  
|[CComBSTR:: ~ CComBSTR](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::Append](#append)|Fügt eine Zeichenfolge, die `m_str`.|  
|[CComBSTR::AppendBSTR](#appendbstr)|Fügt eine `BSTR` auf `m_str`.|  
|[CComBSTR::AppendBytes](#appendbytes)|Fügt eine angegebene Anzahl an Bytes, die `m_str`.|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Erstellt eine `BSTR` vom ersten Zeichen der einzelnen Elemente im Safearray und fügt es der `CComBSTR` Objekt.|  
|[CComBSTR::AssignBSTR](#assignbstr)|Weist eine `BSTR` auf `m_str`.|  
|[CComBSTR::Attach](#attach)|Fügt eine `BSTR` an die `CComBSTR` Objekt.|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|Erstellt ein nullbasierte eindimensionale Safearray, wobei jedes Element des Arrays ist ein Zeichen aus der `CComBSTR` Objekt.|  
|[CComBSTR::ByteLength](#bytelength)|Gibt die Länge des `m_str` in Bytes.|  
|[CComBSTR::Copy](#copy)|Gibt eine Kopie des `m_str`.|  
|[CComBSTR::CopyTo](#copyto)|Gibt eine Kopie des `m_str` über eine **[Out]** Parameter|  
|[CComBSTR::Detach](#detach)|Trennt `m_str` aus der `CComBSTR` Objekt.|  
|[CComBSTR::Empty](#empty)|Frei `m_str`.|  
|[CComBSTR::Length](#length)|Gibt die Länge des `m_str`.|  
|[CComBSTR::LoadString](#loadstring)|Lädt eine Zeichenfolgenressource.|  
|[CComBSTR::ReadFromStream](#readfromstream)|Lädt ein `BSTR` Objekt aus einem Stream.|  
|[CComBSTR::ToLower](#tolower)|Konvertiert die Zeichenfolge in Kleinbuchstaben.|  
|[CComBSTR::ToUpper](#toupper)|Konvertiert die Zeichenfolge in Großbuchstaben.|  
|[CComBSTR::WriteToStream](#writetostream)|Speichert `m_str` in einen Stream.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](#operator_bstr)|Wandelt eine `CComBSTR` -Objekt an eine `BSTR`.|  
|[CComBSTR::operator!](#operator_not)|Gibt `true` oder `false`, je nachdem, ob `m_str`ist `NULL`.|  
|[CComBSTR::operator! =](#operator_neq)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator &](#operator_amp)|Gibt die Adresse des `m_str`.|  
|[CComBSTR::operator +=](#operator_add_eq)|Fügt eine `CComBSTR` auf das Objekt.|  
|[CComBSTR::operator](#operator_lt)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator =](#operator_eq)|Ein Wert zugewiesen `m_str`.|  
|[CComBSTR::operator ==](#operator_eq_eq)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator >](#operator_gt)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|Enthält die `BSTR` zugeordneten der `CComBSTR` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CComBSTR` ist ein Wrapper für `BSTR`s, die Längenpräfix Zeichenfolgen sind. Die Länge wird als eine ganze Zahl an der Speicheradresse vor den Daten in der Zeichenfolge gespeichert.  
  
 Ein [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) ist Null-terminierte nach dem letzten Zeichen gezählt, sondern kann auch in die Zeichenfolge eingebettete Null-Zeichen enthalten. Die Länge der Zeichenfolge wird durch die Anzahl der Zeichen, nicht der ersten Null-Zeichen bestimmt.  
  
> [!NOTE]
>  Die `CComBSTR` -Klasse stellt eine Anzahl von Elementen (Konstruktoren, Zuweisungsoperatoren und Vergleichsoperatoren), die entweder den ANSI- oder Unicode-Zeichenfolgen als Argumente annehmen. Die ANSI-Versionen dieser Funktionen sind weniger effizient als ihre Unicode-Äquivalente, da temporäre Unicode-Zeichenfolgen intern häufig erstellt werden. Aus Gründen der Effizienz verwenden Sie möglichst die Unicode-Versionen.  
  
> [!NOTE]
>  Aufgrund der verbesserten Suchverhalten in Visual Studio .NET implementiert, wie z. B. code `bstr = L"String2" + bstr;`, die in früheren Versionen kompiliert haben, kann stattdessen implementiert werden sollte als `bstr = CStringW(L"String2") + bstr`.  
  
 Eine Liste mit Vorsichtsmaßnahmen bei Verwendung `CComBSTR`, finden Sie unter [Programmieren mit CComBSTR](../../atl/programming-with-ccombstr-atl.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameappenda--ccombstrappend"></a><a name="append"></a>CComBSTR::Append  
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
 [in] Die Anzahl von Zeichen aus `lpsz` angefügt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder einen Standard `HRESULT` Fehlerwert.  
  
### <a name="remarks"></a>Hinweise  
 Eine ANSI-Zeichenfolge wird in Unicode konvertiert werden, bevor angefügt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#32;](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="a-nameappendbstra--ccombstrappendbstr"></a><a name="appendbstr"></a>CComBSTR::AppendBSTR  
 Fügt das angegebene `BSTR` auf [M_str](#m_str).  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Ein `BSTR` angefügt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder einen Standard `HRESULT` Fehlerwert.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie eine gewöhnliche Zeichenfolge nicht an diese Methode. Der Compiler kann nicht den Fehler abfangen und Laufzeit, der der Fehler auftreten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&33;](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="a-nameappendbytesa--ccombstrappendbytes"></a><a name="appendbytes"></a>CComBSTR::AppendBytes  
 Fügt die angegebene Anzahl von Bytes, die [M_str](#m_str) ohne Konvertierung.  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpsz`  
 [in] Ein Zeiger auf ein Array von Bytes, angefügt werden soll.  
  
 `p`  
 [in] Die Anzahl der Bytes, angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder einen Standard `HRESULT` Fehlerwert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#34;](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="a-namearraytobstra--ccombstrarraytobstr"></a><a name="arraytobstr"></a>CComBSTR::ArrayToBSTR  
 Frei vorhandene Zeichenfolgen frei, die der `CComBSTR` -Objekt, und erstellt dann eine `BSTR` vom ersten Zeichen der einzelnen Elemente im Safearray und fügt es der `CComBSTR` Objekt.  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pSrc`  
 [in] Safearray mit Elementen verwendet, um die Zeichenfolge zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder einen Standard `HRESULT` Fehlerwert.  
  
##  <a name="a-nameassignbstra--ccombstrassignbstr"></a><a name="assignbstr"></a>CComBSTR::AssignBSTR  
 Weist eine `BSTR` auf [M_str](#m_str).  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bstrSrc`  
 [in] Ein `BSTR` Zuweisen der aktuellen `CComBSTR` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder einen Standard `HRESULT` Fehlerwert.  
  
##  <a name="a-nameattacha--ccombstrattach"></a><a name="attach"></a>CComBSTR::Attach  
 Fügt eine `BSTR` an der `CComBSTR` Objekt durch Festlegen der [M_str](#m_str) Element *Src*.  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 [in] Die `BSTR` des Objekts an.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie eine gewöhnliche Zeichenfolge nicht an diese Methode. Der Compiler kann nicht den Fehler abfangen und Laufzeit, der der Fehler auftreten.  
  
> [!NOTE]
>  Diese Methode überprüft, wenn `m_str` nicht **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#35;](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="a-namebstrtoarraya--ccombstrbstrtoarray"></a><a name="bstrtoarray"></a>CComBSTR::BSTRToArray  
 Erstellt ein nullbasierte eindimensionale Safearray, wobei jedes Element des Arrays ist ein Zeichen aus der `CComBSTR` Objekt.  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ppArray`  
 [out] Der Zeiger auf die Safearray verwendet, um die Ergebnisse der Funktion enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg oder einen Standard `HRESULT` Fehlerwert.  
  
##  <a name="a-namebytelengtha--ccombstrbytelength"></a><a name="bytelength"></a>CComBSTR::ByteLength  
 Gibt die Anzahl der Bytes im `m_str`, ausgenommen das abschließende Nullzeichen.  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der [M_str](#m_str) Elements in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Gibt 0 zurück, wenn `m_str` ist **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities Nr.&36;](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="a-nameccombstra--ccombstrccombstr"></a><a name="ccombstr"></a>CComBSTR::CComBSTR  
 Der Konstruktor. Die Standard-Konstruktor legt die [M_str](#m_str) Element **NULL**.  
  
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
 [in] Eine zu kopierende Zeichenfolge. Gibt die Unicode-Version eine **LPCOLESTR**; gibt die ANSI-Version einer `LPCSTR`.  
  
 `pSrc`  
 [in] Eine zu kopierende Zeichenfolge. Gibt die Unicode-Version eine **LPCOLESTR**; gibt die ANSI-Version einer `LPCSTR`.  
  
 *src*  
 [in] Ein `CComBSTR`-Objekt.  
  
 `guid`  
 [in] Ein Verweis auf eine **GUID** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor Sätze `m_str` auf eine Kopie der `BSTR` Mitglied *Src*. Die **REFGUID** Konstruktor konvertiert die **GUID** in eine Zeichenfolge mit **"stringfromguid2"** und speichert das Ergebnis.  
  
 Die anderen Konstruktoren legen `m_str` auf eine Kopie der angegebenen Zeichenfolge fest. Wenn Sie einen Wert für `nSize` übergeben, werden nur `nSize`-Zeichen kopiert, gefolgt von einem abschließenden NULL-Zeichen.  
  
 `CComBSTR` unterstützt die move-Semantik. Können Sie den verschiebekonstruktor (des Konstruktors, der einen Rvalue-Verweis akzeptiert ( `&&`) ein neues Objekt zu erstellen, die dieselben zugrunde liegenden Daten verwendet, das alte Objekt Sie übergeben Sie als Argument der Mehraufwand für das Objekt zu kopieren.  
  
 Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#37;](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]  
  
##  <a name="a-namedtora--ccombstrccombstr"></a><a name="dtor"></a>CComBSTR:: ~ CComBSTR  
 Der Destruktor.  
  
```
~CComBSTR();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.  
  
##  <a name="a-namecopya--ccombstrcopy"></a><a name="copy"></a>CComBSTR::Copy  
 Belegt und gibt eine Kopie des `m_str`.  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der [M_str](#m_str) Element. If `m_str` is **NULL**, returns **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#38;](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="a-namecopytoa--ccombstrcopyto"></a><a name="copyto"></a>CComBSTR::CopyTo  
 Belegt und gibt eine Kopie des [M_str](#m_str) über den Parameter.  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pbstr*  
 [out] Die Adresse einer `BSTR` in dem die Zeichenfolge, die der von dieser Methode zurückgegeben.  
  
 `pvarDest`  
 [out] Die Adresse einer **VARIANT** in dem die Zeichenfolge, die der von dieser Methode zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` Wert, der den Erfolg oder Misserfolg der Kopie.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufrufen dieser Methode die **VARIANT** auf den `pvarDest` vom Typ `VT_BSTR`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities Nr.&39;](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="a-namedetacha--ccombstrdetach"></a><a name="detach"></a>CComBSTR::Detach  
 Trennt [M_str](#m_str) aus der `CComBSTR` -Objekt und stellt `m_str` auf **NULL**.  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `BSTR` zugeordneten der `CComBSTR` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#40;](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]  
  
##  <a name="a-nameemptya--ccombstrempty"></a><a name="empty"></a>CComBSTR::Empty  
 Frei der [M_str](#m_str) Element.  
  
```
void Empty() throw();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#41;](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]  
  
##  <a name="a-namelengtha--ccombstrlength"></a><a name="length"></a>CComBSTR::Length  
 Gibt die Anzahl der Zeichen in `m_str`, ausgenommen das abschließende Nullzeichen.  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der [M_str](#m_str) Element.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#42;](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="a-nameloadstringa--ccombstrloadstring"></a><a name="loadstring"></a>CComBSTR::LoadString  
 Lädt eine Zeichenfolgenressource mit dem angegebenen `nID` und speichert sie in diesem Objekt.  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>Parameter  
 Finden Sie unter [LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** gibt zurück, wenn die Zeichenfolge erfolgreich geladen wurde; andernfalls, **false**.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion lädt die Ressource aus dem Modul identifiziert, indem Sie über die `hInst` Parameter. Die zweite Funktion lädt die Ressource aus dem zugeordneten Ressourcenmodul die [CComModule](../../atl/reference/ccommodule-class.md)-abgeleitetes Objekt in diesem Projekt verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#43;](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="a-namemstra--ccombstrmstr"></a><a name="m_str"></a>CComBSTR::m_str  
 Enthält die `BSTR` zugeordneten der `CComBSTR` Objekt.  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities Nr.&49;](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="a-nameoperatorbstra--ccombstroperator-bstr"></a><a name="operator_bstr"></a>CComBSTR::operator BSTR  
 Wandelt eine `CComBSTR` -Objekt an eine `BSTR`.  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Ermöglicht die Übergabe `CComBSTR` Objekte an Funktionen mit **[in] BSTR** Parameter.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CComBSTR::m_str](#m_str).  
  
##  <a name="a-nameoperatornota--ccombstroperator-"></a><a name="operator_not"></a>CComBSTR::operator!  
 Überprüft, ob `BSTR` Zeichenfolge ist NULL.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das [M_str](#m_str) angehört **NULL**, andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator prüft nur auf einen NULL-Wert nicht für eine leere Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#35;](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="a-nameoperatorneqa--ccombstroperator-"></a><a name="operator_neq"></a>CComBSTR::operator! =  
 Gibt das logische Gegenteil [Operator ==](#operator_eq_eq).  
  
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
 Gibt **true** ist das Element wird im Vergleich nicht gleich der `CComBSTR` Objekt; andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 `CComBSTR`s im Kontext des Benutzers Standardgebietsschema Textbefehl verglichen werden. Der endgültige Vergleichsoperator vergleicht nur die enthaltene Zeichenfolge gegen **NULL**.  
  
##  <a name="a-nameoperatorampa--ccombstroperator-amp"></a><a name="operator_amp"></a>CComBSTR::operator&amp;  
 Gibt die Adresse des der `BSTR` gespeichert, der [M_str](#m_str) Element.  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 `CComBstr operator &`eine spezielle Assertion, um Speicherverluste zu identifizieren sind zugeordnet werden. Das Programm wird beim Bestätigen der `m_str` Member wird initialisiert. Diese Assertion wurde entwickelt, um die Identifizierung von Situationen, in denen Programmierer verwendet, die `& operator` auf einen neuen Wert zuweisen `m_str` Element ohne Freigabe der ersten Zuordnung des `m_str`. Wenn `m_str` gleich NULL ist, das Programm wird davon ausgegangen, M_str war nicht noch zugeordnet. In diesem Fall wird das Programm nicht bestätigen.  
  
 Diese Assertion ist standardmäßig nicht aktiviert. Definieren Sie `ATL_CCOMBSTR_ADDRESS_OF_ASSERT` diese Assertion aktivieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#46;](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities&#47;](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]  
  
##  <a name="a-nameoperatoraddeqa--ccombstroperator-"></a><a name="operator_add_eq"></a>CComBSTR::operator +=  
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
 `CComBSTR`s im Kontext des Benutzers Standardgebietsschema Textbefehl verglichen werden. Die **LPCOLESTR** verglichen mit `memcmp` auf die Rohdaten in jeder Zeichenfolge. Die `LPCSTR` Vergleich erfolgt auf dieselbe Weise nach einem temporären Unicode Kopie von `pszSrc` erstellt wurde. Der endgültige Vergleichsoperator vergleicht nur die enthaltene Zeichenfolge gegen **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#48;](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]  
  
##  <a name="a-nameoperatorlta--ccombstroperator-lt"></a><a name="operator_lt"></a>CComBSTR::operator&lt;  
 Vergleicht einen `CComBSTR` mit einer Zeichenfolge.  
  
```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn die verglichenen Element ist kleiner als der `CComBSTR` Objekt; andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich wird mithilfe von Standardgebietsschema des Benutzers ausgeführt.  
  
##  <a name="a-nameoperatoreqa--ccombstroperator-"></a><a name="operator_eq"></a>CComBSTR::operator =  
 Legt die [M_str](#m_str) Member auf eine Kopie der `pSrc` oder eine Kopie der `BSTR` Mitglied *Src*. Verschiebt der bewegungszuweisungsoperator `src` ohne es zu kopieren.   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>Hinweise  
 Die `pSrc` Parameter gibt entweder eine **LPCOLESTR** für Unicode-Versionen oder `LPCSTR` für ANSI-Versionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CComBSTR::Copy](#copy).  
  
##  <a name="a-nameoperatoreqeqa--ccombstroperator-"></a><a name="operator_eq_eq"></a>CComBSTR::operator ==  
 Vergleicht einen `CComBSTR` mit einer Zeichenfolge. `CComBSTR`s im Kontext des Benutzers Standardgebietsschema Textbefehl verglichen werden.  
  
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
 Gibt **true** , wenn das Element verglichen wird, entspricht die `CComBSTR` Objekt; andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 Der endgültige Vergleichsoperator vergleicht nur die enthaltene Zeichenfolge gegen **NULL**.  
  
##  <a name="a-nameoperatorgta--ccombstroperator-gt"></a><a name="operator_gt"></a>CComBSTR::operator&gt;  
 Vergleicht einen `CComBSTR` mit einer Zeichenfolge.  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist der verglichenen Element größer als die `CComBSTR` Objekt; andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich wird mithilfe von Standardgebietsschema des Benutzers ausgeführt.  
  
##  <a name="a-namereadfromstreama--ccombstrreadfromstream"></a><a name="readfromstream"></a>CComBSTR::ReadFromStream  
 Legt die [M_str](#m_str) Member der `BSTR` im angegebenen Stream enthalten.  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle für den Stream, der Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **ReadToStream** erfordert den Inhalt des Streams an der aktuellen Position kompatibel mit dem Datenformat geschrieben, die durch einen Aufruf von [WriteToStream](#writetostream).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#44;](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="a-nametolowera--ccombstrtolower"></a><a name="tolower"></a>CComBSTR::ToLower  
 Konvertiert die enthaltene Zeichenfolge in Kleinbuchstaben.  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter **CharLowerBuff** Weitere Informationen dazu, wie die Konvertierung ausgeführt wird.  
  
##  <a name="a-nametouppera--ccombstrtoupper"></a><a name="toupper"></a>CComBSTR::ToUpper  
 Konvertiert die enthaltene Zeichenfolge in Großbuchstaben.  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter **CharUpperBuff** Weitere Informationen dazu, wie die Konvertierung ausgeführt wird.  
  
##  <a name="a-namewritetostreama--ccombstrwritetostream"></a><a name="writetostream"></a>CComBSTR::WriteToStream  
 Speichert die [M_str](#m_str) Element in einen Stream.  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Schnittstelle in einem Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sie können einen BSTR aus dem Inhalt der Stream mit neu erstellen, die [ReadFromStream](#readfromstream) Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#45;](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)

