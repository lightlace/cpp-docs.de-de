---
title: CDockState-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8cde676795067005406f3eba86bdda7082f272
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435596"
---
# <a name="cdockstate-class"></a>CDockState-Klasse

Eine serialisierte `CObject` -Klasse, die den Zustand einer oder mehrerer andockbarer Steuerleisten in einem persistenten Speicher (eine Datei) lädt, entlädt oder löscht.

## <a name="syntax"></a>Syntax

```
class CDockState : public CObject
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDockState::Clear](#clear)|Löscht die Zustandsinformationen andocken.|
|[CDockState::GetVersion](#getversion)|Ruft die Versionsnummer des gespeicherten Status Leiste.|
|[CDockState::LoadState](#loadstate)|Ruft die Zustandsinformationen aus der Registrierung oder. INI-Datei.|
|[CDockState::SaveState](#savestate)|Speichert Zustandsinformationen der Registrierung oder der INI-Datei.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Array von Zeigern auf den gespeicherten Andocken Zustandsinformationen, die mit einem Eintrag für jede Steuerleiste.|

## <a name="remarks"></a>Hinweise

Die Dock-Status umfasst die Größe und Position der Leiste und davon, ob es angedockt ist. Beim Abrufen von den gespeicherten Zustand, Andocken `CDockState` überprüft des Balkens Position und, wenn die Leiste nicht angezeigt, mit den aktuellen bildschirmeinstellungen wird `CDockState` skaliert des Balkens zu positionieren, damit es sichtbar ist. Der Hauptzweck von `CDockState` besteht darin, den gesamten Status einer Reihe von Steuerleisten speichern und zu diesem Zustand gespeichert werden und entweder in der Registrierungs, die Anwendung geladen. INI-Datei oder in binärer Form im Rahmen einer `CArchive` Inhalt des Objekts.

Die Leiste kann alle andockbaren Balken-, z. B. eine Symbolleiste, die Statusleiste oder die Dialogleiste sein. `CDockState` Objekte werden geschrieben, und liest bis oder aus einer Datei über eine `CArchive` Objekt.

[CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) Ruft ab, die Zustandsinformationen aller des Rahmenfensters `CControlBar` Objekte und versetzt ihn in das `CDockState` Objekt. Anschließend können Sie den Inhalt der Schreiben der `CDockState` Objekt in den Speicher mit [Serialize](../../mfc/reference/cobject-class.md#serialize) oder [CDockState::SaveState](#savestate). Wenn Sie später die Steuerleisten im Rahmenfenster versetzen möchten, können Sie mit der Auslastungstest des Status mit `Serialize` oder [CDockState::LoadState](#loadstate), verwenden Sie dann [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) die gespeicherten anwenden Zustand, der das Rahmenfenster Schiebeleisten-Steuerelemente.

Weitere Informationen zum Andocken Schiebeleisten-Steuerelemente, finden Sie in den Artikeln [Steuerleisten](../../mfc/control-bars.md), [Symbolleisten: andockbare und unverankerte](../../mfc/docking-and-floating-toolbars.md), und [Frame Windows](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>Anforderungen

**Header:** afxadv.h

##  <a name="clear"></a>  CDockState::Clear

Rufen Sie diese Funktion deaktivieren Sie alle Andocken Informationen in den `CDockState` Objekt.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Dies schließt nicht nur, ob die Leiste oder nicht, aber die Größe und Position des Balkens angedockt ist und, und zwar unabhängig davon, ob es angezeigt wird.

##  <a name="getversion"></a>  CDockState::GetVersion

Mit dieser Funktion wird zum Abrufen der Anzahl der Version des gespeicherten Status Leiste.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Rückgabewert

1, wenn die Leiste gespeicherten Informationen ist älter als der aktuelle Strich Zustand 2, wenn die gespeicherte Leiste sind die gleichen Informationen wie die aktuelle Befehlsleiste Zustand.

### <a name="remarks"></a>Hinweise

Versionsunterstützung ermöglicht eine überarbeitete angezeigt, die immer noch in der Lage zu erkennen und zu Laden des persistenten Status, die von einer früheren Version des Balkens erstellt und neue dauerhafte Eigenschaften hinzufügen.

##  <a name="loadstate"></a>  CDockState::LoadState

Mit dieser Funktion wird zum Abrufen von Statusinformationen aus der Registrierung oder. INI-Datei.

```
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
Verweist auf eine Null-Teminated-Zeichenfolge, die gibt den Namen eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, in dem Statusinformationen gespeichert ist.

### <a name="remarks"></a>Hinweise

Der Profilname ist der Teil der Anwendung. INI-Datei oder der Registrierung, die die Balken Zustandsinformationen enthält. Sie können die Steuerleiste Zustandsinformationen in der Registrierung speichern oder. INI-Datei mit `SaveState`.

##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo

Ein `CPtrArray` -Objekt, das ein Array von Zeigern auf die Informationen zur gespeicherten Control Balken für jede Steuerleiste, der Zustandsinformationen in gespeichert ist, wird die `CDockState` Objekt.

```
CPtrArray m_arrBarInfo;
```

##  <a name="savestate"></a>  CDockState::SaveState

Mit dieser Funktion können Sie die Zustandsinformationen in der Registrierung speichern oder. INI-Datei.

```
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
Verweist auf eine Null-Teminated-Zeichenfolge, die gibt den Namen eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, in dem Statusinformationen gespeichert ist.

### <a name="remarks"></a>Hinweise

Der Profilname ist der Teil der Anwendung. INI-Datei oder die Registrierung enthält, die Statusinformationen der Steuerleiste. `SaveState` speichert auch die Größe des aktuellen Bildschirms. Sie können die Leiste Informationen abrufen, aus der Registrierung oder. INI-Datei mit `LoadState`.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

