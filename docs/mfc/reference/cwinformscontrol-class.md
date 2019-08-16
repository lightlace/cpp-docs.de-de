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
ms.openlocfilehash: 75a6d7ea2b4f3ab229d7e3f4d411711261bb1b82
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502197"
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
Ein .NET Framework Windows Forms Steuerelement, das in der MFC-Anwendung angezeigt werden soll.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Erstellt ein MFC-Windows Forms Steuerelement-Wrapper Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Erstellt ein Windows Forms-Steuerelement in einem MFC-Container.|
|[CWinFormsControl::GetControl](#getcontrol)|Ruft einen Zeiger auf das Windows Forms Steuerelement ab.|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Ruft ein Handle für das Windows Forms Steuerelement ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsControl:: Operator-&gt;](#operator_-_gt)|Ersetzt [CWinFormsControl:: GetControl](#getcontrol) in Ausdrücken.|
|[CWinFormsControl:: Operator tmanagedcontrol ^](#operator_tmanagedcontrol)|Wandelt einen Typ als Zeiger in ein Windows Forms Steuerelement um.|

## <a name="remarks"></a>Hinweise

Die `CWinFormsControl` -Klasse stellt die grundlegende Funktionalität für das Hosting eines Windows Forms-Steuer Elements bereit.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Der MFC-Code sollte keine Fenster Handles Zwischenspeichern (in `m_hWnd`der Regel in gespeichert). Einige Windows Forms-Steuerelement Eigenschaften erfordern, dass `Window` das zugrunde liegende Win32-Element `DestroyWindow` zerstört `CreateWindow`und mithilfe von und neu erstellt wird. Die MFC `Destroy` -Windows Forms Implementierung behandelt die `Create` -und-Ereignisse der-Steuer `m_hWnd` Elemente, um den Member zu aktualisieren.

> [!NOTE]
>  Die MFC-Windows Forms Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft sind (in dem AFXDLL definiert ist).

## <a name="requirements"></a>Anforderungen

**Header:** afxwinforms. h

##  <a name="createmanagedcontrol"></a>CWinFormsControl:: kreatemanagedcontrol

Erstellt ein Windows Forms-Steuerelement in einem MFC-Container.

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

*pType*<br/>
Der Datentyp des zu erstellenden Steuer Elements. Muss ein [Type](/dotnet/api/system.type) -Datentyp sein.

*dwStyle*<br/>
Der Fenster Stil, der auf das Steuerelement angewendet werden soll. Geben Sie eine Kombination von [Fenster Stilen](../../mfc/reference/styles-used-by-mfc.md#window-styles)an. Zurzeit werden nur die folgenden Stile unterstützt: WS_TABSTOP, WS_VISIBLE, WS_DISABLED und WS_GROUP.

*Rect*<br/>
Eine [Rect-Struktur](/windows/win32/api/windef/ns-windef-rect) , die die Koordinaten der oberen linken und der unteren rechten Ecke des Steuer Elements definiert (nur die erste Überladung).

*nPlaceHolderID*<br/>
Das Handle des Steuer Elements für die statische Platzhalter, das in den Ressourcen-Editor eingefügt wird. Das neu erstellte Windows Forms Steuerelement ersetzt das statische Steuerelement, wobei seine Position, die z-Reihenfolge und Stile (nur zweite Überladung) angenommen werden.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Fenster.

*nID*<br/>
Die Ressourcen-ID-Nummer, die dem neu erstellten Steuerelement zugewiesen werden soll.

*pControl*<br/>
Eine Instanz eines Windows Forms Steuer Elements, das dem [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) -Objekt zugeordnet werden soll (nur vierte Überladung).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ein Wert ungleich 0 (null) zurückgegeben. Wenn nicht erfolgreich, wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode instanziiert eine .NET Framework Windows Forms-Steuerelement in einem MFC-Container.

Die erste Überladung der-Methode akzeptiert einen .NET Framework Datentyp *pType* , damit MFC ein neues Objekt dieses Typs instanziieren kann. *pType* muss ein [Type](/dotnet/api/system.type) -Datentyp sein.

Die zweite Überladung der-Methode erstellt ein Windows Forms-Steuerelement `TManagedControl` basierend auf dem template `CWinFormsControl` -Parameter der-Klasse. Größe und Position des-Steuer Elements basieren auf der `RECT` -Struktur, die an die-Methode weitergegeben wird. Nur *dwstyle* ist für die Stile wichtig.

Die dritte Überladung der-Methode erstellt ein Windows Forms Steuerelement, das ein statisches Steuerelement ersetzt, es zerstört und seine Position, z-Reihenfolge und Stile annimmt. Das statische Steuerelement dient nur als Platzhalter für das Windows Forms Steuerelement. Wenn Sie das Steuerelement erstellen, kombiniert diese Überladung die Stile von *dwstyle* mit den Ressourcen Stilen des statischen Steuer Elements.

Mit der vierten Überladung der-Methode können Sie eine bereits instanziierte Windows Forms Steuerelement- *pcontrol* übergeben, die von MFC umschlossen wird. Er muss denselben Typ aufweisen wie der `TManagedControl` Vorlagen Parameter `CWinFormsControl` der-Klasse.

Beispiele zur Verwendung von Windows Forms-Steuerelementen finden [Sie unter Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) .

##  <a name="cwinformscontrol"></a>CWinFormsControl:: CWinFormsControl

Erstellt ein MFC-Windows Forms Steuerelement-Wrapper Objekt.

```
CWinFormsControl();
```

### <a name="remarks"></a>Hinweise

Das Windows Forms Steuerelement wird instanziiert, wenn Sie [CWinFormsControl:: foratemanagedcontrol](#createmanagedcontrol)aufrufen.

##  <a name="getcontrol"></a>CWinFormsControl:: GetControl

Ruft einen Zeiger auf das Windows Forms Steuerelement ab.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das Windows Forms Steuerelement zurück.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie unter [CWinFormsControl:: kreatemanagedcontrol](#createmanagedcontrol).

##  <a name="getcontrolhandle"></a>CWinFormsControl:: getcontrolhandle

Ruft ein Handle für das Windows Forms Steuerelement ab.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für das Windows Forms Steuerelement zurück.

### <a name="remarks"></a>Hinweise

`GetControlHandle`ist eine Hilfsmethode, die das Fenster Handle zurückgibt, das in den Eigenschaften des .NET Framework Steuer Elements gespeichert ist. Der Fenster Handle-Wert wird beim [CWnd:: Attach](../../mfc/reference/cwnd-class.md#attach)-Befehl in [CWnd:: m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) kopiert.

##  <a name="operator_-_gt"></a>CWinFormsControl:: Operator-&gt;

Ersetzt [CWinFormsControl:: GetControl](#getcontrol) in Ausdrücken.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Hinweise

Dieser Operator stellt eine bequeme Syntax bereit, `GetControl` die in Ausdrücken ersetzt.

Weitere Informationen zu Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzer Steuer Elements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_tmanagedcontrol"></a>CWinFormsControl:: Operator tmanagedcontrol ^

Wandelt einen Typ als Zeiger in ein Windows Forms Steuerelement um.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Hinweise

Dieser Operator übergibt `CWinFormsControl<TManagedControl>` an Funktionen, die einen Zeiger auf ein Windows Forms Steuerelement akzeptieren.

## <a name="see-also"></a>Siehe auch

[CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)
