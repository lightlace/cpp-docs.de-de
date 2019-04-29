---
title: 'TN006: Meldungszuordnungen'
ms.date: 06/25/2018
f1_keywords:
- vc.messages.maps
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
ms.openlocfilehash: 3536cb215da04fb7114853d3fa5d764585cbb58e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306143"
---
# <a name="tn006-message-maps"></a>TN006: Meldungszuordnungen

In diesem Hinweis wird beschrieben, die MFC-Nachricht-Map-Funktion.

## <a name="the-problem"></a>Das Problem

Microsoft Windows implementiert virtuelle Funktionen in Klassen, die die messaging-Funktion nutzen zu können. Aufgrund der großen Anzahl von Nachrichten beteiligt ist wird eine separate virtuelle Funktion für jede Windows-Meldung bereitstellen eine sehr große Vtable erstellt.

Da die Anzahl der systemeigenen Windows-Meldungen im Laufe der Zeit ändert, und Nachricht zugeordnet, da Anwendungen ihre eigenen Windows-Nachrichten definieren können wird, bieten Sie ein Maß an Dereferenzierung, die verhindert, dass Änderungen an der Benutzeroberfläche vorhandener Code.

## <a name="overview"></a>Übersicht

MFC bietet eine Alternative zum der Switch-Anweisung, die in herkömmlichen Windows-basierten Programmen verwendet wurde, um Nachrichten an ein Fenster zu behandeln. Eine Zuordnung von Nachrichten an Methoden kann definiert werden, sodass Wenn eine Nachricht von einem Fenster empfangen wird, automatisch die entsprechende Methode aufgerufen wird. Diese meldungszuordnung Funktion soll virtuelle Funktionen ähneln, jedoch bietet weitere Vorteile, die mit virtuellen Funktionen für C++ nicht möglich.

## <a name="defining-a-message-map"></a>Definieren einer Meldungszuordnung

Die [DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) Makro wird drei Member einer Klasse deklariert.

- Wird aufgerufen, ein privates Array von AFX_MSGMAP_ENTRY Einträge *_messageEntries*.

- Wird aufgerufen, eine geschützte AFX_MSGMAP Struktur *MessageMap* , verweist auf die *_messageEntries* Array.

- Eine geschützte virtuelle Funktion wird aufgerufen, `GetMessageMap` , die die Adresse zurückgibt *MessageMap*.

Dieses Makro sollten in der Deklaration einer Klasse, die mit meldungszuordnungen abgelegt werden. Gemäß der Konvention ist es am Ende der Klassendeklaration. Zum Beispiel:

```cpp
class CMyWnd : public CMyParentWndClass
{
    // my stuff...

protected:
    //{{AFX_MSG(CMyWnd)
    afx_msg void OnPaint();
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};
```

Dies ist das Format von AppWizard und ClassWizard generiert werden, wenn sie neue Klassen zu erstellen. Die / / {{und / /}} ClassWizard Klammern erforderlich sind.

Die meldungszuordnung-Tabelle wird definiert, mit einem Satz von Makros, die auf Meldungszuordnungseinträge erweitern. Eine Tabelle beginnt mit einem [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro-Aufruf, der definiert, die Klasse, die durch diese nachrichtenzuordnung verarbeitet wird und die übergeordnete Klasse, die nicht verarbeitete Nachrichten übergeben werden. In der Tabelle endet mit dem [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) Makro-Aufruf.

Ist Sie ein Eintrag für jede Nachricht von diesem meldungszuordnung behandelt werden, zwischen diesen beiden Makro aufrufen. Jede standard-Windows-Nachricht ist ein Makro des Formulars ON_WM_*MESSAGE_NAME* Objekt, das einen Eintrag für diese Nachricht generiert.

Eine Signatur für die standard-Funktion wurde für die Parameter der einzelnen Windows-Nachrichten zu entpacken und typsicherheit definiert. Diese Signaturen finden Sie in der Datei Afxwin.h in der Deklaration der [CWnd](../mfc/reference/cwnd-class.md). Jeder ist mit dem Schlüsselwort gekennzeichnet **Afx_msg** zur leichteren Identifizierung.

> [!NOTE]
> Klassen-Assistent setzt voraus, dass Sie die **Afx_msg** -Schlüsselwort in die Nachricht Map-Handler-Deklarationen.

Diese Signaturen von aktivitätsfunktionen wurden mithilfe einer einfachen Konvention abgeleitet. Der Name der Funktion beginnt immer mit `"On`". Dies folgt den Namen der Windows-Meldung mit der "WM_" entfernt und dem ersten Buchstaben jedes Worts in Großbuchstaben angegeben. Die Reihenfolge der Parameter ist *wParam* gefolgt von `LOWORD`(*lParam*) klicken Sie dann `HIWORD`(*lParam*). Nicht verwendete Parameter werden nicht übergeben. Alle Handles, die von MFC-Klassen umschlossen werden, werden in Zeiger auf die entsprechenden MFC-Objekte konvertiert. Das folgende Beispiel zeigt, wie die WM_PAINT-Meldung zu behandeln und dazu führen, dass die `CMyWnd::OnPaint` Funktion aufgerufen werden:

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

Die Message-Zuordnungstabelle muss außerhalb des Bereichs von jeder Funktions- oder Klassendefinition definiert werden. Sie sollten nicht in einem Extern "C"-Block abgelegt werden.

> [!NOTE]
> Klassen-Assistent ändert die Meldungszuordnungseinträge, die zwischen der / / {{und / /}} Kommentar Klammer.

## <a name="user-defined-windows-messages"></a>Benutzerdefinierte Windows-Meldungen

Benutzerdefinierte Meldungen können in einer meldungszuordnung enthalten sein, mit der [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) Makro. Dieses Makro akzeptiert einer Meldungsnummer und eine Methode des Formulars:

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

In diesem Beispiel erstellen wir einen Handler für eine benutzerdefinierte Meldung, die eine Windows-Nachrichten-ID, die die standardmäßige WM_USER-Basis für benutzerdefinierte Meldungen abgeleitet wurde. Das folgende Beispiel zeigt, wie dieser Handler aufgerufen wird:

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

Der Bereich der benutzerdefinierten Nachrichten, die diesen Ansatz verwenden, muss im Bereich WM_USER bis 0x7fff sein.

> [!NOTE]
> Klassen-Assistent unterstützt keine Eingabe ON_MESSAGE Handlerroutinen über die Klassen-Assistenten-Benutzeroberfläche. Sie müssen diese manuell aus dem Visual C++-Editor eingeben. Klassen-Assistent diese Einträge analysiert und lassen Sie diese genau wie alle anderen Meldungszuordnungseinträge durchsuchen.

## <a name="registered-windows-messages"></a>Registrierte Windows-Meldungen

Die [RegisterWindowMessage registriert](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) Funktion wird verwendet, um eine neue Fensternachricht zu definieren, die garantiert im gesamten System eindeutig sein. Das ON_REGISTERED_MESSAGE-Makro wird verwendet, um diese Nachrichten zu verarbeiten. Dieses Makro akzeptiert einen Namen für eine *"uint" in der Nähe* Variable, die die registrierte Windows-Nachrichten-ID enthält. Beispiel:

```cpp
class CMyWnd : public CMyParentWndClass
{
public:
    CMyWnd();

    //{{AFX_MSG(CMyWnd)
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};

static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

Die registrierte Windows Message-ID-Variable (in diesem Beispiel WM_FIND) muss eine *NEAR* Variablen aufgrund der Art und Weise ON_REGISTERED_MESSAGE implementiert wird.

Des Bereichs von benutzerdefinierten Nachrichten, die diesen Ansatz verwenden, werden im Bereich von 0xC000 bis 0xFFFF.

> [!NOTE]
> Klassen-Assistent unterstützt keine Eingabe ON_REGISTERED_MESSAGE Handlerroutinen über die Klassen-Assistenten-Benutzeroberfläche. Sie müssen diese manuell aus dem Texteditor eingeben. Klassen-Assistent diese Einträge analysiert und lassen Sie diese genau wie alle anderen Meldungszuordnungseinträge durchsuchen.

## <a name="command-messages"></a>Befehlsmeldungen

Command-Meldungen von Menüs und Zugriffstasten werden im meldungszuordnungen mit dem ON_COMMAND-Makro behandelt. Dieses Makro akzeptiert eine Befehls-ID und eine Methode an. Nur die spezifischen WM_COMMAND-Meldung, die eine *wParam* gleich den angegebenen Befehl mit der ID von der Methode, die in der meldungszuordnung Eintrag angegeben erfolgt. Member-befehlshandlerfunktionen darf keine Parameter akzeptieren und zurückgeben **"void"**. Das Makro hat folgendes Format:

```cpp
ON_COMMAND(id, memberFxn)
```

Befehl Update-Nachrichten werden über denselben Mechanismus geleitet, aber verwenden Sie stattdessen die ON_UPDATE_COMMAND_UI-Makro. Befehl Update-Handler-Memberfunktionen akzeptieren einen einzelnen Parameter, ein Zeiger auf eine [CCmdUI](../mfc/reference/ccmdui-class.md) Objekt aus, und kehren zurück **"void"**. Das Makro hat das Format

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

Fortgeschrittene Benutzer können die ON_COMMAND_EX-Makro, das eine erweiterte Form der Nachricht Befehlshandler ist. Das Makro enthält eine Obermenge der ON_COMMAND-Funktionen. Erweiterte Befehlshandler-Memberfunktionen akzeptieren einen einzelnen Parameter, eine **UINT** , enthält die Befehls-ID und Zurückgeben einer **"bool"**. Der Rückgabewert muss **"true"** um anzugeben, dass der Befehl behandelt wurde. Andernfalls wird auf anderen Befehl Zielobjekte weiterzuleiten.

Beispiele für die der folgenden Formen:

- Einblick in Resource.h (in der Regel generiert, von Visual C++)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- In der Klassendeklaration

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- In der Definition der Message-Karte

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- In der Implementierungsdatei

    ```cpp
    void CMyClass::OnMyCommand()
    {
        // handle the command
    }

    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)
    {
        // set the UI state with pCmdUI
    }

    BOOL CMyClass::OnComplexCommand(UINT nID)
    {
        // handle the command
        return TRUE;
    }
    ```

Fortgeschrittene Benutzer können eine Auswahl von Befehlen mithilfe eines Handlers für die einzelnen Befehls verarbeiten: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) oder ON_COMMAND_RANGE_EX. Finden Sie in der Produktdokumentation für Weitere Informationen zu diesen Makros.

> [!NOTE]
> Klassen-Assistent unterstützt die Erstellung ON_COMMAND und ON_UPDATE_COMMAND_UI-Handler erstellen ON_COMMAND_EX oder ON_COMMAND_RANGE-Handler wird nicht unterstützt. Allerdings-Klassen-Assistent analysiert und lassen Sie alle vier Befehl Handler Varianten zu durchsuchen.

## <a name="control-notification-messages"></a>Benachrichtigungsmeldungen des Registersteuerelements

Nachrichten, die von untergeordneten Steuerelementen in einem Fenster haben ein zusätzliches bit, der Informationen in die Nachricht gesendet werden Eintrag zuordnen: des Steuerelements. Der Message-Handler in der Eintrag für die Zuordnung eine Nachricht angegebene ist nur aufgerufen, wenn die folgenden Bedingungen erfüllt sind:

- Der Steuerelement-Benachrichtigungscode (hohe Word der *lParam*), z. B. BN_CLICKED, entspricht den Benachrichtigungscode, der in der meldungszuordnung Eintrag angegeben.

- Die Steuerelement-ID (*wParam*) entspricht der Steuerelement-ID, die in der meldungszuordnung Eintrag angegeben.

Benachrichtigungsmeldungen des benutzerdefinierten Steuerelements können Sie die [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) Makro, um einen Eintrag für die Zuordnung von Nachrichten mit einer benutzerdefinierten Benachrichtigung definieren. Dieses Makro hat das Format

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

Für die Verwendung erweiterter [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) können verwendet werden, um eine spezifische Steuerung-Benachrichtigung über eine Vielzahl von Kontrollen, die mit den gleichen Handler behandelt.

> [!NOTE]
> Klassen-Assistenten unterstützt erstellen einen ON_CONTROL oder ON_CONTROL_RANGE-Handler in der Benutzeroberfläche nicht. Sie müssen diese manuell mit dem Texteditor eingeben. Klassen-Assistent diese Einträge analysiert und lassen Sie diese genau wie alle anderen Meldungszuordnungseinträge durchsuchen.

Die Windows-Standardsteuerelemente verwenden die leistungsstärkere [WM_NOTIFY](/windows/desktop/controls/wm-notify) für komplexe steuerelementbenachrichtigungen. Diese Version von MFC hat direkte Unterstützung für diese neue Nachricht mit den ON_NOTIFY- und ON_NOTIFY_RANGE-Makros. Finden Sie in der Produktdokumentation für Weitere Informationen zu diesen Makros.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
