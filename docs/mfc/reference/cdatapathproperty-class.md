---
title: CDataPathProperty-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 89cb8ddcdd42643f52f755516e8845109163c57a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780339"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty-Klasse

Implementiert eine OLE-Steuerelementeigenschaft, die asynchron geladen werden kann.

## <a name="syntax"></a>Syntax

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Erstellt ein `CDataPathProperty`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDataPathProperty::GetControl](#getcontrol)|Ruft ab, der asynchrone zugeordnete OLE-Steuerelement die `CDataPathProperty` Objekt.|
|[CDataPathProperty::GetPath](#getpath)|Ruft den Pfadnamen der Eigenschaft ab.|
|[CDataPathProperty::Open](#open)|Initialisiert das Laden der asynchrone Eigenschaft für das zugeordnete Steuerelement von ActiveX-(OLE).|
|[CDataPathProperty::ResetData](#resetdata)|Aufrufe `CAsyncMonikerFile::OnDataAvailable` des Containers zu benachrichtigen, dass die Eigenschaften des Steuerelements geändert haben.|
|[CDataPathProperty::SetControl](#setcontrol)|Legt das asynchrone ActiveX-(OLE)-Steuerelement, das der Eigenschaft zugeordnet.|
|[CDataPathProperty::SetPath](#setpath)|Legt den Pfadnamen der Eigenschaft fest.|

## <a name="remarks"></a>Hinweise

Asynchrone Eigenschaften werden nach der Initiierung der synchronen geladen.

Die Klasse `CDataPathProperty` ergibt sich aus `CAysncMonikerFile`. Um die asynchrone Eigenschaften in die OLE-Steuerelemente zu implementieren, leiten Sie eine Klasse von `CDataPathProperty`, und überschreiben [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).

Weitere Informationen zur Verwendung von asynchronen Monikern und ActiveX-Steuerelementen in Internet-Anwendungen finden Sie unter den folgenden Artikeln:

- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)

- [Internetgrundlagen: Asynchroner Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty

Erstellt ein `CDataPathProperty`-Objekt.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parameter

*pControl*<br/>
Ein Zeiger auf das OLE-Steuerelementobjekt einen zugeordnet werden soll `CDataPathProperty` Objekt.

*lpszPath*<br/>
Der Pfad, der absolut oder relativ sein kann, verwendet, um die ein asynchrones Monikers zu erstellen, das die tatsächlichen absolute Position der Eigenschaft verweist. `CDataPathProperty` verwendet nicht die Dateinamen-URLs. Wenn Sie möchten eine `CDataPathProperty` Objekt für eine Datei, voranstellen `file://` auf den Pfad.

### <a name="remarks"></a>Hinweise

Die `COleControl` Objekt verweist *pControl* dient der `Open` und von abgeleiteten Klassen abgerufen. Wenn *pControl* NULL ist, das Steuerelement ab, mit `Open` sollten nastavit mit `SetControl`. Wenn *LpszPath* NULL ist, können Sie den Pfad durch übergeben `Open` oder legen Sie sie mit `SetPath`.

##  <a name="getcontrol"></a>  CDataPathProperty::GetControl

Rufen Sie diese Memberfunktion zum Abrufen der `COleControl` zugeordnete Objekt der `CDataPathProperty` Objekt.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Zeiger auf das OLE-Steuerelement zugeordnete der `CDataPathProperty` Objekt. NULL, wenn nicht-Steuerelement ist zugeordnet.

##  <a name="getpath"></a>  CDataPathProperty::GetPath

Rufen Sie diese Memberfunktion zum Abrufen des Pfads festgelegt, wenn die `CDataPathProperty` Objekt erstellt wurde, oder in angegebenen `Open`, oder in einem vorherigen Aufruf von der `SetPath` Member-Funktion.

```
CString GetPath() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt den Pfadnamen für die Eigenschaft selbst zurück. Kann leer sein, wenn kein Pfad angegeben wurde.

##  <a name="open"></a>  CDataPathProperty::Open

Rufen Sie diese Memberfunktion zum Laden der asynchrone Eigenschaft für das zugeordnete Steuerelement einleiten.

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*pControl*<br/>
Ein Zeiger auf das OLE-Steuerelementobjekt einen zugeordnet werden soll `CDataPathProperty` Objekt.

*pError*<br/>
Ein Zeiger auf eine Ausnahme für die Datei. Im Falle eines Fehlers werden um die Ursache festgelegt.

*lpszPath*<br/>
Der Pfad, der absolut oder relativ sein kann, verwendet, um die ein asynchrones Monikers zu erstellen, das die tatsächlichen absolute Position der Eigenschaft verweist. `CDataPathProperty` verwendet nicht die Dateinamen-URLs. Wenn Sie möchten eine `CDataPathProperty` Objekt für eine Datei, voranstellen `file://` auf den Pfad.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die Funktion versucht, erhalten die `IBindHost` Schnittstelle aus dem Steuerelement.

Vor dem Aufruf `Open` ohne Pfad, der Wert für den Pfad von der Eigenschaft muss festgelegt werden. Dies ist möglich, wenn das Objekt erstellten, oder durch Aufrufen der `SetPath` Member-Funktion.

Vor dem Aufruf `Open` ohne ein Steuerelement, ein ActiveX-Steuerelement (früher als OLE-Steuerelements) dem Objekt zugeordnet werden kann. Dies ist möglich, wenn das Objekt erstellten, oder durch Aufrufen von `SetControl`.

Alle Überladungen der [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) stehen Ihnen auf `CDataPathProperty`.

##  <a name="resetdata"></a>  CDataPathProperty::ResetData

Mit dieser Funktion wird zum Abrufen `CAsyncMonikerFile::OnDataAvailable` um dem Container zu benachrichtigen, dass die Eigenschaften des Steuerelements geändert haben, und alle Informationen, die asynchron geladen nicht mehr nützlich ist.

```
virtual void ResetData();
```

### <a name="remarks"></a>Hinweise

Öffnen, sollte neu gestartet werden. Abgeleitete Klassen können diese Funktion für unterschiedliche Standardeinstellungen überschreiben.

##  <a name="setcontrol"></a>  CDataPathProperty::SetControl

Rufen Sie diese Memberfunktion zum Zuordnen eines asynchronen OLE-Steuerelements mit der `CDataPathProperty` Objekt.

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Parameter

*pControl*<br/>
Ein Zeiger auf den asynchronen OLE-Steuerelements die Eigenschaft zugeordnet werden soll.

##  <a name="setpath"></a>  CDataPathProperty::SetPath

Rufen Sie diese Memberfunktion um den Pfadnamen der Eigenschaft festzulegen.

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Parameter

*lpszPath*<br/>
Ein Pfad, der möglicherweise absolut oder relativ sein, auf die Eigenschaft, die asynchron geladen werden. `CDataPathProperty` verwendet nicht die Dateinamen-URLs. Wenn Sie möchten eine `CDataPathProperty` Objekt für eine Datei, voranstellen `file://` auf den Pfad.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-Bild](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)
