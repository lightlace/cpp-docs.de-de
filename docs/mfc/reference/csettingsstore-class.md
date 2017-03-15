---
title: Klasse CSettingsStore | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStore
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStore class
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 0918c8dd9b6284adecb61bc95ddfd41c22d16cb8
ms.lasthandoff: 02/24/2017

---
# <a name="csettingsstore-class"></a>CSettingsStore Class
Kapselt Windows-API-Funktionen und stellt eine objektorientierte Schnittstelle für den Zugriff auf die Registrierung bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|Erstellt ein `CSettingsStore`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|Schließt das Öffnen des Registrierungsschlüssels.|  
|[CSettingsStore::CreateKey](#createkey)|Öffnet den angegebenen Schlüssel, bzw. erstellt, sofern sie nicht vorhanden ist.|  
|[CSettingsStore::DeleteKey](#deletekey)|Löscht den angegebenen Schlüssel und alle untergeordneten Elemente.|  
|[CSettingsStore::DeleteValue](#deletevalue)|Löscht den angegebenen Wert des Schlüssels öffnen.|  
|[CSettingsStore::Open](#open)|Öffnet den angegebenen Schlüssel.|  
|[CSettingsStore::Read](#read)|Ruft die Daten für einen angegebenen Schlüsselwert.|  
|[CSettingsStore::Write](#write)|Schreibt einen Wert in der Registrierung unter dem Schlüssel geöffnet.|  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktionen `CreateKey` und `Open` sind sehr ähnlich. Wenn der Registrierungsschlüssel bereits vorhanden ist, `CreateKey` und `Open` Funktion auf die gleiche Weise. Jedoch, wenn der Registrierungsschlüssel nicht vorhanden ist, `CreateKey` erstellt während `Open` gibt einen Fehlerwert zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Methoden öffnen und lesen, der die `CSettingsStore` Klasse. Dieser Codeausschnitt ist Teil der [Tool Tipp Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo&#1;](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxsettingsstore.h  
  
##  <a name="a-nameclosea--csettingsstoreclose"></a><a name="close"></a>CSettingsStore::Close  
 Schließt das Öffnen des Registrierungsschlüssels.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen werden standardmäßig aus der Destruktor der [CSettingsStore Klasse](../../mfc/reference/csettingsstore-class.md).  
  
##  <a name="a-namecreatekeya--csettingsstorecreatekey"></a><a name="createkey"></a>CSettingsStore::CreateKey  
 Öffnet einen Registrierungsschlüssel, bzw. erstellt, sofern sie nicht vorhanden ist.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszPath`  
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 0, wenn erfolgreich; andernfalls einen Wert ungleich NULL.  
  
### <a name="remarks"></a>Hinweise  
 `CreateKey`verwendet `m_hKey` als Stamm der Registrierung Abfragen. Sucht nach `pszPath` als Unterschlüssel von `m_hKey`. Wenn der Schlüssel nicht vorhanden ist, `CreateKey` wird erstellt. Andernfalls wird den Schlüssel geöffnet. `CreateKey`legt dann `m_hKey` auf den Schlüssel geöffnet oder erstellt wurden.  
  
##  <a name="a-namecsettingsstorea--csettingsstorecsettingsstore"></a><a name="csettingsstore"></a>CSettingsStore::CSettingsStore  
 Erstellt ein `CSettngsStore`-Objekt.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAdmin`  
 Boolescher Parameter, der angibt, ob die `CSettingsStore` Objekt fungiert im Administratormodus.  
  
 [in] `bReadOnly`  
 Boolescher Parameter, der angibt, ob das `CSettingsStore` Objekt wird im schreibgeschützten Modus erstellt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bAdmin` Wert `false`, `m_hKey` Membervariable auf festgelegt ist `HKEY_LOCAL_MACHINE`. If you set `bAdmin` to `true`, `m_hKey` is set to `HKEY_CURRENT_USER`.  
  
 Der Sicherheitszugriff hängt die `bReadOnly` Parameter. Wenn `bReadonly` ist `false`, werden der Sicherheitszugriff auf den `KEY_ALL_ACCESS`. Wenn `bReadyOnly` ist `true`, der Sicherheitszugriff festgelegt, um eine Kombination von `KEY_QUERY_VALUE, KEY_NOTIFY` und `KEY_ENUMERATE_SUB_KEYS`. Weitere Informationen über Sicherheitszugriff zusammen mit der Registrierung finden Sie unter [Registry Key Sicherheit und Zugriffsrechte](http://msdn.microsoft.com/library/windows/desktop/ms724878).  
  
 Der Destruktor für `CSettingsStore` frei `m_hKey` automatisch.  
  
##  <a name="a-namedeletekeya--csettingsstoredeletekey"></a><a name="deletekey"></a>CSettingsStore::DeleteKey  
 Löscht einen Schlüssel und alle untergeordneten Elemente aus der Registrierung.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszPath`  
 Der Name des Schlüssels, der gelöscht werden soll.  
  
 [in] `bAdmin`  
 Wechseln Sie den Speicherort des Schlüssels zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn die `CSettingsStore` Objekt befindet sich im schreibgeschützten Modus.  
  
 Wenn der Parameter `bAdmin` NULL ist, `DeleteKey` sucht nach den Schlüssel löschen unter `HKEY_CURRENT_USER`. Wenn `bAdmin` ungleich NULL ist, `DeleteKey` sucht nach den Schlüssel löschen unter `HKEY_LOCAL_MACHINE`.  
  
##  <a name="a-namedeletevaluea--csettingsstoredeletevalue"></a><a name="deletevalue"></a>CSettingsStore::DeleteValue  
 Löscht einen Wert von `m_hKey`.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszValue`  
 Gibt das Wertfeld "zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-nameopena--csettingsstoreopen"></a><a name="open"></a>CSettingsStore::Open  
 Öffnet einen Registrierungsschlüssel.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszPath`  
 Der Name eines Registrierungsschlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode den angegebenen Schlüssel erfolgreich geöffnet wurde, wird `m_hKey` auf das Handle des Schlüssels.  
  
##  <a name="a-namereada--csettingsstoreread"></a><a name="read"></a>CSettingsStore::Read  
 Liest einen Wert aus einem Schlüssel in der Registrierung.  
  
```  
virtual BOOL Read(
    LPCTSTR pszKey,  
    int& iVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    DWORD& dwVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CString& sVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CRect& rect);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    BYTE** ppData,  
    UINT* pBytes);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject*& pObj);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszKey`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge mit dem Namen des Werts, der aus der Registrierung gelesen.  
  
 [out] `iVal`  
 Verweis auf eine ganzzahlige Variable, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `dwVal`  
 Verweis auf eine 32-Bit-Doppelwort-Variable, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `sVal`  
 Verweis auf eine String-Variable, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `scStringList`  
 Verweis auf eine Zeichenfolgenvariable in der Liste ein, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `scArray`  
 Verweis auf eine String-Array-Variable, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `dwcArray`  
 Verweis auf eine 32-Bit-Doppelwort Array-Variable, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `wcArray`  
 Verweis auf eine 16-Bit-Wort Array-Variable, die den Wert aus dem Registrierungsschlüssel gelesen werden empfängt.  
  
 [out] `bcArray`  
 Verweis auf ein Byte-Array-Variable, die den Wert aus dem Registrierungsschlüssel lesen empfängt.  
  
 [out] `lpPoint`  
 Verweis auf einen Zeiger auf eine `POINT` -Struktur, die den Wert empfängt aus dem Registrierungsschlüssel zu lesen.  
  
 [out] `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Variable den Wert aus dem Registrierungsschlüssel zu lesen.  
  
 [out] `ppData`  
 Zeiger auf einen Zeiger auf Daten, die den Wert empfängt aus dem Registrierungsschlüssel lesen.  
  
 [out] `pBytes`  
 Zeiger auf die Variable eine ganze Zahl ohne Vorzeichen. Diese Variable empfängt die Größe des Puffers, `ppData` verweist.  
  
 [out] `list`  
 Ein Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) -Variable den Wert aus dem Registrierungsschlüssel zu lesen.  
  
 [out] `obj`  
 Ein Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) -Variable den Wert aus dem Registrierungsschlüssel zu lesen.  
  
 [out] `pObj`  
 Verweis auf einen Zeiger auf eine `CObject` -Variable den Wert aus dem Registrierungsschlüssel zu lesen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 `Read`überprüft, ob `pszKey` als Unterschlüssel von `m_hKey`.  
  
##  <a name="a-namewritea--csettingsstorewrite"></a><a name="write"></a>CSettingsStore::Write  
 Schreibt einen Wert in der Registrierung unter dem Schlüssel geöffnet.  
  
```  
virtual BOOL Write(
    LPCTSTR pszKey,  
    int iVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    DWORD dwVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPCTSTR pszVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    const CRect& rect);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPBYTE pData,  
    UINT nBytes);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszKey`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der den festzulegenden Wert enthält.  
  
 [in] `iVal`  
 Verweis auf eine ganzzahlige Variable, die die zu speichernden Daten enthält.  
  
 [in] `dwVal`  
 Verweis auf eine 32-Bit-Doppelwort-Variable, die zu speichernden Daten enthält.  
  
 [in] `pszVal`  
 Ein Zeiger auf eine auf Null abschließende Zeichenfolge-Variable, die zu speichernden Daten enthält.  
  
 [in] `scStringList`  
 Ein Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) Variable, die die zu speichernden Daten enthält.  
  
 [in] `bcArray`  
 Verweis auf ein Byte-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] `scArray`  
 Verweis auf eine String-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] `dwcArray`  
 Verweis auf eine 32-Bit-Doppelwort-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] `wcArray`  
 Verweis auf eine 16-Bit-Wort-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] `rect`  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Variable, die die zu speichernden Daten enthält.  
  
 [in] `lpPoint`  
 Verweis auf einen Zeiger auf eine `POINT` Variable, die die zu speichernden Daten enthält.  
  
 [in] `pData`  
 Ein Zeiger auf einen Puffer, der die zu speichernden Daten enthält.  
  
 [in] `nBytes`  
 Gibt die Größe in Bytes der Daten, die die `pData` Parameter verweist.  
  
 [in] `list`  
 Ein Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) Variable, die die zu speichernden Daten enthält.  
  
 [in] `obj`  
 Ein Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) Variable, die die zu speichernden Daten enthält.  
  
 [in] `pObj`  
 Zeiger auf einen Zeiger auf eine `CObject` Variable, die die zu speichernden Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Um in der Registrierung zu schreiben, müssen Sie festlegen `bReadOnly` ein Wert ungleich NULL bei der Erstellung einer [CSettingsStore](../../mfc/reference/csettingsstore-class.md) Objekt. Weitere Informationen finden Sie unter [CSettingsStore::CSettingsStore](#csettingsstore).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)

