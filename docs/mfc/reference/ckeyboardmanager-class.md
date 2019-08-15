---
title: Ckeyboardmanager-Klasse
ms.date: 11/04/2016
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
ms.openlocfilehash: e4f8f678e76113b5d012242f474ff0ab8b0628dd
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505780"
---
# <a name="ckeyboardmanager-class"></a>Ckeyboardmanager-Klasse

Verwaltet Tastenkombinationstabellen für das Hauptrahmenfenster und die untergeordneten Rahmenfenster.

## <a name="syntax"></a>Syntax

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Erstellt ein `CKeyboardManager`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CKeyboardManager::CleanUp](#cleanup)|Löscht die Tastenkombinationen.|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Ruft die standardmäßige Tastenkombination für den angegebenen Befehl und das Fenster ab.|
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Bestimmt, ob ein Schlüssel von der Zugriffstasten Tabelle behandelt wird.|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Gibt an, ob ein Zeichen druckbar ist.|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Gibt an, ob Menüs alle Tastenkombinationen für einen Befehl oder nur die standardmäßige Tastenkombination anzeigen.|
|[CKeyboardManager::LoadState](#loadstate)|Lädt die Tastenkombinationen aus der Windows-Registrierung.|
|[CKeyboardManager::ResetAll](#resetall)|Lädt die Verknüpfungs Schlüsseltabellen aus der Anwendungs Ressource erneut.|
|[CKeyboardManager::SaveState](#savestate)|Speichert die Tastenkombinationen in der Windows-Registrierung.|
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Gibt an, ob das Framework alle Tastenkombinationen für alle Befehle oder eine einzelne Tastenkombination für jeden Befehl anzeigt. Diese Methode wirkt sich nicht auf Befehle aus, die nur über eine verknüpfte Tastenkombination verfügen.|
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Konvertiert ein Zeichen in das obere Register.|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Aktualisiert eine Tastenkombination mit einer neuen Tastenkombination.|

## <a name="remarks"></a>Hinweise

Die Member dieser Klasse ermöglichen es Ihnen, Tastenkombinationen in der Windows-Registrierung zu speichern und zu laden, eine Vorlage zum Aktualisieren der Kurztaste zu verwenden und die standardmäßige Tastenkombination für einen Befehl in einem Rahmen Fenster zu suchen. Außerdem können Sie mit `CKeyboardManager` dem-Objekt steuern, wie Tastenkombinationen für den Benutzer angezeigt werden.

Ein `CKeyboardManager` -Objekt sollte nicht manuell erstellt werden. Sie wird automatisch vom Framework der Anwendung erstellt. Sie sollten jedoch beim Initialisierungs Prozess der Anwendung [CWinAppEx:: initkeyboardmanager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) aufrufen. Rufen Sie [CWinAppEx:: getkeyboardmanager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)auf, um einen Zeiger auf den Tastatur-Manager für Ihre Anwendung zu erhalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Zeiger auf ein `CKeyboardManager` -Objekt aus `CWinAppEx` einer-Klasse abgerufen wird und wie alle mit Menübefehlen verknüpften Tastenkombinationen angezeigt werden. Dieser Code Ausschnitt ist Teil des Beispiels für [benutzerdefinierte Seiten](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxkeyboardmanager. h

##  <a name="ckeyboardmanager"></a>Ckeyboardmanager:: ckeyboardmanager

Erstellt ein `CKeyboardManager`-Objekt.

```
CKeyboardManager();
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen ist es nicht erforderlich, einen `CKeyboardManager` direkt zu erstellen. Standardmäßig erstellt das Framework eines. Rufen Sie `CKeyboardManager` [CWinAppEx:: getkeyboardmanager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)auf, um einen Zeiger auf den zu erhalten. Wenn Sie einen manuell erstellen, müssen Sie ihn mit der-Methode [CWinAppEx:: initkeyboardmanager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)initialisieren.

##  <a name="cleanup"></a>Ckeyboardmanager:: Cleanup

Gibt die `CKeyboardManager` Ressourcen frei und löscht alle Zuordnungen von Tastenkombinationen.

```
static void CleanUp();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen zu Tastenkombinationen finden Sie unter [Tastatur-und Maus Anpassung](../../mfc/keyboard-and-mouse-customization.md).

Sie müssen diese Funktion nicht aufrufen, wenn die Anwendung beendet wird, da Sie vom Framework beim Beenden der Anwendung automatisch aufgerufen wird.

##  <a name="finddefaultaccelerator"></a>Ckeyboardmanager:: finddefaultaccelerator

Ruft die standardmäßige Tastenkombination für den angegebenen Befehl und das Fenster ab.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID.

*str*<br/>
vorgenommen Ein Verweis auf ein `CString` -Objekt.

*pWndFrame*<br/>
in Ein Zeiger auf ein Rahmen Fenster.

*bIsDefaultFrame*<br/>
in Gibt an, ob das Rahmen Fenster das Standardrahmen Fenster ist.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Verknüpfung gefunden wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode sucht den von *uicmd* angegebenen Befehl und ruft die standardmäßige Tastenkombination ab. Dann nimmt die Methode die mit dieser Tastenkombination verknüpfte Zeichenfolge an und schreibt den Wert in den *Str* -Parameter.

##  <a name="iskeyhandled"></a>Ckeyboardmanager:: iskeybehandelte

Bestimmt, ob der angegebene Schlüssel von der [ckeyboardmanager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)behandelt wird.

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*nKey*|in Der zu Überprüfung Ende Schlüssel.|
|*fVirt*|in Gibt das Verhalten der Tastenkombination an. Eine Liste möglicher Werte finden Sie unter [Accel Structure](/windows/win32/api/winuser/ns-winuser-accel).|
|*pWndFrame*|in Ein Rahmen Fenster. Diese Methode bestimmt, ob eine Tastenkombination in diesem Frame behandelt wird.|
|*bIsDefaultFrame*|in Ein boolescher Parameter, der angibt, ob *pWndFrame* das Standardrahmen Fenster ist.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Tastenkombination behandelt wird. FALSE, wenn der Schlüssel nicht behandelt wird oder *pWndFrame* NULL ist.

### <a name="remarks"></a>Hinweise

Die Eingabeparameter müssen dem Eintrag in der Zugriffstasten Tabelle für *nkey* und *fvirt* entsprechen, um zu bestimmen, ob eine Tastenkombination in *pWndFrame*behandelt wird.

##  <a name="iskeyprintable"></a>Ckeyboardmanager:: iskeyprint

Gibt an, ob ein Zeichen druckbar ist.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*nChar*|in Das Zeichen, das von dieser Methode überprüft wird.|

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Zeichen druckbar ist, andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn beim Aufrufen von [GetKeyboardState](/windows/win32/api/winuser/nf-winuser-getkeyboardstate) ein Fehler auftritt.

##  <a name="isshowallaccelerators"></a>Ckeyboardmanager:: isshowallaccelerators

Gibt an, ob Menüs alle Tastenkombinationen anzeigen, die Menübefehlen zugeordnet sind, oder nur die Standardtasten Kombinationen.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Anwendung alle Tastenkombinationen für Menübefehle auflistet. 0, wenn in der Anwendung nur Standardtasten Kombinationen angezeigt werden.

### <a name="remarks"></a>Hinweise

Die Anwendung listet die Tastenkombinationen für Menübefehle in der Menüleiste auf. Verwenden Sie die Funktion [ckeyboardmanager:: showallaccelerators](#showallaccelerators) , um zu steuern, ob die Anwendung alle Tastenkombinationen oder nur die Standardtasten Kombinationen auflistet.

##  <a name="loadstate"></a>Ckeyboardmanager:: LoadState

Lädt die Tastenkombinationen aus der Windows-Registrierung.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
in Der Registrierungs Pfad, `CKeyboardManager` in dem Daten gespeichert werden.

*pDefaultFrame*<br/>
in Ein Zeiger auf ein Rahmen Fenster, das als Standardfenster verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Zustand erfolgreich geladen wurde, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn der *lpszprofilename* -Parameter NULL ist, überprüft diese Methode den standardmäßigen Registrierungs `CKeyboardManager` Speicherort für Daten. Der Standard Registrierungs Speicherort wird von der [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)angegeben. Die Daten müssen bereits mit der Methode [ckeyboardmanager:: SaveState](#savestate)geschrieben werden.

Wenn Sie kein Standardfenster angeben, wird das Hauptrahmen Fenster der Anwendung verwendet.

##  <a name="resetall"></a>Ckeyboardmanager:: ResetAll

Lädt die Verknüpfungs Schlüsseltabellen aus der Anwendungs Ressource erneut.

```
void ResetAll();
```

### <a name="remarks"></a>Hinweise

Diese Funktion löscht die in der `CKeyboardManager` -Instanz gespeicherten Verknüpfungen. Anschließend wird der Status des Tastatur-Managers von der Anwendungs Ressource erneut geladen.

##  <a name="savestate"></a>Ckeyboardmanager:: SaveState

Speichert die Tastenkombinationen in der Windows-Registrierung.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
in Der Registrierungs Pfad zum Speichern des `CKeyboardManager` Zustands.

*pDefaultFrame*<br/>
in Ein Zeiger auf ein Rahmen Fenster, das zum Standardfenster wird.

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn der Zustand des Tastatur-Managers erfolgreich gespeichert wurde, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn der *lpszprofilename* -Parameter NULL ist, schreibt diese Methode den `CKeyboardManager` Zustand in den Standard Speicherort, der von der [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)angegeben wird. Wenn Sie einen Speicherort angeben, können Sie die Daten später mithilfe der Methode [ckeyboardmanager:: LoadState](#loadstate)laden.

Wenn Sie kein Standardfenster angeben, wird das Hauptrahmen Fenster als Standardfenster verwendet.

##  <a name="showallaccelerators"></a>Ckeyboardmanager:: showallaccelerators

Zeigt alle Tastenkombinationen an, die Menübefehlen zugeordnet sind.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Parameter

*bShowAll*<br/>
in TRUE gibt an, dass alle Tastenkombinationen angezeigt werden. Wenn der Wert false ist, wird nur die erste Tastenkombination angezeigt.

*lpszDelimiter*<br/>
in Eine Zeichenfolge, die zwischen Tastenkombinationen eingefügt werden soll. Dieses Trennzeichen hat keine Auswirkung, wenn nur eine Tastenkombination angezeigt wird.

### <a name="remarks"></a>Hinweise

Wenn einem Befehl mehr als eine Tastenkombination zugeordnet ist, wird standardmäßig nur die erste Tastenkombination angezeigt. Mit dieser Funktion können Sie alle Tastenkombinationen auflisten, die mit allen Befehlen verknüpft sind.

Die Tastenkombinationen werden neben dem Befehl in der Menüleiste aufgeführt. Wenn alle Tastenkombinationen angezeigt werden, werden die einzelnen Tastenkombinationen durch die von *lpszdelimiter* bereitgestellte Zeichenfolge getrennt.

##  <a name="translatechartoupper"></a>Ckeyboardmanager:: translatechartoupper

Konvertiert ein Zeichen in das obere Register.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Parameter

*nChar*<br/>
in Das zu konvertierende Zeichen.

### <a name="return-value"></a>Rückgabewert

Das Zeichen, das das obere Register des Eingabe Parameters ist.

##  <a name="updateacceltable"></a>Ckeyboardmanager:: updateacceltable

Aktualisiert eine Tastenkombination mit einer neuen Tastenkombination.

```
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    LPACCEL lpAccel,
    int nSize,
    CFrameWnd* pDefaultFrame = NULL);

BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    HACCEL hAccelNew,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parameter

*pTemplate*<br/>
in Ein Zeiger auf eine Dokument Vorlage.

*lpAccel*<br/>
in Ein Zeiger auf die neue Tastenkombination.

*nSize*<br/>
in Die Größe der neuen Verknüpfungs Tabelle.

*pDefaultFrame*<br/>
in Ein Zeiger auf das Standardrahmen Fenster.

*hAccelNew*<br/>
in Ein Handle für die neue Verknüpfungs Tabelle.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Methode erfolgreich ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um die vorhandene Verknüpfungs Tabelle durch neue Tastenkombinationen für mehrere Rahmen Fenster Objekte zu ersetzen. Die Funktion empfängt eine Dokument Vorlage als Parameter, um Zugriff auf alle Rahmen Fenster Objekte zu erhalten, die mit der angegebenen Dokument Vorlage verbunden sind.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)
