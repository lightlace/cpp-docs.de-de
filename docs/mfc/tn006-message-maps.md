---
title: "TN006: Meldungszuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.messages.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Meldungszuordnungen [C++], Windows-Messaging"
  - "ON_COMMAND-Makro"
  - "ON_COMMAND_EX-Makro"
  - "ON_COMMAND_RANGE-Makro"
  - "ON_COMMAND_RANGE_EX-Makro"
  - "ON_CONTROL-Makro"
  - "ON_CONTROL_RANGE-Makro"
  - "ON_MESSAGE-Makro"
  - "ON_NOTIFY-Meldung"
  - "ON_NOTIFY_RANGE-Makro"
  - "ON_REGISTERED_MESSAGE-Makro"
  - "ON_UPDATE_COMMAND_UI-Makro"
  - "TN006"
  - "Windows-Nachrichten [C++], Meldungszuordnungen"
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# TN006: Meldungszuordnungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die MFC\-Meldungszuordnungsfunktion.  
  
## Das Problem  
 Microsoft Windows implementiert virtuelle Funktionen in den Fensterklassen, die die Messagingfunktion verwenden.  Aufgrund der großen Anzahl der Nachrichten, die, eine separate virtuelle Funktion für jede Windows\-Meldung Bereitstellen haben, kann ein großes kostspielig vtable erstellen.  
  
 Da die Anzahl systemdefiniertem Windows\-Meldungen im Zeitverlauf ändert und da Anwendungen ihre eigenen Windows\-Meldungen definieren können, stellen Meldungszuordnungen eine Dereferenzierungsebene, die vom Schnittstellenänderungen Unterbrechen des vorhandenen Codes verhindert.  
  
## Übersicht  
 MFC bietet eine Alternative zur switch\-Anweisung bereit, die in herkömmlichen Windows\-basierten Programmen verwendet wurde, um die Meldungen verarbeiten, die an ein Fenster gesendet wurden.  Eine Zuordnung der Meldungen zu Methoden kann definiert werden, dass, wenn eine Meldung von einem Fenster empfangen wird, der entsprechenden Methode automatisch aufgerufen wird.  Diese Meldungszuordnungsfunktion wurde entworfen, um virtuelle Funktionen zu ähneln aber zusätzliche Vorteile verfügt, die mit virtuellen Funktionen C\+\+ nicht möglich sind.  
  
## Definieren eine Meldungszuordnung  
 Das Makro [DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md) deklariert drei Member einer Klasse.  
  
-   Ein privates Array `AFX_MSGMAP_ENTRY` Einträge namens `_messageEntries`.  
  
-   Eine geschützte `AFX_MSGMAP`\-Struktur namens `messageMap`, die auf `_messageEntries` das Array wird.  
  
-   Eine geschützte virtuelle Funktion namens `GetMessageMap`, der die Adresse von `messageMap` zurückgibt.  
  
 Dieses Makro sollte in die Deklaration einer Klasse mithilfe der Meldungszuordnungen platziert werden.  Üblicherweise ist es am Ende der Klassendeklaration.  Beispiel:  
  
```  
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
  
 Dies ist das Format, das vom Anwendungs\-Assistenten generiert und die, wenn sie neuer Klassen erstellen.  Die Klammern \/\/{\/\/{und}} werden für die erfordert.  
  
 Die Tabelle der Meldungszuordnung wird definiert, indem einen Makros verwendet, die den Meldungszuordnungseinträgen erweitern.  Startet eine Tabelle mit einem [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md)\-Makro\-Aufruf, der die Klasse, die durch diese Meldungszuordnung und die übergeordnete Klasse behandelt wird, auf die nicht behandelte Meldungen übergeben werden.  Die Tabellenenden mit dem [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)\-Makro\-Aufruf.  
  
 Zwischen diesen beiden Makro\-Aufrufen ist ein Eintrag, damit jede Meldung von dieser Meldungszuordnung behandelt werden kann.  Jede Standardwindows\-meldung hat ein Makro des Formulars ON\_WM\_*MESSAGE\_NAME*, das einen Eintrag für diese Nachricht generiert.  
  
 Eine Standardfunktionsunterzeichnung ist für das Entpacken der Parameter jeder Windows\-Meldung und das Bereitstellen der Typsicherheit definiert.  Diese Signaturen werden in der Datei Afxwin.h in der Deklaration von [CWnd](../mfc/reference/cwnd-class.md) gefunden werden.  Jedes wird mit dem Schlüsselwort `afx_msg` für einfache Identifikation markiert.  
  
> [!NOTE]
>  Der Klassen\-Assistent erfordert, dass Sie das `afx_msg`\-Schlüsselwort in den Meldungszuordnungshandlerdeklarationen verwenden.  
  
 Diese wurden Funktionssignaturen berechnet, indem eine einfache Konvention verwendet.  Der Name der Funktion beginnt immer mit `"On`".  Dies wird mit dem Namen der Windows\-Meldung mit dem "WM\_ gefolgt", das entfernt wird und den ersten Buchstaben jedes Worts Großbuchstaben.  Die Reihenfolge der Parameter ist `wParam`, das von `LOWORD`\(`lParam`\) gefolgt wird `HIWORD`\(`lParam`\).  Nicht verwendete Parameter sind nicht übergeben.  Alle Handles, die von MFC\-Klassen umschlossen sind, werden zu Zeigern zu den korrespondierenden MFC\-Objekten konvertiert.  Das folgende Beispiel zeigt, wie `WM_PAINT` die Meldung verarbeitet und die `CMyWnd::OnPaint`\-Funktion wird aufgerufen werden:  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    //{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT()  
    //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 Die Meldungszuordnungstabelle muss außerhalb der Möglichkeiten jeder Funktions\- oder Klassendefinition definiert werden.  Sie sollte nicht in einen Block extern "C" abgelegt werden.  
  
> [!NOTE]
>  Der Klassen\-Assistent ändert die Meldungszuordnungseinträge, die zwischen der Kommentarauftreten Klammer \/\/{\/\/{und}}.  
  
## Benutzerdefinierte Windows\-Meldungen  
 Benutzerdefinierte Meldungen werden in der Meldungszuordnung enthalten, indem das [ON\_MESSAGE](../Topic/ON_MESSAGE.md)\-Makro verwendet.  Dieses Makro akzeptiert eine Meldungsnummer und eine Methode des Formulars:  
  
```  
    // inside the class declaration  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);  
  
    #define WM_MYMESSAGE (WM_USER + 100)  
  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)  
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 In diesem Beispiel richten Sie einen Handler für eine benutzerdefinierte Meldung ein, die eine Windows\-Meldung ID verfügt, die in der Standard\- `WM_USER` Basis für benutzerdefinierte Meldungen abgeleitet wird.  Das folgende Beispiel zeigt, wie dieser Handler aufruft:  
  
```  
CWnd* pWnd = ...;  
pWnd->SendMessage(WM_MYMESSAGE);  
```  
  
 Der Gültigkeitsbereich von benutzerdefinierten Meldungen, die diesen Ansatz verwenden, muss im Bereich `WM_USER` zu 0x7fff sein.  
  
> [!NOTE]
>  Der Klassen\-Assistent unterstützt nicht die Eingabe von `ON_MESSAGE`\-Handlerroutinen von der ClassWizard\-Benutzeroberfläche.  Sie müssen sie vom Visual C\+\+\-Editor manuell eingeben.  Der Klassen\-Assistent analysiert diese Einträge und lässt Sie sie genauso wie alle anderen Meldungszuordnungseinträge durchsuchen.  
  
## Registrierte Windows\-Meldungen  
 Die Funktion [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) wird verwendet, um eine Nachricht des neuen Fensters zu definieren, die garantiert wird, um während des Systems eindeutig.  Makro\- `ON_REGISTERED_MESSAGE` wird verwendet, um diese Nachrichten behandeln.  Dieses Makro akzeptiert einen Namen einer Variable `UINT NEAR`, die die registrierte Fenstermeldung ID enthält  Beispiel:  
  
```  
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
  
 Die Windows\-Meldung registrierte ID\-Variable \(WM\_FIND in diesem Beispiel `NEAR` \) muss eine Variable sein aufgrund der Methode, die `ON_REGISTERED_MESSAGE` implementiert wird.  
  
 Der Gültigkeitsbereich von benutzerdefinierten Meldungen, die diesen Ansatz verwenden, ist im Bereich 0xC000 zu 0xFFFF.  
  
> [!NOTE]
>  Der Klassen\-Assistent unterstützt nicht die Eingabe von `ON_REGISTERED_MESSAGE`\-Handlerroutinen von der ClassWizard\-Benutzeroberfläche.  Sie müssen sie im Text\-Editor manuell eingeben.  Der Klassen\-Assistent analysiert diese Einträge und lässt Sie sie genauso wie alle anderen Meldungszuordnungseinträge durchsuchen.  
  
## Befehlsmeldungen  
 Befehlsmeldungen von Menüs und den Zugriffstasten werden im Meldungszuordnungen mit dem Makro `ON_COMMAND` bearbeitet.  Dieses Makro akzeptiert eine Befehls\-ID und eine Methode.  Nur die bestimmte `WM_COMMAND` Meldung, die die angegebene `wParam` gleich Befehls\-ID verfügt, wird von der Methode behandelt, die im Eintrag in der Meldungszuordnung angegeben wird.  Befehlshandlermemberfunktionen nehmen keine Parameter und geben `void` zurück.  Das Makro hat das folgende Format:  
  
```  
ON_COMMAND(id, memberFxn)  
```  
  
 Befehlsupdatemeldungen werden durch denselben Mechanismus weitergeleitet, jedoch das `ON_UPDATE_COMMAND_UI` stattdessen Makro verwenden.  Befehlsaktualisierungshandlermemberfunktionen akzeptieren einen einzelnen Parameter, einen Zeiger auf ein [CCmdUI](../mfc/reference/ccmdui-class.md)\-Objekt und geben `void` zurück.  Das Makro hat das Formular  
  
```  
ON_UPDATE_COMMAND_UI(id, memberFxn)  
```  
  
 Fortgeschrittene Benutzer können das Makro `ON_COMMAND_EX` verwenden, das ein erweitertes Formular von Befehlsmeldungshandlern ist.  Das Makro enthält eine Obermenge der `ON_COMMAND`\-Funktionen.  Erweiterte Befehlshandlermemberfunktionen akzeptieren einen einzelnen Parameter, `UINT`, der die Befehls\-ID enthält, und geben `BOOL` zurück.  Der Rückgabewert sollte `TRUE` sein anzugeben, dass der Befehl behandelt wurde.  Andernfalls wird das Routing zu anderen Befehlszielobjekten fort.  
  
 Beispiele für diese Formulare:  
  
-   Schließen Resource.h normalerweise \(generiert durch Visual C\+\+\)  
  
    ```  
    #define    ID_MYCMD      100  
    #define    ID_COMPLEX    101  
    ```  
  
-   Innerhalb der Klassendeklaration  
  
    ```  
    afx_msg void OnMyCommand();  
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);  
    afx_msg BOOL OnComplexCommand(UINT nID);  
    ```  
  
-   Innerhalb der Meldungszuordnungsdefinition  
  
    ```  
    ON_COMMAND(ID_MYCMD, OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)  
    ```  
  
-   In der Implementierungsdatei  
  
    ```  
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
  
 Fortgeschrittene Benutzer können einen Bereich von Befehlen behandeln, indem er einen einzigen Befehlshandler verwenden: [ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md) oder `ON_COMMAND_RANGE_EX`.  Siehe die Produktdokumentation zu Informationen über diese Makros.  
  
> [!NOTE]
>  Der Klassen\-Assistent unterstützt das Erstellen von `ON_COMMAND` und `ON_UPDATE_COMMAND_UI`, Handler jedoch nicht unterstützt das Erstellen von `ON_COMMAND_EX` oder `ON_COMMAND_RANGE`\-Handlern.  Allerdings analysiert Klassen\-Assistent und lässt Sie alle vier Befehlshandlervarianten durchsuchen.  
  
## Steuerelementbenachrichtigungs\-Meldungen  
 Meldungen, die von untergeordneten Steuerelementen an ein Fenster gesendet werden, haben eine zusätzliche Informationen in einem Eintrag in der Meldungszuordnung: die ID des Steuerelements  Der Meldungshandler, der in einem Eintrag in der Meldungszuordnung angegeben wird, wird aufgerufen, wenn die folgenden Bedingungen erfüllt sind:  
  
-   Der Steuerelementbenachrichtigungscode \(das Wort von `lParam`\), wie BN\_CLICKED, entspricht dem Benachrichtigungscode ab, der im Eintrag in der Meldungszuordnung angegeben wird.  
  
-   Die Steuerelement\-ID \(`wParam`\) entspricht die Steuerelement\-ID ab, die im Eintrag in der Meldungszuordnung angegeben wird.  
  
 Benachrichtigungsmeldungen des benutzerdefinierten Steuerelements können das [ON\_CONTROL](../Topic/ON_CONTROL.md)\-Makro, um einen Eintrag in der Meldungszuordnung mit einem benutzerdefinierten Benachrichtigungscode zu definieren.  Dieses Makro hat das Formular  
  
```  
ON_CONTROL(wNotificationCode, id, memberFxn)  
```  
  
 Für erweiterte Verwendung kann [ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md) verwendet werden, um eine bestimmte Steuerelementbenachrichtigung aus einem Bereich von Steuerelementen mit den gleichen Handler zu bearbeiten.  
  
> [!NOTE]
>  Der Klassen\-Assistent unterstützt nicht die Erstellung eines `ON_CONTROL` oder `ON_CONTROL_RANGE`\-Handlers in der Benutzeroberfläche.  Sie müssen sie für den Text\-Editor manuell eingeben.  Der Klassen\-Assistent analysiert diese Einträge und lässt Sie sie genauso wie alle anderen Meldungszuordnungseinträge durchsuchen.  
  
 Die allgemeinen Windows\-Steuerelemente verwenden effektivere [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) für komplexe Steuerelementbenachrichtigungen.  Diese Version von MFC verfügt direkte Unterstützung dieser neue Meldung, indem die Makros `ON_NOTIFY` und `ON_NOTIFY_RANGE` verwendet.  Siehe die Produktdokumentation zu Informationen über diese Makros.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)