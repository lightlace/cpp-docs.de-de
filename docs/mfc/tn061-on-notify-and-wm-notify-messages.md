---
title: "TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_NOTIFY"
  - "WM_NOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benachrichtigungsmeldungen"
  - "ON_NOTIFY-Meldung"
  - "ON_NOTIFY_EX-Meldung"
  - "ON_NOTIFY_EX_RANGE-Meldung"
  - "ON_NOTIFY_RANGE-Meldung"
  - "TN061"
  - "WM_NOTIFY-Meldung"
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser technische Hinweis enthält Hintergrundinformationen auf der neuen **WM\_NOTIFY** Meldung an und beschreibt die empfohlene \(und verbreitetste\) Methode des **WM\_NOTIFY** Behandlung von Meldungen in der MFC\-Anwendung.  
  
 **Benachrichtigungsmeldungen in Windows 3.x**  
  
 In Windows 3.x, benachrichtigen Steuerelemente ihre übergeordneten Elemente von Ereignissen wie Mausklicks, Änderungen im Inhalt und Auswahl und Steuerhintergrundzeichnen, indem eine Meldung zum übergeordneten senden.  Einfache Benachrichtigungen werden als besondere **WM\_COMMAND** Nachrichten gesendet, mit dem Benachrichtigungscode \(wie **BN\_CLICKED**\) und Steuerelement\-ID gepackt in `wParam` und das Handle des Steuerelements in `lParam`.  Beachten Sie seit das `wParam` und `lParam` sind voll, gibt es keine Möglichkeit, zusätzliche Daten zu übermitteln \- Diese Meldungen können nur einfache Benachrichtigung sein.  In der **BN\_CLICKED** Benachrichtigung, gibt es keine Möglichkeit, Informationen über die Position des Mauszeigers zu senden, sobald auf die Schaltfläche geklickt wurde.  
  
 Wenn Steuerelemente in Windows 3.x eine Benachrichtigung senden müssen, die zusätzliche Daten enthält, verwenden sie eine Reihe von Meldungen für besondere Zwecke, einschließlich `WM_CTLCOLOR`, `WM_VSCROLL`, `WM_HSCROLL`, `WM_DRAWITEM`, `WM_MEASUREITEM`, `WM_COMPAREITEM`, `WM_DELETEITEM`, `WM_CHARTOITEM`, `WM_VKEYTOITEM`, z. B.  Diese Meldungen können an das Steuerelement auswirken, das sie gesendet.  Weitere Informationen finden Sie unter [TN062: Meldungs\-Reflektion für Windows\-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
 **Benachrichtigungsmeldungen in Win32**  
  
 Für Steuerelemente, die in Windows 3.1, waren die Win32 API\-Gebräuche höchst von den Benachrichtigungsmeldungen, die in Windows 3.x. verwendet wurden.  Es fügt Win32 auch einige hoch entwickeltes komplexe Steuerelemente, zu denen hinzu, die in Windows 3.x. unterstützt werden.  Häufig Anforderung dieser Steuerelemente, zusätzliche Daten mit ihren Benachrichtigungen senden.  Anstatt, eine neue **WM\_\*** Meldung für jede Benachrichtigung neue hinzufügen, die weitere Daten benötigt, z die Designer der Win32\-API, um nur eine Nachricht, **WM\_NOTIFY** hinzuzufügen, die eine Menge zusätzliche Daten in einer standardisierten Weise übergeben kann.  
  
 **WM\_NOTIFY** Meldungen enthalten die ID des Steuerelements, das die Meldung im `wParam` und einen Zeiger auf eine Struktur in `lParam` sendet.  Diese Struktur ist entweder **NMHDR** eine Struktur oder eine größere Struktur, die eine **NMHDR**\-Struktur als erster Member verfügt.  Beachten Sie, wie der Member, zuerst **NMHDR** ist ein Zeiger auf diese Struktur kann verwendet werden als Zeiger auf **NMHDR** oder als Zeiger zur größeren Struktur je nachdem, wie Sie sie umwandeln.  
  
 In den meisten Fällen wird der Zeiger auf einer größeren Struktur und Sie müssen es umwandeln, wenn Sie sie verwenden.  In einigen nur Benachrichtigungen wie den allgemeinen Benachrichtigungen der Benachrichtigungen \(deren Namen mit **NM\_** beginnen\) und **TTN\_SHOWTTN\_POP** des ToolTip\-Steuerelements, ist eine wirklich verwendete **NMHDR**\-Struktur.  
  
 Die **NMHDR**\-Struktur oder das Gründungsmitglied enthält das Handle und die ID des Steuerelements, das die Meldung und den Benachrichtigungscode \(wie **TTN\_SHOW**\) sendet.  Das Format der **NMHDR**\-Struktur wird unten angezeigt:  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 Eine **TTN\_SHOW** Meldung würde die Codemember auf **TTN\_SHOW** festgelegt.  
  
 Die meisten Benachrichtigungen übergeben einen größeren Zeiger auf eine Struktur, die eine **NMHDR**\-Struktur als erster Member enthält.  Betrachten Sie beispielsweise die Struktur als Verwendung durch die **LVN\_KEYDOWN** Benachrichtigung des Listenansicht\-Steuerelements, die gesendet wird, wenn eine Taste ein Listenansicht\-Steuerelement gedrückt wird.  Der Zeiger wird auf **LV\_KEYDOWN** einer Struktur, die wie weiter unten definiert wird:  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 Beachten Sie, wie der Member **NMHDR** zunächst in dieser Struktur ist, der Zeiger, den Sie in die Benachrichtigung können einem Zeiger auf **NMHDR** oder ein Zeiger auf **LV\_KEYDOWN** umgewandelt werden entweder übergeben werden.  
  
 **Benachrichtigungen häufig zu allen neuen Windows\-Steuerelementen**  
  
 Einige Benachrichtigungen sind allen neuen Windows\-Steuerelementen häufig.  Diese Benachrichtigungen übergeben einen Zeiger auf eine **NMHDR**\-Struktur.  
  
|Benachrichtigungscode|Gesendet da|  
|---------------------------|-----------------|  
|**NM\_CLICK**|Benutzer klicken auf linke Maustaste im Steuerelement|  
|**NM\_DBLCLK**|Benutzer doppelt geklickt hat auf linke Maustaste im Steuerelement|  
|**NM\_RCLICK**|Benutzer klicken auf rechten Maustaste in Steuerelement|  
|**NM\_RDBLCLK**|Benutzer doppelt geklickt hat auf rechten Maustaste in Steuerelement|  
|**NM\_RETURN**|Benutzer könnten die EINGABETASTE während Steuerelement den Eingabefokus hat|  
|**NM\_SETFOCUS**|Steuerelement ist angegebener Eingabefokus erwiesen|  
|**NM\_KILLFOCUS**|Steuerelement verloren Eingabefokus hat|  
|**NM\_OUTOFMEMORY**|Steuerelement könnte einen Vorgang nicht abgeschlossen werden, da nicht genügend verfügbarer Arbeitsspeicher hat|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON\_NOTIFY: Meldungen der Behandlungs\-WM NOTIFY in MFC\-Anwendungen  
 Die `CWnd::OnNotify` Handlebenachrichtigungsmeldungen func.  Die Standardimplementierung überprüft die Meldungszuordnung, sodass Benachrichtigungshandler aufrufen.  Im Allgemeinen überschreiben Sie nicht `OnNotify`.  Stattdessen stellen Sie eine Handlerfunktion bereit und fügen einen Eintrag in der Meldungszuordnung für diesen Handler der Meldungszuordnung der Klasse des Besitzerfensters hinzu.  
  
 Der Klassen\-Assistent, zum ClassWizard\-Eigenschaftenblatt, kann den `ON_NOTIFY` Eintrag in der Meldungszuordnung erstellen und mit einer Skeletthandlerfunktion bereitgestellt.  Weitere Informationen zur Verwendung von die, um dies zu erleichtern, finden Sie unter [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
 Das `ON_NOTIFY` Meldungszuordnungsmakro hat die folgende Syntax:  
  
```  
  
ON_NOTIFY( wNotifyCode, id, memberFxn )  
```  
  
 von wo die kursiv gedruckten Parameter ersetzt werden:  
  
 `wNotifyCode`  
 Der Code, um die Benachrichtigung, wie **LVN\_KEYDOWN** behandelt werden kann.  
  
 `id`  
 Der untergeordnete Bezeichner des Steuerelements, für das die Benachrichtigung gesendet wird.  
  
 `memberFxn`  
 Die Memberfunktion, aufgerufen werden, wenn diese Benachrichtigung gesendet wird.  
  
 muss die Memberfunktion mit folgendem Prototyp deklariert werden:  
  
```  
  
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## Hinweise  
 wobei die kursiv gedruckten Parameter sind:  
  
 `pNotifyStruct`  
 Ein Zeiger auf Benachrichtigungsstruktur, wie im Abschnitt oben beschrieben.  
  
 *result*  
 Ein Zeiger auf den Ergebniscode, den Sie festlegen, bevor Sie zurückkehren.  
  
## Beispiel  
 Um anzugeben dass Sie die Memberfunktion `OnKeydownList1`**LVN\_KEYDOWN** Meldungen von `CListCtrl` verarbeiten soll mit der ID `IDC_LIST1`, müsste die verwenden um Folgendes der Meldungszuordnung hinzuzufügen:  
  
```  
ON_NOTIFY( LVN_KEYDOWN, IDC_LIST1, OnKeydownList1 )  
```  
  
 Im Beispiel oben, ist die Funktion, die durch die bereitgestellt wird:  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
   LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;  
   // TODO: Add your control notification handler  
   //       code here  
  
   *pResult = 0;  
}  
```  
  
 Beachten Sie, dass die einen Zeiger des richtigen Typs automatisch bereitstellt.  Sie können auf die Benachrichtigungsstruktur entweder von `pNMHDR` oder `pLVKeyDow` zugreifen.  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON\_NOTIFY\_RANGE  
 Wenn Sie dieselbe **WM\_NOTIFY** Nachricht für einen Satz von Steuerelementen verarbeiten müssen, können Sie **ON\_NOTIFY\_RANGE** anstelle von `ON_NOTIFY` verwenden.  Möglicherweise haben Sie eine Gruppe von Schaltflächen, für die Sie die gleiche Aktion für eine bestimmte Benachrichtigung ausführen möchten.  
  
 Wenn Sie **ON\_NOTIFY\_RANGE** verwenden, geben Sie einen zusammenhängenden Bereich von untergeordneten Bezeichner, sodass die bearbeiten die Benachrichtigung durch Angeben der untergeordneten Bezeichner von Anfang und Ende des Bereichs.  
  
 Der Klassen\-Assistent behandelt keine **ON\_NOTIFY\_RANGE**; um ihn verwenden zu können, müssen Sie die Meldungszuordnung bearbeiten sich.  
  
 Der Eintrag in der Meldungszuordnung und der Funktionsprototyp für **ON\_NOTIFY\_RANGE** sind, wie folgt:  
  
```  
  
ON_NOTIFY_RANGE(   
wNotifyCode  
,   
id  
,   
idLast  
,   
memberFxn  
 )  
  
```  
  
 von wo die kursiv gedruckten Parameter ersetzt werden:  
  
 `wNotifyCode`  
 Der Code, um die Benachrichtigung, wie **LVN\_KEYDOWN** behandelt werden kann.  
  
 `id`  
 Der erste Bezeichner in zusammenhängenden Bereich von Bezeichnern.  
  
 `idLast`  
 Der letzte Bezeichner in zusammenhängenden Bereich von Bezeichnern.  
  
 `memberFxn`  
 Die Memberfunktion, aufgerufen werden, wenn diese Benachrichtigung gesendet wird.  
  
 muss die Memberfunktion mit folgendem Prototyp deklariert werden:  
  
```  
  
afx_msg void memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## Hinweise  
 wobei die kursiv gedruckten Parameter sind:  
  
 `id`  
 Der untergeordnete Bezeichner des Steuerelements, das die Benachrichtigung gesendet.  
  
 `pNotifyStruct`  
 Ein Zeiger auf Benachrichtigungsstruktur, wie oben beschrieben.  
  
 *result*  
 Ein Zeiger auf den Ergebniscode, den Sie festlegen, bevor Sie zurückkehren.  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON\_NOTIFY\_EX, ON\_NOTIFY\_EX\_RANGE  
 Wenn Sie mehr als ein Objekt in Benachrichtigungsrouting eine Meldung verarbeiten soll, können Sie **ON\_NOTIFY\_EX** \(oder **ON\_NOTIFY\_EX\_RANGE**\) und nicht `ON_NOTIFY` \(oder **ON\_NOTIFY\_RANGE**\).  Der einzige Unterschied zwischen der **EX**\-Version und der reguläre Version ist, dass die Memberfunktion, die für die **EX**\-Version aufgerufen wird, **BOOL** zurückgibt, die angibt, ob Meldungsverarbeitung von fortgesetzt werden soll.  Die Rückgabe von **FALSE** dieser Funktion ermöglicht Ihnen, die gleiche Meldung in mehr als einem Objekt zu verarbeiten.  
  
 Der Klassen\-Assistent behandelt nicht **ON\_NOTIFY\_EX** oder **ON\_NOTIFY\_EX\_RANGE**; wenn Sie einen davon verwenden möchten, müssen Sie die Meldungszuordnung bearbeiten sich.  
  
 Der Eintrag in der Meldungszuordnung und der Funktionsprototyp für **ON\_NOTIFY\_EX** und **ON\_NOTIFY\_EX\_RANGE** sind die folgenden.  Die Bedeutung der Parameter sind mit denen für Nicht\- die **EX**\-Versionen.  
  
```  
  
ON_NOTIFY_EX( nCode, id, memberFxn ) ON_NOTIFY_EX_RANGE( wNotifyCode, id, idLast, memberFxn )  
```  
  
 Der Prototyp für beide der obigen ist identisch:  
  
```  
  
afx_msg BOOL memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## Hinweise  
 In beiden Fällen unterbricht `id` den untergeordneten Bezeichner des Steuerelements an, die die Benachrichtigung gesendet.  
  
 Die Funktion muss **TRUE** zurückgeben, wenn die Benachrichtigung vollständig oder **FALSE** behandelt wurde, wenn andere Objekte im Befehlsrouting eine Möglichkeit haben, die Meldung zu bearbeiten.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)