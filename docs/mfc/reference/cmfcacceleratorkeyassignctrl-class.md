---
title: CMFCAcceleratorKeyAssignCtrl-Klasse
ms.date: 10/18/2018
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
ms.openlocfilehash: 5e57bf149fdbc293692c613afcabcf2d11d32221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505471"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl-Klasse

Die `CMFCAcceleratorKeyAssignCtrl` -Klasse erweitert die [CEdit-Klasse](../../mfc/reference/cedit-class.md) , um zusätzliche System Schaltflächen wie alt, Control und Shift zu unterstützen.

## <a name="syntax"></a>Syntax

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcacceleratorkeyzuzuzutragstrg:: cmfcacceleratorkeyzuzuzuordnung](#cmfcacceleratorkeyassignctrl)|Erstellt ein `CMFCAcceleratorKeyAssignCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Ruft die `ACCEL`-Struktur für eine im `CMFCAcceleratorKeyAssignCtrl`-Objekt gedrückte Tastenkombination ab.|
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Bestimmt, ob eine Tastenkombination definiert wurde.|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Setzt die Tastenkombination zurück.|

## <a name="remarks"></a>Hinweise

Diese Klasse erweitert die Funktionalität der `CEdit`-Klasse, indem Sie Unterstützung von Tastenkombinationen hinzufügt, auch bekannt als Zugriffstasten. Die `CMFCAcceleratorKeyAssignCtrl` -Klasse fungiert als [CEdit-Klasse](../../mfc/reference/cedit-class.md) und kann auch System Schaltflächen erkennen.

Diese Klasse ordnet Zeichenfolgenwerten physische Tastenkombinationen zu. Angenommen die Tastenkombination ALT+B ist der Zeichenfolge „Alt + B“ zugeordnet. Wenn der Benutzer diese Tastenkombination in einem `CMFCAcceleratorKeyAssignCtrl`-Objekt drückt, wird ihm „Alt+B“ angezeigt. Weitere Informationen zur Zuordnung zwischen Tastenkombinationen und einem Zeichen folgen Format finden Sie unter [cmfcacceleratorkey-Klasse](../../mfc/reference/cmfcacceleratorkey-class.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAcceleratorKeyAssignCtrl`-Objekts und die Verwendung der `ResetKey`-Methode zum Zurücksetzen der Tastenkombination.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxacceleratorkeyzuzuzutragstrg. h

##  <a name="cmfcacceleratorkeyassignctrl"></a>Cmfcacceleratorkeyzuzuzutragstrg:: cmfcacceleratorkeyzuzuzuordnung

Erstellt ein [cmfcacceleratorkeyzuzuzurichtstrg](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) -Objekt.

```
CMFCAcceleratorKeyAssignCtrl();
```

##  <a name="getaccel"></a>Cmfcacceleratorkeyzuzuzutragstrg:: GetAccel

Ruft die `ACCEL` -Struktur für eine Tastenkombination ab, die im [cmfcacceleratorkeyzuzu-](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Objekt gedrückt wurde.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Rückgabewert

Eine `ACCEL` -Struktur, die die Tastenkombination beschreibt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um `ACCEL` die Struktur für eine Tastenkombination abzurufen, die der Benutzer `CMFCAcceleratorKeyAssignCtrl` in Ihr Objekt eingegeben hat.

##  <a name="isfocused"></a>Cmfcacceleratorkeyzuzuzutragstrg:: isfokussiert

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="iskeydefined"></a>Cmfcacceleratorkeyzuzuzutragstrg:: iskeydefined

Bestimmt, ob eine Tastenkombination im [cmfcacceleratorkeyzuzu-](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Objekt definiert wurde.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn der Benutzer bereits eine gültige Tastenkombination gedrückt hat, die eine Tastenkombination definiert. andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um zu bestimmen, ob der Benutzer eine gültige Tasten `CMFCAcceleratorKeyAssignCtrl` Kombination in das Objekt eingegeben hat. Wenn eine Tastenkombination vorhanden ist, können Sie die [cmfcacceleratorkeyzuzuordnermethode](#getaccel) verwenden, um die Struktur `ACCEL` abzurufen, die dieser Tastenkombination zugeordnet ist.

##  <a name="pretranslatemessage"></a>Cmfcacceleratorkeyzuzutragstrg::P retranslatemess Age

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parameter

[in] *pMsg*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="resetkey"></a>Cmfcacceleratorkeyzuzuzutragstrg:: Resetkey

Setzt die Tastenkombination zurück.

```
void ResetKey();
```

### <a name="remarks"></a>Hinweise

Die-Funktion löscht den Bearbeitungs Steuerelement Text. Dies schließt alle Tastenkombinationen ein, die der Benutzer gedrückt hat.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey-Klasse](../../mfc/reference/cmfcacceleratorkey-class.md)
