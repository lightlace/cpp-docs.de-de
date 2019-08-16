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
ms.openlocfilehash: 75d86b81d9651e5892913af5919ae0a78fe6bbc5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502923"
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
|[CSettingsStore::Close](#close)|Schließt den geöffneten Registrierungsschlüssel.|
|[CSettingsStore::CreateKey](#createkey)|Öffnet den angegebenen Schlüssel oder erstellt ihn, wenn er nicht vorhanden ist.|
|[CSettingsStore::DeleteKey](#deletekey)|Löscht den angegebenen Schlüssel und alle untergeordneten Elemente.|
|[CSettingsStore::DeleteValue](#deletevalue)|Löscht den angegebenen Wert des geöffneten Schlüssels.|
|[CSettingsStore::Open](#open)|Öffnet den angegebenen Schlüssel.|
|[CSettingsStore::Read](#read)|Ruft die Daten für einen angegebenen Schlüsselwert ab.|
|[CSettingsStore::Write](#write)|Schreibt einen Wert in die Registrierung unter der geöffneten Taste.|

## <a name="remarks"></a>Hinweise

Die Member- `CreateKey` Funktionen `Open` und sind sehr ähnlich. Wenn der Registrierungsschlüssel bereits vorhanden ist `CreateKey` , `Open` und funktionieren Sie auf dieselbe Weise. Wenn der Registrierungsschlüssel jedoch nicht vorhanden ist, wird `CreateKey` er von erstellt, `Open` während einen Fehlerwert zurückgibt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die Open-Methode und die Read `CSettingsStore` -Methode der-Klasse verwendet werden. Dieser Code Ausschnitt ist Teil des QuickInfo- [Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>Anforderungen

**Header:** afxsettingsstore. h

##  <a name="close"></a>Csettingsstore:: Close

Schließt den geöffneten Registrierungsschlüssel.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Standardmäßig wird diese Methode vom Dekonstruktor der [csettingsstore-Klasse](../../mfc/reference/csettingsstore-class.md)aufgerufen.

##  <a name="createkey"></a>Csettingsstore:: up Key

Öffnet einen Registrierungsschlüssel oder erstellt ihn, wenn er nicht vorhanden ist.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
in Gibt den Namen eines zu erstellenden oder zu öffnenden Schlüssels an.

### <a name="return-value"></a>Rückgabewert

0, wenn erfolgreich; andernfalls ein Wert ungleich 0 (null).

### <a name="remarks"></a>Hinweise

`CreateKey`wird `m_hKey` als Stamm von Registrierungsanfragen verwendet. Er sucht nach *pszpath* als Unterschlüssel von `m_hKey`. Wenn der Schlüssel nicht vorhanden ist, `CreateKey` wird er von erstellt. Andernfalls wird der Schlüssel geöffnet. `CreateKey`dann wird `m_hKey` auf den erstellten oder geöffneten Schlüssel festgelegt.

##  <a name="csettingsstore"></a>Csettingsstore:: csettingsstore

Erstellt ein `CSettngsStore`-Objekt.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parameter

*bAdmin*<br/>
in Boolescher Parameter, der angibt, `CSettingsStore` ob das Objekt im Administrator Modus fungiert.

*bReadOnly*<br/>
in Boolescher Parameter, der angibt, `CSettingsStore` ob das Objekt im schreibgeschützten Modus erstellt wird.

### <a name="remarks"></a>Hinweise

Wenn *Badmin* auf true festgelegt ist, `m_hKey` wird die Element Variable auf **HKEY_LOCAL_MACHINE**festgelegt. Wenn Sie *Badmin* auf false festlegen, `m_hKey` wird auf **HKEY_CURRENT_USER**festgelegt.

Der Sicherheits Zugriff hängt von dem *bReadOnly* -Parameter ab. Wenn *bReadOnly* den Wert false hat, wird der Sicherheits Zugriff auf **KEY_ALL_ACCESS**festgelegt. Wenn *breadyonly* den Wert true hat, wird der Sicherheits Zugriff auf eine Kombination aus **KEY_QUERY_VALUE, KEY_NOTIFY** und **KEY_ENUMERATE_SUB_KEYS**festgelegt. Weitere Informationen zum Sicherheits Zugriff in Verbindung mit der Registrierung finden Sie unter [Sicherheit und Zugriffsrechte für den Registrierungsschlüssel](/windows/win32/SysInfo/registry-key-security-and-access-rights).

Der Dekonstruktor `CSettingsStore` für `m_hKey` Releases wird automatisch angezeigt.

##  <a name="deletekey"></a>Csettingsstore::D eletekey

Löscht einen Schlüssel und alle untergeordneten Elemente aus der Registrierung.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
in Der Name des zu löschenden Schlüssels.

*bAdmin*<br/>
in Ein Schalter, der den Speicherort des zu löschenden Schlüssels angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn `CSettingsStore` sich das Objekt im schreibgeschützten Modus befindet.

Wenn der Parameter *Badmin* NULL ist, `DeleteKey` sucht nach dem zu löschenden Schlüssel unter **HKEY_CURRENT_USER**. Wenn *Badmin* ungleich NULL ist, `DeleteKey` sucht nach dem zu löschenden Schlüssel unter **HKEY_LOCAL_MACHINE**.

##  <a name="deletevalue"></a>Csettingsstore::D eletevalue

Löscht einen Wert aus `m_hKey`.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Parameter

*pszValue*<br/>
in Gibt das Wertfeld an, das entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="open"></a>Csettingsstore:: Open

Öffnet einen Registrierungsschlüssel.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Parameter

*pszPath*<br/>
in Der Name eines Registrierungsschlüssels.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Nachdem diese Methode den angegebenen Schlüssel erfolgreich geöffnet hat, wird `m_hKey` auf das Handle dieses Schlüssels festgelegt.

##  <a name="read"></a>Csettingsstore:: Read

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
in Ein Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des Werts enthält, der aus der Registrierung gelesen werden soll.

*iVal*<br/>
vorgenommen Verweis auf eine ganzzahlige Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*dwVal*<br/>
vorgenommen Verweis auf eine 32-Bit-Doppelwort Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*sVal*<br/>
vorgenommen Verweis auf eine Zeichen folgen Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*scStringList*<br/>
vorgenommen Verweis auf eine Zeichen folgen Listen Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*scArray*<br/>
vorgenommen Verweis auf eine Zeichen folgen Array Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*dwcArray*<br/>
vorgenommen Verweis auf eine 32-Bit-Double-Word-Array Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*wcArray*<br/>
vorgenommen Verweis auf eine 16-Bit-Word-Array Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*bcArray*<br/>
vorgenommen Verweis auf eine Bytearray-Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*lpPoint*<br/>
vorgenommen Verweis auf einen Zeiger auf eine `POINT` -Struktur, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*Rect*<br/>
vorgenommen Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*ppData*<br/>
vorgenommen Zeiger auf einen Zeiger auf Daten, die den aus dem Registrierungsschlüssel gelesenen Wert empfangen.

*pBytes*<br/>
vorgenommen Zeiger auf eine ganzzahlige Variable ohne Vorzeichen. Diese Variable erhält die Größe des Puffers, auf den *ppData* verweist.

*list*<br/>
vorgenommen Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) -Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*obj*<br/>
vorgenommen Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) -Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

*pObj*<br/>
vorgenommen Verweis auf einen Zeiger auf eine `CObject` Variable, die den aus dem Registrierungsschlüssel gelesenen Wert empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

`Read`prüft *pszkey* als Unterschlüssel von `m_hKey`.

##  <a name="write"></a>Csettingsstore:: Write

Schreibt einen Wert in die Registrierung unter der geöffneten Taste.

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
in Ein Zeiger auf eine Zeichenfolge, die den Namen des festzulegenden Werts enthält.

*iVal*<br/>
in Verweis auf eine ganzzahlige Variable, die die zu Speicher Ende Daten enthält.

*dwVal*<br/>
in Verweis auf eine 32-Bit-Doppelwort Variable, die die zu speicherbaren Daten enthält.

*pszVal*<br/>
in Zeiger auf eine mit NULL endenden Zeichen folgen Variable, die die zu Speicher enden Daten enthält.

*scStringList*<br/>
in Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) -Variable, die die Daten enthält, die gespeichert werden sollen.

*bcArray*<br/>
in Verweis auf eine Bytearray-Variable, die die zu speicherbaren Daten enthält.

*scArray*<br/>
in Verweis auf eine Zeichen folgen Array Variable, die die zu speicherbaren Daten enthält.

*dwcArray*<br/>
in Verweis auf eine 32-Bit-Double-Word-Array Variable, die die zu speicherbaren Daten enthält.

*wcArray*<br/>
in Verweis auf eine 16-Bit-Word-Array Variable, die die zu speicherbaren Daten enthält.

*Rect*<br/>
in Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) -Variable, die die zu speicherbaren Daten enthält.

*lpPoint*<br/>
in Verweis auf einen Zeiger auf eine `POINT` Variable, die die Daten enthält, die gespeichert werden sollen.

*pData*<br/>
in Zeiger auf einen Puffer, der die Daten enthält, die gespeichert werden sollen.

*nBytes*<br/>
in Gibt die Größe (in Bytes) der Daten an, auf die der *pData* -Parameter verweist.

*list*<br/>
in Verweis auf eine [CObList](../../mfc/reference/coblist-class.md) -Variable, die die zu Speicher enden Daten enthält.

*obj*<br/>
in Verweis auf eine [CObject](../../mfc/reference/cobject-class.md) -Variable, die die zu speicherbaren Daten enthält.

*pObj*<br/>
in Zeiger auf einen Zeiger auf eine `CObject` Variable, die die zu speicherbaren Daten enthält.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Wenn Sie ein [csettingsstore](../../mfc/reference/csettingsstore-class.md) -Objekt erstellen möchten, müssen Sie beim Erstellen eines csettingsstore-Objekts *Brot nur* auf einen Wert ungleich 0 festlegen. Weitere Informationen finden Sie unter [csettingsstore:: csettingsstore](#csettingsstore).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
