---
title: 'TN006: Meldungszuordnungen | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.messages.maps
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c4bc820c6b54e055235c1bd29bd55ccfc032c92
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121675"
---
# <a name="tn006-message-maps"></a>TN006: Meldungszuordnungen

In diesem Hinweis werden die MFC-Nachricht Map-Funktion.

## <a name="the-problem"></a>Das Problem

Microsoft Windows implementiert virtuelle Funktionen in Fensterklassen, die die messaging-Funktion verwenden. Aufgrund der großen Anzahl von betroffenen Nachrichten würde das Bereitstellen einer separaten virtuellen Funktion für jede Windows-Nachricht eine sehr große Vtable erstellen.

Daran, dass die Anzahl der vom System definierte Windows-Meldungen, die mit der Zeit ändert, und daran, dass Anwendungen ihre eigenen Windows-Meldungen definieren können meldungszuordnungen, geben Sie ein Maß an Dereferenzierung, die verhindert, dass die Schnittstelle ändert sich wichtige von vorhandenem Code.

## <a name="overview"></a>Übersicht

MFC bietet eine Alternative für die Switch-Anweisung, die in herkömmlichen Windows-basierten Programmen verwendet wurde, um Nachrichten in einem Fenster zu behandeln. Eine Zuordnung von Nachrichten an Methoden kann definiert werden, sodass, wenn eine Nachricht von einem Fenster empfangen wird, automatisch die entsprechende Methode aufgerufen wird. Diese Nachricht-Map-Funktion virtuelle Funktionen ähneln ausgelegt ist, aber es bietet weitere Vorteile, die mit virtuellen Funktionen von C++ nicht möglich.

## <a name="defining-a-message-map"></a>Definieren einer Meldungszuordnung

Die [DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) Makro deklariert drei Member für eine Klasse.

- Eine private Array von AFX_MSGMAP_ENTRY Einträge bezeichnet *_messageEntries*.

- Wird aufgerufen, eine geschützte AFX_MSGMAP Struktur *MessageMap* , verweist auf die *_messageEntries* Array.

- Eine geschützte virtuelle Funktion mit dem Namen `GetMessageMap` , die die Adresse des zurückgibt *MessageMap*.

Dieses Makro sollten in der Deklaration einer Klasse, die anhand von Karten, Nachricht abgelegt werden. Gemäß der Konvention ist es am Ende der Klassendeklaration. Zum Beispiel:

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

Dies ist das Format von AppWizard und ClassWizard generiert werden, wenn sie neue Klassen erstellen. Der / / {{und / /}} ClassWizard Klammern erforderlich sind.

Die meldungszuordnung-Tabelle wird definiert, werden anhand eines Satzes von Makros, die als Meldungszuordnungseinträge erweitert. Eine Tabelle beginnt mit einem [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro-Aufruf, der definiert, die Klasse, die durch diese nachrichtenzuordnung verarbeitet wird und die übergeordnete Klasse, die nicht verarbeitete Nachrichten übergeben werden. Die Tabelle endet mit dem [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) Makro-Aufruf.

Ist Sie ein Eintrag für jede Nachricht von diesem meldungszuordnung behandelt werden, zwischen diesen beiden-Makro aufrufen. Alle standardmäßigen Windows-Meldung ist ein Makro im Format ON_WM_*MESSAGE_NAME* , einen Eintrag für diese Nachricht generiert.

Eine Standardfunktion Signatur wurde definiert, Entpacken die Parameter der einzelnen Windows-Nachrichten und typsicherheit zu bieten. Diese Signaturen finden Sie in der Datei Afxwin.h in der Deklaration des [CWnd](../mfc/reference/cwnd-class.md). Jede einer ist mit dem Schlüsselwort markiert **Afx_msg** leicht identifiziert.

> [!NOTE]
> Klassen-Assistent setzt voraus, dass Sie die **Afx_msg** Schlüsselwort in der Nachricht Zuordnung Handler-Deklarationen.

 Diese Funktionssignaturen wurden mithilfe einer einfachen Konvention abgeleitet. Der Name der Funktion beginnt immer mit `"On`". Dies ist der Name des Windows-Meldung mit der "WM_" entfernt und der erste Buchstabe jedes Wortes großgeschrieben folgen. Die Reihenfolge der Parameter ist *wParam* gefolgt von `LOWORD`(*lParam*) dann `HIWORD`(*lParam*). Nicht verwendete Parameter werden nicht übergeben. Alle Handles, die von MFC-Klassen umschlossen sind, werden in Zeiger auf die entsprechenden MFC-Objekte konvertiert. Im folgende Beispiel wird gezeigt, wie die WM_PAINT-Meldung behandeln und dazu führen, dass die `CMyWnd::OnPaint` Funktion aufgerufen werden:

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

 Die Message-Zuordnungstabelle muss außerhalb des Bereichs von jeder Funktions- oder Klassendefinition definiert werden. Sie sollten nicht in einem Extern "C" Block abgelegt werden.

> [!NOTE]
> ClassWizard Ändern der Zuordnungseinträge der Nachricht, die zwischen dem Auftreten der / / {{und / /}} Kommentar Klammer.

## <a name="user-defined-windows-messages"></a>Benutzerdefinierte Windows-Meldungen

Benutzerdefinierte Meldungen können in einer meldungszuordnung aufgenommen werden, mithilfe der [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) Makro. Dieses Makro akzeptiert einer Meldungsnummer und eine Methode der Form:

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

In diesem Beispiel erstellen wir einen Handler für eine benutzerdefinierte Meldung, die eine Windows-Nachrichten-ID von der standardmäßigen WM_USER Basisklasse für benutzerdefinierte Meldungen abgeleitet wurde. Im folgende Beispiel wird gezeigt, wie dieser Handler aufgerufen wird:

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

Des Bereichs von benutzerdefinierten Meldungen, die diesen Ansatz verwenden, muss im Bereich WM_USER bis 0x7fff sein.

> [!NOTE]
> ClassWizard unterstützt Eingabe ON_MESSAGE Handlerroutinen über die Benutzeroberfläche von ClassWizard nicht. Sie müssen Sie manuell aus dem Visual C++-Editor eingeben. Klassen-Assistent diese Einträge analysiert und diese genau wie andere Meldungszuordnungseinträge zu durchsuchen.

## <a name="registered-windows-messages"></a>Registrierte Windows-Meldungen

Die [RegisterWindowMessage registriert](http://msdn.microsoft.com/library/windows/desktop/ms644947) Funktion wird verwendet, um eine neue fenstermeldung zu definieren, die garantiert im gesamten System eindeutig sein. ON_REGISTERED_MESSAGE-Makro wird verwendet, um diese Nachrichten zu behandeln. Dieses Makro akzeptiert einen Namen für eine *"uint" in der Nähe* Variable an, die registrierten Windows-Nachrichten-ID enthält. Beispiel:

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

Die registrierte Windows-ID Nachrichtenvariable fest (in diesem Beispiel WM_FIND) muss eine *NEAR* Variable aufgrund der Art und Weise ON_REGISTERED_MESSAGE implementiert.

Des Bereichs von benutzerdefinierten Meldungen, die diesen Ansatz verwenden, werden im Bereich 0xC000 bis 0xFFFF.

> [!NOTE]
> ClassWizard unterstützt Eingabe ON_REGISTERED_MESSAGE Handlerroutinen über die Benutzeroberfläche von ClassWizard nicht. Sie müssen Sie manuell aus dem Texteditor eingeben. Klassen-Assistent diese Einträge analysiert und diese genau wie andere Meldungszuordnungseinträge zu durchsuchen.

## <a name="command-messages"></a>Befehlsmeldungen

Command-Meldungen von Menüs und Zugriffstasten in meldungszuordnungen mit dem ON_COMMAND-Makro behandelt werden. Dieses Makro akzeptiert eine Befehls-ID und eine Methode. Nur die spezifischen WM_COMMAND Nachricht mit einem *wParam* gleich den angegebenen Befehl ID durch die Methode, die in der Meldungszuordnungseintrags angegeben erfolgt. Befehlshandlerfunktionen Element darf keine Parameter akzeptieren und zurückgeben **"void"**. Das Makro weist folgende Form:

```cpp
ON_COMMAND(id, memberFxn)
```

Update von befehlsmeldungen mithilfe desselben Mechanismus weitergeleitet werden, aber verwenden Sie stattdessen die ON_UPDATE_COMMAND_UI-Makro. Update Member befehlshandlerfunktionen nehmen einen einzelnen Parameter, ein Zeiger auf eine [CCmdUI](../mfc/reference/ccmdui-class.md) -Objekts und zurückgeben **"void"**. Das Makro hat das Format

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

Erfahrene Benutzer können die ON_COMMAND_EX-Makro eine erweiterte Form der Befehlshandler der Nachricht ist verwenden. Das Makro enthält eine Obermenge der ON_COMMAND-Funktionen. Erweiterte Befehlshandler-Memberfunktionen akzeptieren einen einzelnen Parameter eine **"uint"** , enthält die Befehls-ID und Zurückgeben einer **BOOL**. Der Rückgabewert muss **"true"** um anzugeben, dass der Befehl behandelt wurde. Andernfalls wird auf anderen Befehl Zielobjekte weiterzuleiten.

Beispiele für diese Formen:

- In Resource.h (in der Regel von Visual C++ generiert)

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

- In der Nachrichtendefinition-Karte

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

 Erfahrene Benutzer können eine Auswahl von Befehlen behandeln, indem Sie einen einzelnen Befehlshandler: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) oder ON_COMMAND_RANGE_EX. Finden Sie in der Produktdokumentation für Weitere Informationen zu diesen Makros.

> [!NOTE]
> Klassen-Assistent unterstützt erstellen ON_COMMAND- und ON_UPDATE_COMMAND_UI-Handler erstellen ON_COMMAND_EX oder ON_COMMAND_RANGE-Handler wird nicht unterstützt. Allerdings Klassen-Assistenten analysiert und alle vier Befehl Handler Varianten zu durchsuchen.

## <a name="control-notification-messages"></a>Benachrichtigungsmeldungen des Registersteuerelements

Nachrichten, die von untergeordneten Steuerelementen in einem Fenster haben eine zusätzliche bit, der Informationen in die Nachricht gesendet werden zuzuordnen, Eintrag: das Steuerelement-ID. Der Message-Handler, die in einer Nachrichtenzuordnungseintrag angegeben heißt nur dann, wenn Folgendes zutrifft:

- Der Steuerungscode-Benachrichtigung (hohe Word des *lParam*), z. B. BN_CLICKED, entspricht den Benachrichtigungscode in die Meldungszuordnungseintrags angegeben.

- Die Steuerelement-ID (*wParam*) entspricht die Steuerelement-ID, die in der Meldungszuordnungseintrags angegeben.

Benachrichtigungsmeldungen von benutzerdefinierten möglicherweise verwenden Sie die [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) Makro, das einen Nachrichtenzuordnungseintrag durch eine benutzerdefinierte Benachrichtigungscode zu definieren. Dieses Makro hat das Format

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

Für die Verwendung erweiterter [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) können verwendet werden, um ein bestimmtes Steuerelement-Benachrichtigung aus einem Bereich von Steuerelementen mit den gleichen Handler behandelt.

> [!NOTE]
> Erstellen einen ON_CONTROL oder ON_CONTROL_RANGE-Handler in der Benutzeroberfläche von ClassWizard nicht unterstützt. Sie müssen Sie manuell in einem Texteditor eingeben. Klassen-Assistent diese Einträge analysiert und diese genau wie andere Meldungszuordnungseinträge zu durchsuchen.

Die allgemeine Windows-Steuerelemente verwenden die leistungsstärkere [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) für komplexe steuerelementbenachrichtigungen. Diese Version von MFC hat direkte Unterstützung für die neue Nachricht mit den Makros ON_NOTIFY- und ON_NOTIFY_RANGE. Finden Sie in der Produktdokumentation für Weitere Informationen zu diesen Makros.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)  
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)  
