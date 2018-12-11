---
title: CWinFormsControl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: e8728c876badcf6648740cc842a1f289789bf0f4
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178238"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl-Klasse

Stellt die grundlegende Funktionalität zum Hosten eines Windows Forms-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>Parameter

*TManagedControl*<br/>
Ein .NET Framework Windows Forms-Steuerelement in der MFC-Anwendung angezeigt werden.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Erstellt ein Wrapperobjekt für MFC-Windows Forms-Steuerelement.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Erstellt ein Windows Forms-Steuerelement in einem MFC-Container an.|
|[CWinFormsControl::GetControl](#getcontrol)|Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Ruft ein Handle für das Windows Forms-Steuerelement ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Ersetzt [CWinFormsControl::GetControl](#getcontrol) in Ausdrücken.|
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.|

## <a name="remarks"></a>Hinweise

Die `CWinFormsControl` Klasse stellt die grundlegende Funktionalität für das Hosten eines Windows Forms-Steuerelements bereit.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

MFC-Code sollte nicht zwischenspeichern Fensterhandles (gespeichert in der Regel `m_hWnd`). Einige Windows Forms-Steuerelementeigenschaften benötigen, die die zugrunde liegende Win32 `Window` zerstört und neu erstellt, mit `DestroyWindow` und `CreateWindow`. Die Ziehpunkte der MFC-Windows Forms-Implementierung der `Destroy` und `Create` Ereignisse der Steuerelemente zum Aktualisieren der `m_hWnd` Member.

> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpfen (in der Bezeichnung definiert ist).

## <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h

##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl

Erstellt ein Windows Forms-Steuerelement in einem MFC-Container an.

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>Parameter

*PGeben*<br/>
Der Datentyp des Steuerelements erstellt werden. Muss eine [Typ](https://msdn.microsoft.com/library/system.type) -Datentyp.

*dwStyle*<br/>
Der Fensterstil, um auf das Steuerelement angewendet werden soll. Geben Sie eine Kombination von [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Derzeit werden nur die folgenden Formate unterstützt: WS_TABSTOP "," WS_VISIBLE "," WS_DISABLED "und" WS_GROUP ".

*Rect*<br/>
Ein [RECT-Struktur](/windows/desktop/api/windef/ns-windef-tagrect) , die die Koordinaten der oberen linken und rechten unteren Ecke des Steuerelements definiert (nur erste Überladung).

*nPlaceHolderID*<br/>
Das Handle des Steuerelements Inhaber statische Stelle platziert der Ressourcen-Editor. Das neu erstellte Windows Forms-Steuerelement ersetzt das statische-Steuerelement, wenn seine Position, die Z-Reihenfolge und die Stile (nur zweite Überladung).

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Fenster.

*nID*<br/>
Die Ressourcen-ID-Nummer, die neu erstellte Steuerelement zugewiesen werden soll.

*pControl*<br/>
Eine Instanz eines Windows Forms-Steuerelements zugeordnet werden die [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) -Objekt (nur für die vierte Überladung).

### <a name="return-value"></a>Rückgabewert

Im Erfolgsfall gibt einen Wert ungleich NULL zurück. Wenn Fehler auftreten, gibt Sie 0 (null) zurück.

### <a name="remarks"></a>Hinweise

Diese Methode instanziiert ein .NET Framework Windows Forms-Steuerelement in einem MFC-Container.

Die erste Überladung der Methode akzeptiert einen .NET Framework-Datentyp *PGeben* so, dass MFC ein neues Objekt dieses Typs instanziiert werden kann. *PGeben* muss eine [Typ](https://msdn.microsoft.com/library/system.type) -Datentyp.

Die zweite Überladung der Methode erstellt ein Windows Forms-Steuerelement, das auf der Grundlage der `TManagedControl` Template-Parameter, der die `CWinFormsControl` Klasse. Die Größe und Position des Steuerelements basiert auf der `RECT` Struktur, die an die Methode übergeben. Nur *DwStyle* ist wichtig für die Formate.

Die dritte Überladung der Methode erstellt ein Windows Forms-Steuerelement, das ein statisches Steuerelement zerstören und übernimmt dessen Position, die Z-Reihenfolge und die Stile ersetzt. Statische Steuerelement dient nur als Platzhalter für das Windows Forms-Steuerelement. Wenn Sie das Steuerelement zu erstellen, kombiniert diese Überladung der Stile aus *DwStyle* mit des statischen Steuerelements Ressource Stilen.

Die vierte Überladung der Methode können Sie eine bereits instanziierte Windows Forms-Steuerelement übergeben *pControl* , die MFC umbrochen wird. Es muss vom gleichen Typ wie die `TManagedControl` Template-Parameter, der die `CWinFormsControl` Klasse.

Finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) Beispiele zur Verwendung von Windows-Formular steuert.

##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl

Erstellt ein Wrapperobjekt für MFC-Windows Forms-Steuerelement.

```
CWinFormsControl();
```

### <a name="remarks"></a>Hinweise

Das Windows Forms-Steuerelement instanziiert wird, beim Aufrufen [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).

##  <a name="getcontrol"></a>  CWinFormsControl::GetControl

Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das Windows Forms-Steuerelement.

### <a name="example"></a>Beispiel

  Finden Sie unter [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).

##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle

Ruft ein Handle für das Windows Forms-Steuerelement ab.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle auf das Windows Forms-Steuerelement zurück.

### <a name="remarks"></a>Hinweise

`GetControlHandle` ist eine Hilfsmethode, die das Fensterhandle, das in die .NET Framework-Steuerelementeigenschaften gespeicherten zurückgibt. In den Wert für das Handle kopiert [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) während des Aufrufs von [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).

##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;

Ersetzt [CWinFormsControl::GetControl](#getcontrol) in Ausdrücken.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Hinweise

Dieser Operator bietet eine praktische Syntax, die ersetzt `GetControl` in Ausdrücken.

Weitere Informationen zu Windows Forms, finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^

Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Hinweise

Dieser Operator übergibt `CWinFormsControl<TManagedControl>` für Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement zu akzeptieren.

## <a name="see-also"></a>Siehe auch

[CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)
