---
title: CUserTool-Klasse
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
ms.openlocfilehash: 5bb0ae073b722c97e8e30158f8f7832fd88b2fbc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779039"
---
# <a name="cusertool-class"></a>CUserTool-Klasse

Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Die **Tools** auf der Registerkarte die **anpassen** (Dialogfeld) ( [CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) ermöglicht es dem Benutzer, Benutzertools hinzuzufügen, und geben den Namen, den Befehl, die Argumente und ursprüngliche Verzeichnis für jedes benutzertool.

## <a name="syntax"></a>Syntax

```
class CUserTool : public CObject
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||
|[CUserTool::DrawToolIcon](#drawtoolicon)|Zeichnet das Symbol für Benutzer in einem bestimmten Rechteck.|
|[CUserTool::GetCommand](#getcommand)|Gibt eine Zeichenfolge mit dem Text des Befehls mit dem benutzertool verknüpft ist.|
|[CUserTool::GetCommandId](#getcommandid)|Gibt die Befehls-ID des Menüelements des Benutzer-Tools zurück.|
|[CUserTool::Invoke](#invoke)|Führt den Befehl mit dem benutzertool verknüpft ist.|
|[CUserTool::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CUserTool::SetCommand](#setcommand)|Legt fest, den das benutzertool zugeordneten Befehl.|
|[CUserTool::SetToolIcon](#settoolicon)|Lädt das Symbol für das benutzertool von der Anwendung verknüpft ist, mit dem Tool an.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Lädt das Standardsymbol für ein Tool an.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|Die Befehlszeilenargumente für das benutzertool.|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Das Ausgangsverzeichnis für das benutzertool.|
|[CUserTool::m_strLabel](#m_strlabel)|Der Name des Tools, die in das Menüelement für das Tool angezeigt wird.|

## <a name="remarks"></a>Hinweise

Weitere Informationen dazu, wie Sie die Benutzertools für in Ihrer Anwendung ermöglichen, finden Sie unter [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie Sie ein Tool erstellt eine `CUserToolsManager` -Objekts die `m_strLabel` Membervariablen gespeichert, und legen Sie die Anwendung, die die benutzertool ausgeführt wird. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxusertool.h

##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon

Zeichnet das Symbol für Benutzer in der Mitte der einem bestimmten Rechteck.

```
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*rectImage*<br/>
[in] Gibt die Koordinaten des Bereichs, um das Symbol anzuzeigen.

##  <a name="getcommand"></a>  CUserTool::GetCommand

Gibt eine Zeichenfolge mit dem Text des Befehls mit dem benutzertool verknüpft ist.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf `CString` -Objekt, das den Text des Befehls verknüpft ist, mit dem benutzertool enthält.

##  <a name="getcommandid"></a>  CUserTool::GetCommandId

Gibt die Befehls-ID des Benutzers Tools zurück.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Rückgabewert

Die Befehls-ID des Benutzers Tools.

##  <a name="invoke"></a>  CUserTool::Invoke

Führt den Befehl mit dem benutzertool verknüpft ist.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Befehl erfolgreich ausgeführt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Aufrufe [ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea) zum Ausführen eines Befehls mit dem benutzertool verknüpft ist. Die Funktion schlägt fehl, wenn der Befehl leer ist oder wenn [ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea) ein Fehler auftritt.

##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon

Lädt das Standardsymbol für ein Tool an.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Laden des Symbols (HICON) oder NULL, wenn das Symbol "Standard" kann nicht geladen werden.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn sie ein Symbol für ein benutzerdefiniertes Tool aus der ausführbaren Datei des Tools laden kann.

Überschreiben Sie diese Methode, um Ihre eigenen Standardsymbol für das Tool angeben.

##  <a name="m_strarguments"></a>  CUserTool::m_strArguments

Die Befehlszeilenargumente für das benutzertool.

```
CString m_strArguments;
```

### <a name="remarks"></a>Hinweise

Diese Zeichenfolge wird an das Tool übergeben, wenn Sie aufrufen [CUserTool::Invoke](#invoke) oder wenn ein Benutzer mit diesem Tool zugeordneten Befehl klickt.

##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory

Gibt an, das ursprüngliche Verzeichnis für das benutzertool.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Hinweise

Diese Variable gibt an, das Ausgangsverzeichnis, die in das Tool, beim Aufrufen ausführt [CUserTool::Invoke](#invoke) oder wenn ein Benutzer mit diesem Tool zugeordneten Befehl klickt.

##  <a name="m_strlabel"></a>  CUserTool::m_strLabel

Die Bezeichnung, die in das Menüelement für das Tool angezeigt wird.

```
CString m_strLabel;
```

##  <a name="serialize"></a>  CUserTool::Serialize

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

[in] *ar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setcommand"></a>  CUserTool::SetCommand

Legt fest, die Anwendung, die die benutzertool ausgeführt wird.

```
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Parameter

*lpszCmd*<br/>
[in] Gibt die neue Anwendung mit dem benutzertool zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um eine neue Anwendung festlegen, die die benutzertool ausgeführt wird. Die Methode zerstört das alte Symbol und ein neues Symbol aus der angegebenen Anwendung lädt. Wenn sie ein Symbol aus der Anwendung nicht geladen werden kann, laden Sie das Standardsymbol für ein Tool durch Aufrufen von [CUserTool::LoadDefaultIcon](#loaddefaulticon).

##  <a name="settoolicon"></a>  CUserTool::SetToolIcon

Lädt das Symbol für das benutzertool von der Anwendung, die vom Tool verwendet wird.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle auf das Symbol geladen werden soll.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Laden des Symbols, das auf das Menüelement angezeigt werden. Diese Methode sucht das Symbol in die ausführbare Datei, die vom Tool verwendet wird. Wenn sie nicht über ein Standardsymbol verfügt, wird das Symbol von bereitgestellten [CUserTool::LoadDefaultIcon](#loaddefaulticon) wird stattdessen verwendet.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)<br/>
[CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md)
