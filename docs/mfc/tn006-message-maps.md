---
title: 'TN006: Meldungszuordnungen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 160b88a7069ac9a5851c0f472f756d694e59874e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384696"
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
  
-   Eine private Array von `AFX_MSGMAP_ENTRY` Einträge mit der Bezeichnung `_messageEntries`.  
  
-   Eine geschützte `AFX_MSGMAP` Struktur mit dem Namen `messageMap` , verweist auf die `_messageEntries` Array.  
  
-   Eine geschützte virtuelle Funktion mit dem Namen `GetMessageMap` , die die Adresse des zurückgibt `messageMap`.  
  
 Dieses Makro sollten in der Deklaration einer Klasse, die anhand von Karten, Nachricht abgelegt werden. Gemäß der Konvention ist es am Ende der Klassendeklaration. Zum Beispiel:  
  
```  
class CMyWnd : public CMyParentWndClass  
{ *// my stuff...  
 
protected: *//{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();
*//}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
```  
  
 Dies ist das Format von AppWizard und ClassWizard generiert werden, wenn sie neue Klassen erstellen. Der / / {{und / /}} ClassWizard Klammern erforderlich sind.  
  
 Die meldungszuordnung-Tabelle wird definiert, werden anhand eines Satzes von Makros, die als Meldungszuordnungseinträge erweitert. Eine Tabelle beginnt mit einem [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) Makro-Aufruf, der definiert, die Klasse, die durch diese nachrichtenzuordnung verarbeitet wird und die übergeordnete Klasse, die nicht verarbeitete Nachrichten übergeben werden. Die Tabelle endet mit dem [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) Makro-Aufruf.  
  
 Ist Sie ein Eintrag für jede Nachricht von diesem meldungszuordnung behandelt werden, zwischen diesen beiden-Makro aufrufen. Alle standardmäßigen Windows-Meldung ist ein Makro im Format ON_WM_*MESSAGE_NAME* , einen Eintrag für diese Nachricht generiert.  
  
 Eine Standardfunktion Signatur wurde definiert, Entpacken die Parameter der einzelnen Windows-Nachrichten und typsicherheit zu bieten. Diese Signaturen finden Sie in der Datei Afxwin.h in der Deklaration des [CWnd](../mfc/reference/cwnd-class.md). Jede einer ist mit dem Schlüsselwort markiert `afx_msg` leicht identifiziert.  
  
> [!NOTE]
>  Klassen-Assistent setzt voraus, dass Sie die `afx_msg` Schlüsselwort in der Nachricht Zuordnung Handler-Deklarationen.  
  
 Diese Funktionssignaturen wurden mithilfe einer einfachen Konvention abgeleitet. Der Name der Funktion beginnt immer mit `"On`". Dies ist der Name des Windows-Meldung mit der "WM_" entfernt und der erste Buchstabe jedes Wortes großgeschrieben folgen. Die Reihenfolge der Parameter ist `wParam` gefolgt von `LOWORD`(`lParam`) dann `HIWORD`(`lParam`). Nicht verwendete Parameter werden nicht übergeben. Alle Handles, die von MFC-Klassen umschlossen sind, werden in Zeiger auf die entsprechenden MFC-Objekte konvertiert. Das folgende Beispiel zeigt, wie behandelt die `WM_PAINT` Meldungen und dazu führen, dass die `CMyWnd::OnPaint` Funktion aufgerufen werden:  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT() *//}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 Die Message-Zuordnungstabelle muss außerhalb des Bereichs von jeder Funktions- oder Klassendefinition definiert werden. Sie sollten nicht in einem Extern "C" Block abgelegt werden.  
  
> [!NOTE]
>  ClassWizard Ändern der Zuordnungseinträge der Nachricht, die zwischen dem Auftreten der / / {{und / /}} Kommentar Klammer.  
  
## <a name="user-defined-windows-messages"></a>Benutzerdefinierte Windows-Meldungen  
 Benutzerdefinierte Meldungen können in einer meldungszuordnung aufgenommen werden, mithilfe der [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) Makro. Dieses Makro akzeptiert einer Meldungsnummer und eine Methode der Form:  
  
"" * / / in der Klassendeklaration  
    Afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 
 #<a name="define-wmmymessage-wmuser--100"></a>Definieren von WM_MYMESSAGE (WM_USER + 100)  
 
BEGIN_MESSAGE_MAP (CMyWnd, CMyParentWndClass)  
    ON_MESSAGE (WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 In this example, we establish a handler for a custom message that has a Windows message ID derived from the standard `WM_USER` base for user-defined messages. The following example shows how to call this handler:  
  
```  
CWnd * pWnd =...;  
pWnd-SendMessage(WM_MYMESSAGE) >;
```  
  
 The range of user-defined messages that use this approach must be in the range `WM_USER` to 0x7fff.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the Visual C++ editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Registered Windows Messages  
 The [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) function is used to define a new window message that is guaranteed to be unique throughout the system. The macro `ON_REGISTERED_MESSAGE` is used to handle these messages. This macro accepts a name of a `UINT NEAR` variable that contains the registered windows message ID. For example  
  
```  
-Klasse CMyWnd: öffentliche CMyParentWndClass  
{  
public:  
    CMyWnd();

 *//{{AFX_MSG(CMyWnd)  
    Afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam); * //}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
 
Statische "uint" in der Nähe von WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

 
BEGIN_MESSAGE_MAP (CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_REGISTERED_MESSAGE (WM_FIND, OnFind) * //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 The registered Windows message ID variable (WM_FIND in this example) must be a `NEAR` variable because of the way `ON_REGISTERED_MESSAGE` is implemented.  
  
 The range of user-defined messages that use this approach will be in the range 0xC000 to 0xFFFF.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_REGISTERED_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the text editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Command Messages  
 Command messages from menus and accelerators are handled in message maps with the `ON_COMMAND` macro. This macro accepts a command ID and a method. Only the specific `WM_COMMAND` message that has a `wParam` equal to the specified command ID is handled by the method specified in the message-map entry. Command handler member functions take no parameters and return `void`. The macro has the following form:  
  
```  
ON_COMMAND (Id, MemberFxn)  
```  
  
 Command update messages are routed through the same mechanism, but use the `ON_UPDATE_COMMAND_UI` macro instead. Command update handler member functions take a single parameter, a pointer to a [CCmdUI](../mfc/reference/ccmdui-class.md) object, and return `void`. The macro has the form  
  
```  
ON_UPDATE_COMMAND_UI (Id, MemberFxn)  
```  
  
 Advanced users can use the `ON_COMMAND_EX` macro, which is an extended form of command message handlers. The macro provides a superset of the `ON_COMMAND` functionality. Extended command-handler member functions take a single parameter, a `UINT` that contains the command ID, and return a `BOOL`. The return value should be `TRUE` to indicate that the command has been handled. Otherwise routing will continue to other command target objects.  
  
 Examples of these forms:  
  
-   Inside Resource.h (usually generated by Visual C++)  
  
 ```  
 #<a name="define----idmycmd------100"></a>Definieren von ID_MYCMD 100  
 #<a name="define----idcomplex----101"></a>Definieren von ID_COMPLEX 101  
 ```  
  
-   Inside the class declaration  
  
 ```  
    afx_msg void OnMyCommand();
Afx_msg "void" OnUpdateMyCommand (CCmdUI * nämlich pCmdUI);

    afx_msg BOOL OnComplexCommand(UINT nID);

 ```  
  
-   Inside the message map definition  
  
 ```  
    ON_COMMAND(ID_MYCMD,
    OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD,
    OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD,
    OnComplexCommand)  
 ```  
  
-   In the implementation file  
  
 ```  
    void CMyClass::OnMyCommand()  
 {* / / Verarbeiten Sie den Befehl  
 }  
 
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
 {* / / Legen Sie den Zustand der Benutzeroberfläche mit nämlich pCmdUI  
 }  
 
    BOOL CMyClass::OnComplexCommand(UINT nID)  
 {* / / Verarbeiten Sie den Befehl  
    Geben Sie "true" zurück.  
 }  
 ```  
  
 Advanced users can handle a range of commands by using a single command handler: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) or `ON_COMMAND_RANGE_EX`. See the product documentation for more information about these macros.  
  
> [!NOTE]
>  ClassWizard supports creating `ON_COMMAND` and `ON_UPDATE_COMMAND_UI` handlers, but it does not support creating `ON_COMMAND_EX` or `ON_COMMAND_RANGE` handlers. However, Class Wizard will parse and let you browse all four command handler variants.  
  
## Control Notification Messages  
 Messages that are sent from child controls to a window have an extra bit of information in their message map entry: the control's ID. The message handler specified in a message map entry is called only if the following conditions are true:  
  
-   The control notification code (high word of `lParam`), such as BN_CLICKED, matches the notification code specified in the message-map entry.  
  
-   The control ID (`wParam`) matches the control ID specified in the message-map entry.  
  
 Custom control notification messages may use the [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) macro to define a message map entry with a custom notification code. This macro has the form  
  
```  
ON_CONTROL (wNotificationCode, Id, MemberFxn)  
```  
  
 For advanced usage [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) can be used to handle a specific control notification from a range of controls with the same handler.  
  
> [!NOTE]
>  ClassWizard does not support creating an `ON_CONTROL` or `ON_CONTROL_RANGE` handler in the user interface. You must manually enter them with the text editor. ClassWizard will parse these entries and let you browse them just like any other message map entries.  
  
 The Windows Common Controls use the more powerful [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) for complex control notifications. This version of MFC has direct support for this new message by using the `ON_NOTIFY` and `ON_NOTIFY_RANGE` macros. See the product documentation for more information about these macros.  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

