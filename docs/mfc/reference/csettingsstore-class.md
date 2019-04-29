---
title: CSettingsStore Class
ms.date: 11/04/2016
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
ms.openlocfilehash: 1e1373da86c1c3fea3b1ddd6ff17f0fac4f76980
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324187"
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
|[CSettingsStore::CreateKey](#createkey)|Öffnet den angegebenen Schlüssel ab oder erstellt diese, wenn er nicht vorhanden ist.|
|[CSettingsStore::DeleteKey](#deletekey)|Löscht den angegebenen Schlüssel und alle untergeordneten Elemente.|
|[CSettingsStore::DeleteValue](#deletevalue)|Löscht den angegebenen Wert, der den geöffneten Schlüssel.|
|[CSettingsStore::Open](#open)|Öffnet den angegebenen Schlüssel.|
|[CSettingsStore::Read](#read)|Ruft die Daten für einen angegebenen Schlüsselwert ab.|
|[CSettingsStore::Write](#write)|Schreibt einen Wert in der Registrierung unter den geöffneten Schlüssel.|

## <a name="remarks"></a>Hinweise

Die Memberfunktionen `CreateKey` und `Open` sind sehr ähnlich. Wenn der Registrierungsschlüssel bereits vorhanden ist, `CreateKey` und `Open` Funktion auf die gleiche Weise. Jedoch, wenn der Registrierungsschlüssel nicht vorhanden ist, `CreateKey` erstellt während `Open` gibt einen Fehlerwert zurück.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die Methoden öffnen und lesen, der die `CSettingsStore` Klasse. Dieser Codeausschnitt ist Teil der [Tool Tipp Demobeispiel](../../overview/visual-cpp-samples.md).

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

Standardmäßig ist diese Methode aufgerufen, aus der Destruktor von der [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).

##  <a name="createkey"></a>  CSettingsStore::CreateKey

Öffnet einen Registrierungsschlüssel oder erstellt diese, wenn er nicht vorhanden ist.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
[in] Gibt den Namen eines Schlüssels erstellt oder geöffnet werden.

### <a name="return-value"></a>Rückgabewert

0, wenn erfolgreich; andernfalls ein Wert ungleich NULL.

### <a name="remarks"></a>Hinweise

`CreateKey` verwendet `m_hKey` als Stamm Anfragen, die Registrierung. Es sucht nach *PszPath* als Unterschlüssel des `m_hKey`. Wenn der Schlüssel nicht vorhanden ist, `CreateKey` wird erstellt. Andernfalls wird es den Schlüssel geöffnet. `CreateKey` legt dann `m_hKey` auf den Schlüssel geöffnet oder erstellt wurden.

##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore

Erstellt ein `CSettngsStore`-Objekt.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parameter

*bAdmin*<br/>
[in] Boolescher Parameter, der angibt, ob die `CSettingsStore` Objekt dient, im Administratormodus.

*bReadOnly*<br/>
[in] Boolescher Parameter, der angibt, ob die `CSettingsStore` Objekt wird in nur-Lese Modus erstellt.

### <a name="remarks"></a>Hinweise

Wenn *bAdminpfad* ist auf TRUE festgelegt, die `m_hKey` Membervariable nastaven NA hodnotu **HKEY_LOCAL_MACHINE**. Setzen Sie *bAdminpfad* auf "FALSE" `m_hKey` nastaven NA hodnotu **HKEY_CURRENT_USER**.

Hängt von der Sicherheitszugriff der *bReadOnly* Parameter. Wenn *bReadonly* ist "false", der Sicherheitszugriff auf gesetzt **KEY_ALL_ACCESS**. Wenn *bReadyOnly* TRUE ist, wird eine Kombination aus der Sicherheitszugriff festgelegt **KEY_QUERY_VALUE, KEY_NOTIFY** und **KEY_ENUMERATE_SUB_KEYS nicht**. Weitere Informationen zu den Sicherheitszugriff, zusammen mit der Registrierung, finden Sie unter [Schlüssel Registrierungssicherheit und Zugriffsrechte](/windows/desktop/SysInfo/registry-key-security-and-access-rights).

Der Destruktor für `CSettingsStore` frei `m_hKey` automatisch.

##  <a name="deletekey"></a>  CSettingsStore::DeleteKey

Löscht einen Schlüssel und alle zugehörigen untergeordneten Elemente aus der Registrierung an.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
[in] Der Name des Schlüssels, der gelöscht werden soll.

*bAdmin*<br/>
[in] Der Schalter, der angibt, den Speicherort des Schlüssels zu löschen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn die `CSettingsStore` Objekt befindet sich im schreibgeschützten Modus.

Wenn der Parameter *bAdminpfad* ist 0 (null), `DeleteKey` Suchvorgänge für den Schlüssel unter Löschen **HKEY_CURRENT_USER**. Wenn *bAdminpfad* ungleich NULL ist, `DeleteKey` Suchvorgänge für den Schlüssel unter Löschen **HKEY_LOCAL_MACHINE**.

##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue

Löscht einen Wert von `m_hKey`.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Parameter

*pszValue*<br/>
[in] Gibt das Wertfeld "zu entfernen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="open"></a>  CSettingsStore::Open

Öffnet einen Registrierungsschlüssel an.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
[in] Der Name eines Registrierungsschlüssels.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Nachdem diese Methode den angegebenen Schlüssel wurde erfolgreich geöffnet wurde, wird `m_hKey` an das Handle dieses Schlüssels.

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

*pszKey*<br/>
[in] Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der aus der Registrierung gelesen.

*iVal*<br/>
[out] Verweis auf eine ganzzahlige Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*dwVal*<br/>
[out] Verweis auf eine 32-Bit-Doppelwort-Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*sVal*<br/>
[out] Verweis auf eine String-Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*scStringList*<br/>
[out] Verweis auf eine Zeichenfolgenvariable in der Liste ein, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*scArray*<br/>
[out] Verweis auf eine String-Array-Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*dwcArray*<br/>
[out] Verweis auf eine 32-Bit-Doppelwort-Array-Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*wcArray*<br/>
[out] Verweis auf eine 16-Bit-Wort-Array-Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*bcArray*<br/>
[out] Verweis auf einen Byte-Array-Variable, die empfängt den Wert aus dem Registrierungsschlüssel zu lesen.

*lpPoint*<br/>
[out] Verweis auf einen Zeiger auf eine `POINT` -Struktur, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.

*rect*<br/>
[out] Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.

*ppData*<br/>
[out] Zeiger auf einen Zeiger auf Daten, die empfängt den Wert aus dem Registrierungsschlüssel lesen.

*pBytes*<br/>
[out] Zeiger auf die Variable eine ganze Zahl ohne Vorzeichen. Diese Variable empfängt die Größe des Puffers, *PpData* verweist auf.

*list*<br/>
[out] Ein Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.

*obj*<br/>
[out] Ein Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.

*pObj*<br/>
[out] Verweis auf einen Zeiger auf eine `CObject` -Variable, den Wert empfängt, aus dem Registrierungsschlüssel zu lesen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

`Read` überprüft, ob *PszKey* als Unterschlüssel des `m_hKey`.

##  <a name="write"></a>  CSettingsStore::Write

Schreibt einen Wert in der Registrierung unter den geöffneten Schlüssel.

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

*pszKey*<br/>
[in] Zeiger auf eine Zeichenfolge, die den Namen der den festzulegenden Wert enthält.

*iVal*<br/>
[in] Verweis auf eine ganzzahlige Variable, die die zu speichernden Daten enthält.

*dwVal*<br/>
[in] Verweis auf eine 32-Bit-Doppelwort-Variable, die zu speichernden Daten enthält.

*pszVal*<br/>
[in] Zeiger auf eine Null-terminierte Zeichenfolge-Variable, die zu speichernden Daten enthält.

*scStringList*<br/>
[in] Ein Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) Variable, die die zu speichernden Daten enthält.

*bcArray*<br/>
[in] Verweis auf eine Byte-Array-Variable, die zu speichernden Daten enthält.

*scArray*<br/>
[in] Verweis auf eine String-Array-Variable, die die zu speichernden Daten enthält.

*dwcArray*<br/>
[in] Verweis auf eine 32-Bit-Doppelwort-Array-Variable, die zu speichernden Daten enthält.

*wcArray*<br/>
[in] Verweis auf eine 16-Bit-Wort-Array-Variable, die zu speichernden Daten enthält.

*rect*<br/>
[in] Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Variable, die die zu speichernden Daten enthält.

*lpPoint*<br/>
[in] Verweis auf einen Zeiger auf eine `POINT` Variable, die die zu speichernden Daten enthält.

*pData*<br/>
[in] Zeiger auf einen Puffer, der die zu speichernden Daten enthält.

*nBytes*<br/>
[in] Gibt die Größe in Bytes der Daten, die die *pData* -Parameter zeigt.

*list*<br/>
[in] Ein Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) Variable, die die zu speichernden Daten enthält.

*obj*<br/>
[in] Ein Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) Variable, die die zu speichernden Daten enthält.

*pObj*<br/>
[in] Zeiger auf einen Zeiger auf eine `CObject` Variable, die die zu speichernden Daten enthält.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Um in der Registrierung zu schreiben, müssen Sie festlegen *bReadOnly* einen Wert ungleich NULL, wenn Sie erstellen eine [CSettingsStore](../../mfc/reference/csettingsstore-class.md) Objekt. Weitere Informationen finden Sie unter [CSettingsStore::CSettingsStore](#csettingsstore).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
