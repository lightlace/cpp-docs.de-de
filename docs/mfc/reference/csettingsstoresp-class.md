---
title: CSettingsStoreSP-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 5c7a992b983552340ebe21e59d2ee9a667841ec0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339521"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP-Klasse

Die `CSettingsStoreSP` Klasse ist eine Hilfsklasse, die Sie, zum Erstellen von Instanzen von verwenden können der [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).

## <a name="syntax"></a>Syntax

```
class CSettingsStoreSP
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Erstellt ein `CSettingsStoreSP`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSettingsStoreSP::Create](#create)|Erstellt eine Instanz einer Klasse, die von abgeleitet ist `CSettingsStore`.|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Festlegen der Common Language Runtime-Klasse. Die `Create` Methode verwendet die Common Language Runtime-Klasse, um zu bestimmen, welche Klasse von Objekten zu erstellen.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|`m_dwUserData`|Benutzerdefinierte Daten, die in gespeichert ist die `CSettingsStoreSP` Objekt. Diese Daten in den Konstruktor der Angabe der `CSettingsStoreSP` Objekt.|
|`m_pRegistry`|Die `CSettingsStore`-abgeleitete Objekt, das `Create` -Methode erstellt.|

## <a name="remarks"></a>Hinweise

Sie können die `CSettingsStoreSP` Klasse, um alle MFC-Registrierungsvorgängen an andere Speicherorte, z. B. eine XML-Datei oder einer Datenbank umleiten. Führen Sie dazu folgende Schritte aus:

1. Erstellen Sie eine Klasse (z. B. `CMyStore`) und leiten sie von `CSettingsStore`.

1. Verwendung [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) und [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) Makros mit Ihrer benutzerdefinierten `CSettingsStore` -Klasse zur Aktivierung der dynamischen Erstellung.

1. Die virtuellen Funktionen überschreiben und Implementieren der `Read` und `Write` Funktionen in Ihre benutzerdefinierte Klasse. Implementieren Sie alle sonstigen Funktionen, die zum Lesen und Schreiben von Daten in den gewünschten Speicherort.

1. Rufen Sie in Ihrer Anwendung `CSettingsStoreSP::SetRuntimeClass` und übergeben Sie einen Zeiger auf die [CRuntimeClass-Struktur](../../mfc/reference/cruntimeclass-structure.md) von Ihrer Klasse abgerufen.

Wenn das Framework in der Regel die Registrierung zugreifen würden, es jetzt dynamisch Ihre benutzerdefinierte Klasse zu instanziieren und verwenden, um die Daten lesen oder schreiben.

`CSettingsStoreSP::SetRuntimeClass` verwendet eine globale statische Variable. Daher ist nur einen benutzerdefinierten Speicher zu einem Zeitpunkt zur Verfügung.

## <a name="requirements"></a>Anforderungen

**Header:** afxsettingsstore.h

##  <a name="create"></a>  CSettingsStoreSP::Create

Erstellt eine neue Instanz eines Objekts, das von abgeleitet ist die [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parameter

*bAdmin*<br/>
[in] Ein boolescher Parameter, der bestimmt, ob eine `CSettingsStore` Objekt erstellt wird, im Administratormodus.

*bReadOnly*<br/>
[in] Ein boolescher Parameter, der bestimmt, ob eine `CSettingsStore` Objekt wird für nur-Lese Zugriff erstellt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das neu erstellte `CSettingsStore` Objekt.

### <a name="remarks"></a>Hinweise

Sie können die Methode [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) um zu bestimmen, welche Art von Objekt `CSettingsStoreSP::Create` erstellt. Diese Methode erstellt standardmäßig eine `CSettingsStore` Objekt.

Bei der Erstellung einer `CSettingsStore` Objekt im Administratormodus der Standardspeicherort für alle Zugriff auf die Registrierung ist HKEY_LOCAL_MACHINE. Andernfalls ist der Standardspeicherort für alle Registrierungszugriff HKEY_CURRENT_USER.

Wenn *bAdminpfad* ist "true", die Anwendung muss über Administratorrechte verfügen. Andernfalls schlägt sie fehl, wenn er versucht, auf die Registrierung zugreifen.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode der `CSettingsStoreSP` Klasse.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP

Erstellt eine [CSettingsStoreSP-Klasse](../../mfc/reference/csettingsstoresp-class.md) Objekt.

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*dwUserData*<br/>
[in] Benutzerdefinierte Daten, die die `CSettingsStoreSP` -Objekt speichert.

### <a name="remarks"></a>Hinweise

Die `CSettingsStoreSP` Objekt speichert die Daten aus *DwUserData* in der geschützten Membervariablen `m_dwUserData`.

##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass

Festlegen der Common Language Runtime-Klasse. Die Methode [CSettingsStoreSP::Create](#create) verwendet die Common Language Runtime-Klasse, um zu bestimmen, welche Art des zu erstellenden Objekts.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>Parameter

*pRTI*<br/>
[in] Ein Zeiger auf die laufzeitklasseninformationen für eine Klasse abgeleitet wird, aus der [CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md).

### <a name="return-value"></a>Rückgabewert

True, wenn erfolgreich; FALSE, wenn die Klasse durch identifiziert *pRTI* stammt nicht aus `CSettingsStore`.

### <a name="remarks"></a>Hinweise

Sie können die [CSettingsStoreSP-Klasse](../../mfc/reference/csettingsstoresp-class.md) zum Ableiten von Klassen aus `CSettingsStore`. Verwenden Sie die Methode `SetRuntimeClass` sollten Sie Objekte einer benutzerdefinierten Klasse erstellen, die abgeleitet wird `CSettingsStore`.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore-Klasse](../../mfc/reference/csettingsstore-class.md)
