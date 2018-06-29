---
title: CSettingsStore-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7711e0105085f0b7af1344ce230839e90f2b6851
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079487"
---
# <a name="csettingsstore-class"></a>CSettingsStore Class
Kapselt Windows-API-Funktionen und stellt eine objektorientierte Schnittstelle für den Zugriff auf die Registrierung bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|Erstellt ein `CSettingsStore`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|Schließt das Öffnen des Registrierungsschlüssels an.|  
|[CSettingsStore::CreateKey](#createkey)|Öffnet den angegebenen Schlüssel oder erstellt diese, wenn er nicht vorhanden ist.|  
|[CSettingsStore::DeleteKey](#deletekey)|Löscht den angegebenen Schlüssel und aller diesem untergeordneten Elemente.|  
|[CSettingsStore::DeleteValue](#deletevalue)|Löscht den angegebenen Wert des Schlüssels öffnen.|  
|[CSettingsStore::Open](#open)|Öffnet den angegebenen Schlüssel.|  
|[CSettingsStore::Read](#read)|Ruft die Daten für einen angegebenen Schlüsselwert ab.|  
|[CSettingsStore::Write](#write)|Schreibt einen Wert in der Registrierung unter folgendem Schlüssel geöffnet.|  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktionen `CreateKey` und `Open` sind sehr ähnlich. Wenn der Registrierungsschlüssel bereits vorhanden ist, `CreateKey` und `Open` Funktion auf die gleiche Weise. Jedoch, wenn der Registrierungsschlüssel nicht vorhanden ist, `CreateKey` erstellt während `Open` gibt einen Fehlerwert zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Methoden öffnen "und" Lesen ", der die `CSettingsStore` Klasse. Dieser Codeausschnitt ist Teil der [Tool Tipp Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxsettingsstore.h  
  
##  <a name="close"></a>  CSettingsStore::Close  
 Schließt das Öffnen des Registrierungsschlüssels an.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode aufgerufen, aus der Destruktor von der [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).  
  
##  <a name="createkey"></a>  CSettingsStore::CreateKey  
 Öffnet einen Registrierungsschlüssel oder erstellt diese, wenn er nicht vorhanden ist.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PszPath*  
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 0, wenn erfolgreich; andernfalls einen Wert ungleich NULL.  
  
### <a name="remarks"></a>Hinweise  
 `CreateKey` verwendet `m_hKey` als Stamm der Registrierung Abfragen. Sucht *PszPath* als einen Unterschlüssel des Schlüssels `m_hKey`. Wenn der Schlüssel nicht vorhanden ist, `CreateKey` wird erstellt. Andernfalls wird den Schlüssel geöffnet. `CreateKey` legt dann `m_hKey` auf den Schlüssel geöffnet oder erstellt wurden.  
  
##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore  
 Erstellt ein `CSettngsStore`-Objekt.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAdminpfad*  
 Boolescher Parameter, der angibt, ob die `CSettingsStore` Objekt dient im Administratormodus.  
  
 [in] *bReadOnly*  
 Boolescher Parameter, der angibt, ob die `CSettingsStore` Objekt wird in nur-Lese-Modus erstellt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bAdminpfad* festgelegt ist, um `true`, `m_hKey` Membervariable wird festgelegt, um `HKEY_LOCAL_MACHINE`. Wenn Sie festlegen, *bAdminpfad* auf `false`, `m_hKey` festgelegt ist, um `HKEY_CURRENT_USER`.  
  
 Der Sicherheitszugriff hängt die *bReadOnly* Parameter. Wenn *bReadonly* ist `false`, den Sicherheitszugriff festgelegt, um `KEY_ALL_ACCESS`. Wenn *bReadyOnly* ist `true`, den Sicherheitszugriff festgelegt, um eine Kombination von `KEY_QUERY_VALUE, KEY_NOTIFY` und `KEY_ENUMERATE_SUB_KEYS`. Weitere Informationen über Sicherheitszugriff zusammen mit der Registrierung finden Sie unter [Registry Key Sicherheit und Zugriffsrechte](http://msdn.microsoft.com/library/windows/desktop/ms724878).  
  
 Der Destruktor für `CSettingsStore` frei `m_hKey` automatisch.  
  
##  <a name="deletekey"></a>  CSettingsStore::DeleteKey  
 Löscht einen Schlüssel und aller diesem untergeordneten Elemente aus der Registrierung.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PszPath*  
 Der Name des Schlüssels zu löschen.  
  
 [in] *bAdminpfad*  
 Wechseln Sie den Speicherort des Schlüssels zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn die `CSettingsStore` Objekt befindet sich im schreibgeschützten Modus.  
  
 Wenn der Parameter *bAdminpfad* ist 0 (null), `DeleteKey` sucht nach den Schlüssel unter Löschen `HKEY_CURRENT_USER`. Wenn *bAdminpfad* ungleich NULL ist `DeleteKey` sucht nach den Schlüssel unter Löschen `HKEY_LOCAL_MACHINE`.  
  
##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue  
 Löscht einen Wert von `m_hKey`.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PszValue*  
 Gibt das Wertfeld zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="open"></a>  CSettingsStore::Open  
 Öffnet einen Registrierungsschlüssel an.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PszPath*  
 Der Name eines Registrierungsschlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf dieser Methode den angegebenen Schlüssel erfolgreich geöffnet wird, legt `m_hKey` an das Handle dieses Schlüssels.  
  
##  <a name="read"></a>  CSettingsStore::Read  
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
 [in] *PszKey*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts aus der Registrierung gelesen.  
  
 [out] *iVal*  
 Verweis auf eine ganzzahlige Variable, die den Wert aus dem Registrierungsschlüssel lesen empfängt.  
  
 [out] *DwVal*  
 Verweis auf eine 32-Bit-Doppelwort-Variable, die aus dem Registrierungsschlüssel gelesenen Wert empfängt.  
  
 [out] *sVal*  
 Verweis auf eine Zeichenfolgenvariable, die den Wert aus dem Registrierungsschlüssel lesen empfängt.  
  
 [out] *ScStringList*  
 Verweis auf eine Zeichenfolgenvariable in der Liste ein, die den Wert aus dem Registrierungsschlüssel lesen empfängt.  
  
 [out] *ScArray*  
 Verweis auf eine Zeichenfolge-Array-Variable, die aus dem Registrierungsschlüssel gelesenen Wert empfängt.  
  
 [out] *DwcArray*  
 Verweis auf eine 32-Bit-Doppelwort-Array-Variable, die aus dem Registrierungsschlüssel gelesenen Wert empfängt.  
  
 [out] *WcArray*  
 Verweis auf eine 16-Bit-Wort-Array-Variable, die aus dem Registrierungsschlüssel gelesenen Wert empfängt.  
  
 [out] *BcArray*  
 Verweis auf eine Byte-Array-Variable, die aus dem Registrierungsschlüssel gelesenen Wert empfängt.  
  
 [out] *LpPoint*  
 Verweis auf einen Zeiger auf eine `POINT` Struktur, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.  
  
 [out] *Rect*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.  
  
 [out] *PpData*  
 Zeiger auf einen Zeiger auf Daten, die den Wert empfangen aus dem Registrierungsschlüssel zu lesen.  
  
 [out] *pBytes*  
 Zeiger auf die Variable eine ganze Zahl ohne Vorzeichen. Diese Variable empfängt die Größe des Puffers, *PpData* verweist auf.  
  
 [out] *Liste*  
 Ein Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.  
  
 [out] *Obj*  
 Ein Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.  
  
 [out] *pObj*  
 Verweis auf einen Zeiger auf eine `CObject` -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 `Read` überprüft, ob *PszKey* als einen Unterschlüssel des Schlüssels `m_hKey`.  
  
##  <a name="write"></a>  CSettingsStore::Write  
 Schreibt einen Wert in der Registrierung unter folgendem Schlüssel geöffnet.  
  
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
 [in] *PszKey*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der den festzulegenden Wert enthält.  
  
 [in] *iVal*  
 Verweis auf eine ganzzahlige Variable, die die zu speichernden Daten enthält.  
  
 [in] *DwVal*  
 Verweis auf eine 32-Bit-Doppelwort-Variable, die die zu speichernden Daten enthält.  
  
 [in] *PszVal*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge-Variable, die zu speichernden Daten enthält.  
  
 [in] *ScStringList*  
 Ein Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) Variable an, die zu speichernden Daten enthält.  
  
 [in] *BcArray*  
 Verweis auf ein Byte-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] *ScArray*  
 Verweis auf eine Zeichenfolgenvariable für das Array, die die zu speichernden Daten enthält.  
  
 [in] *DwcArray*  
 Verweis auf eine 32-Bit-Doppelwort-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] *WcArray*  
 Verweis auf eine 16-Bit-Wort-Array-Variable, die die zu speichernden Daten enthält.  
  
 [in] *Rect*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Variable an, die zu speichernden Daten enthält.  
  
 [in] *LpPoint*  
 Verweis auf einen Zeiger auf eine `POINT` Variable an, die zu speichernden Daten enthält.  
  
 [in] *pData*  
 Ein Zeiger auf einen Puffer, der die zu speichernden Daten enthält.  
  
 [in] *Anzahl_byte*  
 Gibt die Größe in Bytes, der Daten, die *pData* Parameter verweist.  
  
 [in] *Liste*  
 Ein Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) Variable an, die zu speichernden Daten enthält.  
  
 [in] *Obj*  
 Ein Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) Variable an, die zu speichernden Daten enthält.  
  
 [in] *pObj*  
 Zeiger auf einen Zeiger auf eine `CObject` Variable an, die zu speichernden Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Um in der Registrierung zu schreiben, müssen Sie festlegen *bReadOnly* auf einen Wert ungleich NULL bei der Erstellung einer [CSettingsStore](../../mfc/reference/csettingsstore-class.md) Objekt. Weitere Informationen finden Sie unter [CSettingsStore::CSettingsStore](#csettingsstore).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
