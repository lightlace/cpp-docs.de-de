---
title: CFindReplaceDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: de48d8f495802bdf1c5f69e7a4edc41153c9599f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206012"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog-Klasse

Können Sie Standardzeichenfolge in Dateien suchen/ersetzen-Dialogfelder in Ihrer Anwendung zu implementieren.

## <a name="syntax"></a>Syntax

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Mit dieser Funktion wird zum Erstellen einer `CFindReplaceDialog` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFindReplaceDialog::Create](#create)|Erstellt und zeigt eine `CFindReplaceDialog` Dialogfeld.|
|[CFindReplaceDialog::FindNext](#findnext)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das nächste Vorkommen des Suchbegriffs suchen möchte.|
|[CFindReplaceDialog::GetFindString](#getfindstring)|Rufen Sie diese Funktion zum Abrufen des aktuellen Suchbegriffs suchen.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Mit dieser Funktion wird zum Abrufen der `FINDREPLACE` Struktur Ihrer registrierten Nachrichtenhandler.|
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Rufen Sie diese Funktion zum Abrufen der aktuellen Ersetzungszeichenfolge.|
|[CFindReplaceDialog::IsTerminating](#isterminating)|Rufen Sie diese Funktion, um zu bestimmen, ob das Dialogfeld beendet wird.|
|[CFindReplaceDialog::MatchCase](#matchcase)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte die Groß-/Kleinschreibung die Suchzeichenfolge genau übereinstimmen.|
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte nur ganze Wörter abzugleichen.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer alle Vorkommen der Zeichenfolge, die ersetzt werden soll.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das aktuelle Wort ersetzt werden soll.|
|[CFindReplaceDialog::SearchDown](#searchdown)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer die Suche nach unten durchgeführt fortsetzen möchte.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFindReplaceDialog::m_fr](#m_fr)|Eine Struktur, die zum Anpassen einer `CFindReplaceDialog` Objekt.|

## <a name="remarks"></a>Hinweise

Im Gegensatz zu den anderen Windows Standarddialogfelder `CFindReplaceDialog` Objekte sind nicht modales, Benutzer können mit anderen Fenstern interagieren, während sie sich auf dem Bildschirm befinden. Es gibt zwei Arten von `CFindReplaceDialog` Objekte: Suchen Sie die angezeigten Dialogfelder und Dialogfelder in Dateien suchen/ersetzen. Obwohl Sie die Dialogfelder den Benutzer Eingabe-Search "und" Suchen/Ersetzen-Zeichenfolgen können, führen sie keine Suchvorgänge oder Ersetzen von Funktionen aus. Sie müssen diese für die Anwendung hinzufügen.

Zum Erstellen einer `CFindReplaceDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor (die keine Argumente verfügt). Da es sich um ein nicht modales Dialogfeld handelt, ordnen Sie das Objekt auf dem Heap mit dem **neue** -Operator, und nicht auf dem Stapel.

Einmal eine `CFindReplaceDialog` -Objekts, rufen Sie die [erstellen](#create) Member-Funktion zum Erstellen und das Dialogfeld anzuzeigen.

Verwenden der [M_fr](#m_fr) Struktur zum Initialisieren des Dialogfelds vor dem Aufruf `Create`. Die `m_fr` Struktur ist vom Typ [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.

In der Reihenfolge für das übergeordnete Fenster, in Dateien suchen/ersetzen-Anforderungen benachrichtigt zu werden, müssen Sie die Windows verwenden [RegisterWindowMessage registriert](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) -Funktion und die Nutzung der [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) meldungszuordnung Makro in Ihrem Frame Fenster, das diese registrierte Meldung verarbeitet.

Sie können bestimmen, ob der Benutzer entschieden hat, um das Dialogfeld zu beenden. die `IsTerminating` Member-Funktion.

`CFindReplaceDialog` basiert auf der COMMDLG. DLL-Datei, die in Windows-Versionen 3.1 und höher enthalten ist.

Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFindReplaceDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelementen zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten in der Basisklasse übergeben werden.

Anpassen der Hookfunktion ist nicht erforderlich.

Weitere Informationen zur Verwendung von `CFindReplaceDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxdlgs.h

##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog

Erstellt ein `CFindReplaceDialog`-Objekt.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>Hinweise

Da die `CFindReplaceDialog` Objekt ist ein nicht modales Dialogfeld, müssen Sie es auf dem Heap mit erstellen die **neue** Operator.

Während der Zerstörung, versucht das Framework zum Ausführen einer **löschen** auf den Zeiger auf das Dialogfeld. Wenn Sie im Dialogfeld auf den Stapel, erstellt die **dies** Zeiger ist nicht vorhanden und kann zu nicht definiertem Verhalten führen.

Um mehr über die Erstellung von `CFindReplaceDialog` Objekten finden Sie die [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) Übersicht. Verwenden der [CFindReplaceDialog::Create](#create) Memberfunktion, um das Dialogfeld anzuzeigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

##  <a name="create"></a>  CFindReplaceDialog::Create

Erstellt und zeigt eine suchen oder in Dateien suchen/ersetzen Dialogfeldobjekt abhängig vom Wert `bFindDialogOnly`.

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*bFindDialogOnly*<br/>
Legen Sie diesen Parameter auf "true" zum Anzeigen einer **finden** Dialogfeld. Legen Sie sie auf "false" zum Anzeigen einer **Suchen/Ersetzen** Dialogfeld.

*lpszFindWhat*<br/>
Zeiger auf die Suchzeichenfolge Standardwert, wenn das Dialogfeld wird angezeigt. Wenn der Wert NULL ist, enthält das Dialogfeld keine Suchzeichenfolge ein Standardwert.

*lpszReplaceWith*<br/>
Zeiger auf die Ersetzungszeichenfolge standardmäßigen, wenn das Dialogfeld wird angezeigt. Wenn der Wert NULL ist, enthält das Dialogfeld keine Ersetzungszeichenfolge standardmäßigen.

*dwFlags*<br/>
Ein oder mehrere Flags, die Sie, zum Anpassen der Einstellungen im Dialogfeld verwenden können, mit dem bitweisen OR-Operator kombiniert. Der Standardwert ist FR_DOWN, der angibt, dass bei der Suche wird die weitere Vorgehensweise nach unten durchgeführt. Finden Sie unter den [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea) Struktur im Windows SDK für Weitere Informationen zu diesen Flags.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Element oder Besitzer des Dialogfelds-Fenster. Dies ist das Fenster, das erhält die Sondermeldung gibt an, dass eine Suchen/Ersetzen-Aktion angefordert wird. Wenn der Wert NULL ist, wird das Hauptfenster der Anwendung verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Dialogfeld wurde erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

In der Reihenfolge für das übergeordnete Fenster, in Dateien suchen/ersetzen-Anforderungen benachrichtigt zu werden, müssen Sie die Windows verwenden [RegisterWindowMessage registriert](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) Funktion, deren Rückgabewert ist die Nummer einer Anwendungsinstanz eindeutig. Ihr Rahmenfenster müssen einen Zuordnungseintrag für Nachrichten, die die Callback-Funktion deklariert ( `OnFindReplace` in das folgende Beispiel), die diese registrierten Nachricht verarbeitet. Das folgende Codefragment ist ein Beispiel für ein Rahmenfenster (Klasse) mit dem Namen `CMyRichEditView`:

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

Innerhalb Ihrer `OnFindReplace` -Funktion interpretiert die Absicht des Benutzers mithilfe der [CFindReplaceDialog::FindNext](#findnext) und [CFindReplaceDialog::IsTerminating](#isterminating) Methoden und Sie den Code zu erstellen für die Suchen/Ersetzen-Vorgänge.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

##  <a name="findnext"></a>  CFindReplaceDialog::FindNext

Rufen Sie diese Funktion aus Ihrer Callback-Funktion, um festzustellen, ob der Benutzer das nächste Vorkommen der Suchzeichenfolge suchen möchte.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Benutzer das nächste Vorkommen der Suchzeichenfolge suchen möchte; andernfalls 0.

##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString

Rufen Sie diese Funktion aus Ihrer Callback-Funktion, um die Standardeinstellung, die zu suchende Zeichenfolge abzurufen.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Rückgabewert

Die Standardzeichenfolge gefunden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier

Rufen Sie diese Funktion, um einen Zeiger auf das aktuelle Dialogfeld Suchen und Ersetzen abzurufen.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*lParam*<br/>
Die *Lparam* Wert übergeben wird, an des Rahmenfensters `OnFindReplace` Member-Funktion.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das aktuelle Dialogfeld.

### <a name="remarks"></a>Hinweise

Es sollte für den Zugriff auf das aktuelle Dialogfeld Aufrufen seiner Member, Funktionen und Zugriff in Ihrer Callback-Funktion verwendet werden die `m_fr` Struktur.

### <a name="example"></a>Beispiel

Finden Sie unter [CFindReplaceDialog::Create](#create) für ein Beispiel für die Benachrichtigungen über das Dialogfeld Suchen und Ersetzen OnFindReplace Handler registriert werden.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString

Rufen Sie diese Funktion zum Abrufen der aktuellen Ersetzungszeichenfolge.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Rückgabewert

Die Standardzeichenfolge mit der gefundene Zeichenfolgen ersetzt werden soll.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CFindReplaceDialog::GetFindString](#getfindstring).

##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating

Rufen Sie diese Funktion in Ihrer Callback-Funktion, um festzustellen, ob der Benutzer entschieden hat, um das Dialogfeld zu beenden.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Benutzer entschieden hat, um das Dialogfeld zu beenden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn diese Funktion ungleich NULL zurückgibt, sollten Sie Aufrufen der `DestroyWindow` Memberfunktion der aktuellen Dialogfeld ein, und alle Zeigervariable der Dialogfeld-Feld auf NULL festgelegt. Sie können optional auch den zuletzt eingegebenen Suchen/Ersetzen-Text speichern und verwenden, um im nächsten Suchen/Ersetzen-Dialogfeld zu initialisieren.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CFindReplaceDialog::GetFindString](#getfindstring).

##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr

Zum Anpassen einer `CFindReplaceDialog` Objekt.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>Hinweise

`m_fr` ist eine Struktur vom Typ [FINDREPLACE](/windows/desktop/api/commdlg/ns-commdlg-tagfindreplacea). Member speichern Sie die Eigenschaften des Objekts im Dialogfeld. Nach dem Erstellen einer `CFindReplaceDialog` -Objekts verwenden Sie `m_fr` verschiedene Werte im Dialogfeld ändern.

Weitere Informationen zu dieser Struktur finden Sie unter den `FINDREPLACE` Struktur im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).

##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte die Groß-/Kleinschreibung die Suchzeichenfolge genau übereinstimmen.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Benutzer möchte, um Vorkommen der Suchzeichenfolge zu suchen, die die zu suchende Zeichenfolge die Groß-/Kleinschreibung genau übereinstimmen; andernfalls 0.

##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte nur ganze Wörter abzugleichen.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Benutzer möchte nur die ganze Wörter der Suchzeichenfolge abzugleichen; andernfalls 0.

##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer alle Vorkommen der Zeichenfolge, die ersetzt werden soll.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Benutzer angefordert hat, dass alle Zeichenfolgen, die übereinstimmende die Ersetzungszeichenfolge ersetzt; andernfalls 0.

##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das aktuelle Wort ersetzt werden soll.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Benutzer angefordert hat, die derzeit ausgewählte Zeichenfolge mit die Ersetzungszeichenfolge ersetzt werden; andernfalls 0.

##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown

Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer die Suche nach unten durchgeführt fortsetzen möchte.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Benutzer die Suche nach unten fortfahren soll; 0, wenn der Benutzer die Suche nach oben fortsetzen möchte.

## <a name="see-also"></a>Siehe auch

[CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
