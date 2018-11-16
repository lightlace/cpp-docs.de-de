---
title: CKeyboardManager-Klasse
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
ms.openlocfilehash: d144731d05e861f4b462c4d58022b5155fdeb79b
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694269"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager-Klasse

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
|[CKeyboardManager::CleanUp](#cleanup)|Löscht die tastenkombinationstabellen an.|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Ruft die standardmäßige Tastenkombination für den angegebenen Befehl und das Fenster ab.|
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Bestimmt, ob ein Schlüssel von der tastenkombinationstabelle verarbeitet wird.|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Gibt an, ob ein Zeichen druckbaren ist.|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Gibt an, ob alle Tastenkombinationen für einen Befehl oder nur die standardmäßige Tastenkombination Menüs angezeigt werden.|
|[CKeyboardManager::LoadState](#loadstate)|Lädt die tastenkombinationstabellen aus der Windows-Registrierung.|
|[CKeyboardManager::ResetAll](#resetall)|Lädt die tastenkombinationstabellen aus Ressource für die Anwendung erneut.|
|[CKeyboardManager::SaveState](#savestate)|Speichert die Verknüpfung Tabellen in der Windows-Registrierung.|
|[Ckeyboardmanager](#showallaccelerators)|Gibt an, ob das Framework alle Tastenkombinationen für alle Befehle oder einer einzelnen Tastenkombination für jeden Befehl angezeigt. Diese Methode wirkt sich nicht auf Befehle aus, die nur einen zugeordneten Tastenkombination verfügen.|
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Konvertiert ein Zeichen in der oberen registrieren.|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Eine wichtige Verknüpfung-Tabelle aktualisiert mit einer neuen Verknüpfung-Key-Tabelle.|

## <a name="remarks"></a>Hinweise

Die Member dieser Klasse ermöglichen Ihnen das Speichern und Laden tastenkombinationstabellen an der Windows-Registrierung, mithilfe einer Vorlage um die wichtige Verknüpfung-Tabellen zu aktualisieren, und suchen die standardmäßige Tastenkombination für einen Befehl in einem Rahmenfenster. Darüber hinaus die `CKeyboardManager` -Objekt können Sie steuern, wie die Tastenkombinationen für den Benutzer angezeigt werden.

Erstellen Sie keine `CKeyboardManager` Objekt manuell. Es wird automatisch durch das Framework der Anwendung erstellt werden. Sie sollten jedoch aufrufen [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) während der Initialisierung der Anwendung. Um einen Zeiger auf die Tastatur-Manager für Ihre Anwendung zu erhalten, rufen [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie einen Zeiger zum Abrufen einer `CKeyboardManager` -Objekt aus einer `CWinAppEx` -Klasse, und alle zugeordneten Befehle im Menü Tastenkombinationen anzeigen. Dieser Codeausschnitt ist Teil der [Beispiel für benutzerdefinierte Seiten](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxkeyboardmanager.h

##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager

Erstellt ein `CKeyboardManager`-Objekt.

```
CKeyboardManager();
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen, Sie müssen keine Erstellung einer `CKeyboardManager` direkt. Standardmäßig erstellt das Framework für Sie. Um einen Zeiger auf die `CKeyboardManager`, rufen Sie [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Wenn Sie einen manuell erstellen, müssen Sie es mit der Methode initialisieren [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).

##  <a name="cleanup"></a>  CKeyboardManager::CleanUp

Gibt frei, die `CKeyboardManager` Ressourcen und löscht alle Schlüssel Verknüpfung-Zuordnungen.

```
static void CleanUp();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen zu Tastenkombinationen finden Sie unter [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md).

Sie müssen nicht diese Funktion aufrufen, wenn die Anwendung beendet wird, da das Framework sie beim Beenden der Anwendung automatisch aufruft.

##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator

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
[in] Die Befehls-ID.

*str*<br/>
[out] Ein Verweis auf eine `CString` Objekt.

*pWndFrame*<br/>
[in] Ein Zeiger auf ein Rahmenfenster.

*bIsDefaultFrame*<br/>
[in] Gibt an, ob das Rahmenfenster, das Standard-Rahmenfenster ist.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Verknüpfung gefunden wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode sucht anhand des Befehls *UiCmd* und ruft die standardmäßige Tastenkombination. Die Methode nimmt die Zeichenfolge, die diese Tastenkombination zugeordnet, und schreibt den Wert, der *str* Parameter.

##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled

Bestimmt, ob es sich bei der angegebene Schlüssel von verarbeitet wird die [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md).

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
|*nKey*|[in] Die zu überprüfende Taste.|
|*fVirt*|[in] Gibt das Verhalten der Tastenkombination. Eine Liste der möglichen Werte, finden Sie unter [ACCELERATION Struktur](/windows/desktop/api/winuser/ns-winuser-tagaccel).|
|*pWndFrame*|[in] Ein Rahmenfenster. Diese Methode bestimmt, ob eine Tastenkombination, die in diesem Frame behandelt wird.|
|*bIsDefaultFrame*|[in] Ein boolescher Parameter, der angibt, ob *pWndFrame* ist das Standard-Rahmenfenster.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Tastenkombination behandelt wird. "False", wenn der Schlüssel nicht behandelt wird oder wenn *pWndFrame* ist NULL.

### <a name="remarks"></a>Hinweise

Der Eingabeparameter müssen den Eintrag in der tastenkombinationstabelle sowohl für entsprechen *nKey* und *fVirt* zu bestimmen, ob eine Tastenkombination in erfolgt *pWndFrame*.

##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable

Gibt an, ob ein Zeichen druckbaren ist.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*NChar*|[in] Das Zeichen, das diese Methode überprüft.|

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Zeichen "druckbaren" ist, ist dies nicht.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn ein Aufruf von [GetKeyboardState](/windows/desktop/api/winuser/nf-winuser-getkeyboardstate) ein Fehler auftritt.

##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators

Gibt an, ob alle Befehle im Menü zugeordneten Tastenkombinationen oder nur die Standardtastenkombinationen Menüs angezeigt werden.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Anwendung alle Tastenkombinationen für Befehle im Menü angezeigt werden; 0, wenn die Anwendung nur Standardtastenkombinationen zeigt.

### <a name="remarks"></a>Hinweise

Die Anwendung sind die Tastenkombinationen für Befehle in der Menüleiste im Menü aufgeführt. Verwenden Sie die Funktion [Ckeyboardmanager](#showallaccelerators) steuern, ob die Anwendung listet alle Tastenkombinationen oder nur die standardmäßigen Tastenkombinationen.

##  <a name="loadstate"></a>  CKeyboardManager::LoadState

Lädt die tastenkombinationstabellen aus der Windows-Registrierung.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Im Registrierungspfad befinden, in denen `CKeyboardManager` Daten werden gespeichert.

*pDefaultFrame*<br/>
[in] Ein Zeiger auf ein Rahmenfenster, das als das Standardfenster verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Zustand erfolgreich geladen wurde, oder 0 ist.

### <a name="remarks"></a>Hinweise

Wenn die *LpszProfileName* Parameter NULL ist, diese Methode überprüft den Standardspeicherort für die Registrierung für `CKeyboardManager` Daten. Der Standardspeicherort für die Registrierung wird angegeben, indem die [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md). Die Daten müssen zuvor geschrieben werden, mit der Methode [CKeyboardManager::SaveState](#savestate).

Wenn Sie ein Standardfenster nicht angeben, wird das Hauptrahmenfenster Ihrer Anwendung verwendet werden.

##  <a name="resetall"></a>  CKeyboardManager::ResetAll

Lädt die tastenkombinationstabellen aus Ressource für die Anwendung erneut.

```
void ResetAll();
```

### <a name="remarks"></a>Hinweise

Diese Funktion löscht die Tastenkombinationen, gespeichert der `CKeyboardManager` Instanz. Es wird dann den Status der Ressource für die Anwendung den Manager für die Tastatur neu geladen.

##  <a name="savestate"></a>  CKeyboardManager::SaveState

Speichert die Verknüpfung Tabellen in der Windows-Registrierung.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Der Registrierungspfad zum Speichern der `CKeyboardManager` Zustand.

*pDefaultFrame*<br/>
[in] Ein Zeiger auf ein Rahmenfenster, das den Standardwert wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Zustand der Tastatur-Manager erfolgreich gespeichert wurde oder andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn die *LpszProfileName* Parameter NULL ist, diese Methode schreibt die `CKeyboardManager` am Standardspeicherort, der anhand des Status der [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md). Wenn Sie einen Speicherort angeben, können Sie die Daten, die später mithilfe der-Methode laden [CKeyboardManager::LoadState](#loadstate).

Wenn Sie ein Standardfenster nicht angeben, wird das Hauptrahmenfenster als das Standardfenster verwendet werden.

##  <a name="showallaccelerators"></a>  Ckeyboardmanager

Zeigt alle zugeordneten Befehle im Menü Tastenkombinationen.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>Parameter

*bShowAll*<br/>
[in] Bei TRUE werden alle Tastenkombinationen angezeigt. Wenn "FALSE" werden nur die ersten Tastenkombination angezeigt.

*lpszDelimiter*<br/>
[in] Eine Zeichenfolge, die zwischen Tastenkombinationen eingefügt werden soll. Diese Trennzeichen hat keine Auswirkungen, wenn nur eine Tastenkombination angezeigt wird.

### <a name="remarks"></a>Hinweise

Standardmäßig verfügt ein Befehl mehr als eine Tastenkombination zugeordnet, wird nur die ersten Tastenkombination angezeigt. Diese Funktion können Sie alle Tastenkombinationen zugeordnet alle Befehle auflisten.

Die Tastenkombination gedrückt werden neben den Befehl in der Menüleiste aufgeführt. Wenn die Tastenkombination gedrückt angezeigt werden, wird die Zeichenfolge von bereitgestellten *LpszDelimiter* trennt die einzelnen Tastenkombinationen.

##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper

Konvertiert ein Zeichen in der oberen registrieren.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>Parameter

*NChar*<br/>
[in] Das zu konvertierende Zeichen.

### <a name="return-value"></a>Rückgabewert

Das Zeichen, das den oberen Register des input-Parameters ist.

##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable

Eine wichtige Verknüpfung-Tabelle aktualisiert mit einer neuen Verknüpfung-Key-Tabelle.

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
[in] Ein Zeiger auf eine Dokumentvorlage.

*lpAccel*<br/>
[in] Ein Zeiger auf die neue Zugriffstaste.

*nSize*<br/>
[in] Die Größe der neuen Tabelle Verknüpfung.

*pDefaultFrame*<br/>
[in] Ein Zeiger auf das Standard-Rahmenfenster.

*hAccelNew*<br/>
[in] Ein Handle für die neue Tabelle für die Verknüpfung.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um die vorhandene Verknüpfung-Tabelle mit neuen Tastenkombinationen für verschiedene Windows-Frame-Objekte zu ersetzen. Die Funktion empfängt eine Dokumentvorlage, als Parameter für den Zugriff auf alle Fensterobjekte für Frame mit dem angegebenen Dokument-Vorlage verbunden sind.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)

