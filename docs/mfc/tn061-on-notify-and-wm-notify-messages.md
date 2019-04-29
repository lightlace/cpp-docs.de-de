---
title: 'TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen'
ms.date: 06/28/2018
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
ms.openlocfilehash: 74eb39a855da3ff3e6da7f14a76bf0804919826d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399576"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Diese technische Hinweis enthält Hintergrundinformationen für die neue WM_NOTIFY-Nachricht und wird beschrieben, wie empfohlen (und am häufigsten verwendeten) WM_NOTIFY-Meldungen in der MFC-Anwendung zu verarbeiten.

**Von Benachrichtigungsmeldungen in Windows 3.x**

In Windows 3.x, Benachrichtigung Steuerelemente ihren übergeordneten Elementen von Ereignissen wie Mausklicks, Inhalt und Auswahl und das Hintergrund Zeichnen von Steuerelementen durch Senden einer Nachricht an das übergeordnete Element ändert. Einfache Benachrichtigungen als spezielle WM_COMMAND-Meldungen, mit dem Notification-Code (z. B. BN_CLICKED) gesendet und Steuerelement-ID in gepackt *wParam* und das Handle des Steuerelements in *lParam*. Beachten Sie, dass seit *wParam* und *lParam* voll ist, besteht keine Möglichkeit, zusätzlichen Daten übergeben werden, diese Nachrichten können nur einfache Benachrichtigung sein. Beispielsweise in der Benachrichtigung BN_CLICKED besteht keine Möglichkeit zum Senden von Informationen über den Speicherort des Mauszeigers, wenn die Schaltfläche geklickt wurde.

Wenn Steuerelemente in Windows 3.x müssen eine Benachrichtigung, die zusätzliche Daten enthält senden, verwenden sie eine Reihe von Meldungen für spezielle Zwecke, einschließlich WM_CTLCOLOR WM_VSCROLL WM_HSCROLL WM_DRAWITEM WM_MEASUREITEM WM_COMPAREITEM WM_DELETEITEM, WM_ CHARTOITEM WM_VKEYTOITEM und So weiter. Diese Nachrichten können an das Steuerelement gespiegelt werden, die sie gesendet wurden. Weitere Informationen finden Sie unter [TN062: Nachricht Reflektion für Windows-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).

**Von Benachrichtigungsmeldungen in Win32**

Für Steuerelemente, die in Windows 3.1 vorhanden waren, verwendet die Win32-API die Benachrichtigungsnachrichten erstellt werden, mit denen, die meisten in Windows 3.x. Allerdings Win32 sowie eine Reihe von selbst ausgereifte, komplexe Kontrollmechanismen, die in Windows unterstützt 3.x. In vielen Fällen müssen diese Steuerelemente zusätzliche Daten in die benachrichtigungsmeldungen zu senden. Anstatt das Hinzufügen eines neuen **WM_** <strong>\*</strong> Nachrichteneigenschaften werden für jede neue Benachrichtigung, die zusätzliche Daten, die Entwickler von Win32-API benötigt ausgewählt haben, nur eine Nachricht, WM_NOTIFY, hinzufügen, die einem übergeben werden können Menge zusätzlicher Daten auf standardisierte Weise.

WM_NOTIFY-Meldungen enthalten, die ID des Steuerelements, das Senden der Nachricht in *wParam* und einen Zeiger auf eine Struktur in *lParam*. Diese Struktur ist entweder ein **NMHDR** Struktur oder eine größere Struktur, die eine **NMHDR** Struktur wie des ersten Elements. Beachten Sie, dass seit der **NMHDR** Member ersten, als entweder einen Zeiger auf ein Zeiger auf diese Struktur verwendet werden eine **NMHDR** oder als Zeiger auf die größere Struktur, je nachdem, wie Sie ihn umwandeln.

In den meisten Fällen der Zeiger verweist auf eine größere-Struktur, und müssen Sie ihn umwandeln, wenn Sie sie verwenden. In nur wenigen Benachrichtigungen, wie allgemeine Benachrichtigungen (, deren Namen beginnen mit **NM_**) und das Tool Tipp des Steuerelements TTN_SHOW und TTN_POP Benachrichtigungen, die eine **NMHDR** Struktur, die tatsächlich verwendet werden.

Die **NMHDR** Struktur oder das erste Element enthält, das Handle und die ID des Steuerelements, das Senden der Nachricht und der Benachrichtigungscode (z. B. TTN_SHOW). Das Format der **NMHDR** Struktur wird unten gezeigt:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

Bei einer Nachricht TTN_SHOW der **Code** Member auf TTN_SHOW fest.

Die meisten Benachrichtigungen übergeben einen Zeiger auf eine größere Datenstruktur, enthält ein **NMHDR** Struktur wie des ersten Elements. Betrachten Sie beispielsweise die Struktur, die von der Listenansicht-Steuerelement des LVN_KEYDOWN-Benachrichtigung, die gesendet wird, wenn eine Taste, in einem Listenansicht-Steuerelement gedrückt wird verwendet. Der Zeiger verweist auf eine **LV_KEYDOWN** -Struktur, die definiert wird, wie unten dargestellt:

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

Beachten Sie, dass seit der **NMHDR** Member an erster Stelle in dieser Struktur, die Zeiger, die Sie in der Benachrichtigung übergeben umgewandelt werden kann, um entweder einen Zeiger auf ein **NMHDR** oder ein Zeiger auf ein **LV_KEYDOWN** .

**Benachrichtigungen, die für alle neuen Windows-Steuerelemente gelten**

Einige Benachrichtigungen gelten für alle neuen Windows-Steuerelemente zur Verfügung. Diese Benachrichtigungen übergeben, einen Zeiger auf ein **NMHDR** Struktur.

|Benachrichtigungscode|Gesendet, weil|
|-----------------------|------------------|
|NM_CLICK|Benutzer klicken auf die linke Maustaste im Steuerelement|
|NM_DBLCLK|Benutzer doppelklickt linke Maustaste im Steuerelement|
|NM_RCLICK|Benutzer klickt rechten Maustaste im Steuerelement|
|NM_RDBLCLK|Benutzer doppelklickt rechten Maustaste im Steuerelement|
|NM_RETURN|Benutzer, die die EINGABETASTE gedrückt, während das Steuerelement den Eingabefokus besitzt|
|NM_SETFOCUS|Steuerelement verfügt über Eingabefokus erhalten|
|NM_KILLFOCUS|Steuerelement hat den Eingabefokus verloren.|
|NM_OUTOFMEMORY|Steuerelement konnte einen Vorgang nicht abschließen, weil nicht genügend Arbeitsspeicher verfügbar war|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON_NOTIFY: Verarbeiten von WM_NOTIFY-Meldungen in MFC-Anwendungen

Die Funktion `CWnd::OnNotify` benachrichtigungsmeldungen behandelt. Die Standardimplementierung überprüft die meldungszuordnung für Benachrichtigungshandler aufrufen. Im Allgemeinen nicht überschreiben `OnNotify`. Sie können stattdessen bieten eine Handlerfunktion und die meldungszuordnung Ihres Besitzerfensters-Klasse eine Meldungszuordnungseintrags für diesen Handler hinzugefügt.

Klassen-Assistenten, über das Eigenschaftenblatt des Klassen-Assistenten, erstellen die Meldungszuordnungseintrags ON_NOTIFY und bieten Ihnen eine Skelett Handlerfunktion. Weitere Informationen zur Verwendung der Klassen-Assistent, um dies zu vereinfachen, finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

Die meldungszuordnung ON_NOTIFY-Makro hat die folgende Syntax:

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

mit folgenden Parametern:

*wNotifyCode*<br/>
Der Code der benachrichtigungsmeldung, wie z. B. LVN_KEYDOWN behandelt werden.

*ID*<br/>
Der untergeordnete Bezeichner des Steuerelements für die die Benachrichtigung gesendet wird.

*memberFxn*<br/>
Die Memberfunktion aufgerufen werden, wenn diese Benachrichtigung gesendet wird.

Ihre Memberfunktion muss mit dem folgenden Prototyp deklariert werden:

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

mit folgenden Parametern:

*pNotifyStruct*<br/>
Ein Zeiger auf die Benachrichtigungsstruktur, wie im vorherigen Abschnitt beschrieben.

*result*<br/>
Ein Zeiger auf den Ergebniscode müssen Sie festlegen, bevor Sie zurückkehren.

## <a name="example"></a>Beispiel

Um anzugeben, dass die Member-Funktion soll `OnKeydownList1` LVN_KEYDOWN Nachrichten von behandelt die `CListCtrl` , deren ID `IDC_LIST1`, verwenden Sie Klassen-Assistenten, um Ihre meldungszuordnung Folgendes hinzugefügt:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

Im obigen Beispiel ist die Funktion, die von den Klassen-Assistent bereitgestellt:

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

Beachten Sie, dass Klassen-Assistent automatisch einen Zeiger des richtigen Typs bereitstellt. Sie können die Benachrichtigungsstruktur zugreifen, entweder durch *pNMHDR* oder *pLVKeyDow*.

##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE

Wenn Sie die gleiche WM_NOTIFY-Nachricht für einen Satz von Steuerelementen verarbeiten müssen, können Sie ON_NOTIFY_RANGE statt ON_NOTIFY. Beispielsweise müssen Sie eine Reihe von Schaltflächen möglicherweise für die Sie die gleiche Aktion für eine bestimmte Meldung ausführen möchten.

Wenn Sie ON_NOTIFY_RANGE verwenden, geben Sie einen zusammenhängenden Bereich von untergeordneten Bezeichner für das die benachrichtigungsmeldung behandelt, indem Sie am Anfang und beenden untergeordneten Bezeichner des Bereichs.

ON_NOTIFY_RANGE behandelt-Klassen-Assistenten nicht; um es zu verwenden, müssen Sie die Zuordnung der Nachricht selbst bearbeiten.

Die Meldungszuordnungseintrags und Funktionsprototyp für ON_NOTIFY_RANGE lauten folgendermaßen:

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

mit folgenden Parametern:

*wNotifyCode*<br/>
Der Code der benachrichtigungsmeldung, wie z. B. LVN_KEYDOWN behandelt werden.

*ID*<br/>
Der erste Bezeichner im zusammenhängenden Bereich von Bezeichnern.

*idLast*<br/>
Der letzte Bezeichner im zusammenhängenden Bereich von Bezeichnern.

*memberFxn*<br/>
Die Memberfunktion aufgerufen werden, wenn diese Benachrichtigung gesendet wird.

Ihre Memberfunktion muss mit dem folgenden Prototyp deklariert werden:

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

mit folgenden Parametern:

*ID*<br/>
Der untergeordnete Bezeichner des Steuerelements, das die Benachrichtigung gesendet werden soll.

*pNotifyStruct*<br/>
Ein Zeiger auf die Benachrichtigungsstruktur, wie oben beschrieben.

*result*<br/>
Ein Zeiger auf den Ergebniscode müssen Sie festlegen, bevor Sie zurückkehren.

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

Wenn mehr als ein Objekt in der Benachrichtigung, routing, um eine Nachricht verarbeitet werden soll, können Sie ON_NOTIFY_EX (oder ON_NOTIFY_EX_RANGE) anstatt ON_NOTIFY (oder ON_NOTIFY_RANGE) verwenden. Der einzige Unterschied zwischen der **EX** Version und die Standardversion ist, dass für die Memberfunktion aufgerufen der **EX** Version zurückgibt eine **"bool"** , der angibt, und zwar unabhängig davon, ob Es sollte die Verarbeitung von Nachrichten fortgesetzt werden. Zurückgeben von **"false"** von dieser Funktion können Sie dieselbe Nachricht in mehr als ein Objekt zu verarbeiten.

Klassen-Assistent wird nicht ON_NOTIFY_EX oder ON_NOTIFY_EX_RANGE behandelt. Wenn Sie beide Buildtypen verwenden möchten, müssen Sie die Zuordnung der Nachricht selbst bearbeiten.

Die Meldungszuordnungseintrags und Funktionsprototyp für ON_NOTIFY_EX und ON_NOTIFY_EX_RANGE sind wie folgt. Die Bedeutung der Parameter werden genauso wie bei anderen**EX** Versionen.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

Der Prototyp für beide oben genannten Schritte ist das gleiche:

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

In beiden Fällen *Id* enthält den untergeordnete Bezeichner des Steuerelements, das die Benachrichtigung gesendet.

Die Funktion zurückgeben muss **"true"** , wenn die Nachricht vollständig verarbeitet wurde oder **"false"** Wenn andere Objekte in das Befehlsrouting eine Chance zur Verarbeitung der Nachricht haben soll.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
