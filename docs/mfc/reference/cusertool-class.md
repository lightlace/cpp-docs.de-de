---
title: Cusertool-Klasse
ms.date: 11/04/2016
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
ms.openlocfilehash: b73cb3d3c6e244a9aa41a91a3ee9ff1efa98d496
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502245"
---
# <a name="cusertool-class"></a>Cusertool-Klasse

Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Die Registerkarte **Tools** des Dialog Felds **Anpassen** ( [cmfctoolbarscustomizedialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) ermöglicht dem Benutzer, Benutzer Tools hinzuzufügen und den Namen, den Befehl, die Argumente und das ursprüngliche Verzeichnis für jedes Benutzer Tool anzugeben.

## <a name="syntax"></a>Syntax

```
class CUserTool : public CObject
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||
|[CUserTool::DrawToolIcon](#drawtoolicon)|Zeichnet das Benutzer Tool Symbol in einem angegebenen Rechteck.|
|[CUserTool::GetCommand](#getcommand)|Gibt eine Zeichenfolge zurück, die den Text des Befehls enthält, der dem Benutzer Tool zugeordnet ist.|
|[CUserTool::GetCommandId](#getcommandid)|Gibt die Befehls-ID des Menü Elements des Benutzer Tools zurück.|
|[CUserTool::Invoke](#invoke)|Führt den Befehl aus, der dem Benutzer Tool zugeordnet ist.|
|[CUserTool::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CUserTool::SetCommand](#setcommand)|Legt den dem Benutzer Tool zugeordneten Befehl fest.|
|[CUserTool::SetToolIcon](#settoolicon)|Lädt das Symbol für das Benutzer Tool aus der Anwendung, die mit dem Tool verknüpft ist.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Lädt das Standard Symbol für ein Benutzer Tool.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|Die Befehlszeilenargumente für das Benutzer Tool.|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Das Ausgangs Verzeichnis für das Benutzer Tool.|
|[CUserTool::m_strLabel](#m_strlabel)|Der ToolName, der im Menü Element für das Tool angezeigt wird.|

## <a name="remarks"></a>Hinweise

Weitere Informationen zum Aktivieren von Benutzer Tools in der Anwendung finden Sie unter [cusertoolsmanager-Klasse](../../mfc/reference/cusertoolsmanager-class.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Tool aus einem `CUserToolsManager` -Objekt erstellt, `m_strLabel` die Element Variable festgelegt und die Anwendung festgelegt wird, die vom Benutzer Tool ausgeführt wird. Dieser Code Ausschnitt ist Teil des [Visual Studio-Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxusertool. h

##  <a name="copyicontoclipboard"></a>Cusertool:: copyiconumclipboard

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="drawtoolicon"></a>Cusertool::D rawumolicon

Zeichnet das Benutzer Tool Symbol in der Mitte eines angegebenen Rechtecks.

```
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*rectImage*<br/>
in Gibt die Koordinaten des Bereichs an, in dem das Symbol angezeigt werden soll.

##  <a name="getcommand"></a>Cusertool:: GetCommand

Gibt eine Zeichenfolge zurück, die den Text des Befehls enthält, der dem Benutzer Tool zugeordnet ist.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf `CString` das-Objekt, das den Text des Befehls enthält, der dem Benutzer Tool zugeordnet ist.

##  <a name="getcommandid"></a>Cusertool:: getcommandid

Gibt die Befehls-ID des Benutzer Tools zurück.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Rückgabewert

Die Befehls-ID dieses Benutzer Tools.

##  <a name="invoke"></a>Cusertool:: aufrufen

Führt den Befehl aus, der dem Benutzer Tool zugeordnet ist.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Befehl erfolgreich ausgeführt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Ruft [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) auf, um einen Befehl auszuführen, der mit dem Benutzer Tool verknüpft ist. Die Funktion schlägt fehl, wenn der Befehl leer ist oder wenn [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) fehlschlägt.

##  <a name="loaddefaulticon"></a>Cusertool:: loaddefaulticon

Lädt das Standard Symbol für ein Benutzer Tool.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das geladene Symbol (HICON) oder NULL, wenn das Standard Symbol nicht geladen werden kann.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn es nicht möglich ist, ein Symbol für ein benutzerdefiniertes Tool aus der ausführbaren Datei des Tools zu laden.

Überschreiben Sie diese Methode, um ein eigenes Standard Tool Symbol bereitzustellen.

##  <a name="m_strarguments"></a>Cusertool:: m_strArguments

Die Befehlszeilenargumente für das Benutzer Tool.

```
CString m_strArguments;
```

### <a name="remarks"></a>Hinweise

Diese Zeichenfolge wird an das Tool übermittelt, wenn Sie [cusertool:: Aufrufen](#invoke) aufrufen oder wenn ein Benutzer auf den Befehl klickt, der mit diesem Tool verknüpft ist.

##  <a name="m_strinitialdirectory"></a>Cusertool:: m_strInitialDirectory

Gibt das Ausgangs Verzeichnis für das Benutzer Tool an.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Hinweise

Diese Variable gibt das Ausgangs Verzeichnis an, in dem das Tool ausgeführt wird, wenn Sie [cusertool:: Aufrufen](#invoke) aufrufen oder wenn ein Benutzer auf den Befehl klickt, der diesem Tool zugeordnet ist.

##  <a name="m_strlabel"></a>Cusertool:: m_strLabel

Die Bezeichnung, die im Menü Element für das Tool angezeigt wird.

```
CString m_strLabel;
```

##  <a name="serialize"></a>Cusertool:: Serialize

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

[in] *ar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setcommand"></a>Cusertool:: SetCommand

Legt die Anwendung fest, die das Benutzer Tool ausführt.

```
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Parameter

*lpszCmd*<br/>
in Gibt die neue Anwendung an, die dem Benutzer Tool zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie eine neue Anwendung festlegen, die vom Benutzer Tool ausgeführt wird. Die-Methode zerstört das alte Symbol und lädt ein neues Symbol aus der angegebenen Anwendung. Wenn ein Symbol nicht aus der Anwendung geladen werden kann, wird das Standard Symbol für ein Benutzer Tool geladen, indem [cusertool:: loaddefaulticon](#loaddefaulticon)aufgerufen wird.

##  <a name="settoolicon"></a>Cusertool:: setdeolicon

Lädt das Symbol für das Benutzer Tool aus der Anwendung, die vom Tool verwendet wird.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das geladene Symbol.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird das Symbol geladen, das auf dem Menü Element angezeigt werden soll. Diese Methode sucht nach dem Symbol in der ausführbaren Datei, die vom Tool verwendet wird. Wenn Sie nicht über ein Standard Symbol verfügt, wird stattdessen das von [cusertool:: loaddefaulticon](#loaddefaulticon) bereitgestellte Symbol verwendet.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)<br/>
[CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md)
