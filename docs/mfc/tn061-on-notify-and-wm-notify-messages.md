---
title: 'TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen'
ms.date: 06/28/2018
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
ms.openlocfilehash: aa1efb628ee45be3dfaee320cf64c4b2cbb91f04
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302236"
---
# <a name="tn061-on_notify-and-wm_notify-messages"></a>TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Technische Hinweis enthält Hintergrundinformationen zur neuen WM_NOTIFY Meldung und beschreibt die empfohlene (und gängigste) Methode zum Verarbeiten von WM_NOTIFY Meldungen in ihrer MFC-Anwendung.

**Benachrichtigungs Meldungen in Windows 3. x**

In Windows 3. x benachrichtigen die Steuerelemente ihre übergeordneten Ereignisse, wie z. b. Mausklicks, Änderungen an Inhalt und Auswahl, und steuern die Hintergrund Darstellung, indem eine Meldung an das übergeordnete Element gesendet wird. Einfache Benachrichtigungen werden als spezielle WM_COMMAND Nachrichten gesendet, wobei der Benachrichtigungs Code (z. b. BN_CLICKED) und die Steuerelement-ID in *wParam* und das Handle des Steuer Elements in *LPARAM*verpackt werden. Beachten Sie, dass es keine Möglichkeit gibt, zusätzliche Daten zu übergeben, da *wParam* und *LPARAM* voll sind. – diese Nachrichten können nur eine einfache Benachrichtigung sein. Beispielsweise gibt es in der BN_CLICKED Benachrichtigung keine Möglichkeit, Informationen über die Position des Mauszeigers zu senden, wenn auf die Schaltfläche geklickt wurde.

Wenn Steuerelemente in Windows 3. x eine Benachrichtigungs Meldung senden müssen, die zusätzliche Daten enthält, verwenden Sie eine Vielzahl von speziellen Nachrichten, einschließlich WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_ Chartoitem, WM_VKEYTOITEM usw. Diese Nachrichten können wieder auf das Steuerelement reflektiert werden, das Sie gesendet hat. Weitere Informationen finden Sie unter [TN062: Message Reflection for Windows Controls](../mfc/tn062-message-reflection-for-windows-controls.md).

**Benachrichtigungs Meldungen in Win32**

Für Steuerelemente, die in Windows 3,1 vorhanden waren, verwendet die Win32-API die meisten Benachrichtigungs Meldungen, die in Windows 3. x verwendet wurden. Win32 fügt jedoch auch eine Reihe komplexer, komplexer Steuerelemente hinzu, die in Windows 3. x unterstützt werden. Häufig müssen diese Steuerelemente zusätzliche Daten mit ihren Benachrichtigungs Nachrichten senden. Anstatt für jede neue Benachrichtigung, die zusätzliche Daten benötigt, eine neue **WM_** <strong>\*</strong> Meldung hinzuzufügen, haben die Designer der Win32-API entschieden, nur eine Nachricht hinzuzufügen, WM_NOTIFY, die eine beliebige Menge an zusätzlichen Daten auf standardisierte Weise übergeben kann.

WM_NOTIFY Meldungen enthalten die ID des Steuer Elements, das die Nachricht in *wParam* sendet, und einen Zeiger auf eine Struktur in *LPARAM*. Diese Struktur ist entweder eine **NMHDR** -Struktur oder eine größere Struktur, deren erstes Mitglied eine **NMHDR** -Struktur aufweist. Beachten Sie, dass ein Zeiger auf diese Struktur als Zeiger auf eine **NMHDR** oder als Zeiger auf die größere Struktur verwendet werden kann, je nachdem, wie Sie ihn umwandeln, da der **NMHDR** -Member erstmalig ist.

In den meisten Fällen zeigt der Zeiger auf eine größere Struktur, und Sie müssen ihn bei der Verwendung umwandeln. Nur einige Benachrichtigungen, wie z. b. die allgemeinen Benachrichtigungen (deren Namen mit **NM_** beginnen) und die TTN_SHOW-und TTN_POP Benachrichtigungen des QuickInfo-Steuer Elements, werden tatsächlich in einer **NMHDR** -Struktur verwendet.

Die **NMHDR** -Struktur oder das erste Member enthält das Handle und die ID des Steuer Elements, das die Nachricht sendet, und den Benachrichtigungs Code (z. b. TTN_SHOW). Das Format der **NMHDR** -Struktur ist unten dargestellt:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

Für eine TTN_SHOW Meldung wird das **Codemember** auf TTN_SHOW festgelegt.

Die meisten Benachrichtigungen übergeben einen Zeiger auf eine größere Struktur, die eine **NMHDR** -Struktur als ersten Member enthält. Betrachten Sie beispielsweise die Struktur, die von der LVN_KEYDOWN Benachrichtigungs Meldung des Listen Ansichts Steuer Elements verwendet wird, die gesendet wird, wenn eine Taste in einem Listenansicht-Steuerelement gedrückt wird. Der Zeiger verweist auf eine **LV_KEYDOWN** -Struktur, die wie unten dargestellt definiert ist:

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

Beachten Sie, dass der Zeiger, der in der Benachrichtigungs Meldung angezeigt wird, in einen Zeiger auf einen **NMHDR** oder einen Zeiger auf einen **LV_KEYDOWN**umgewandelt werden kann, da der **NMHDR** -Member in dieser Struktur an erster Stelle steht.

**Benachrichtigungen, die allen neuen Windows-Steuerelementen gemeinsam sind**

Einige Benachrichtigungen sind von allen neuen Windows-Steuerelementen gemeinsam. Diese Benachrichtigungen übergeben einen Zeiger auf eine **NMHDR** -Struktur.

|Benachrichtigungs Code|Gesendet aufgrund|
|-----------------------|------------------|
|NM_CLICK|Vom Benutzer angeklickte linke Maustaste im Steuerelement|
|NM_DBLCLK|Benutzer hat auf die linke Maustaste im Steuerelement Doppel geklickt.|
|NM_RCLICK|Benutzer hat auf das Steuerelement mit der rechten Maustaste geklickt.|
|NM_RDBLCLK|Benutzer, auf den mit der rechten Maustaste im Steuerelement Doppel geklickt wurde|
|NM_RETURN|Benutzer hat die EINGABETASTE gedrückt, während das Steuerelement den Eingabefokus besitzt|
|NM_SETFOCUS|Das Steuerelement hat den Eingabefokus erhalten.|
|NM_KILLFOCUS|Steuerelement hat den Eingabefokus verloren.|
|NM_OUTOFMEMORY|Das Steuerelement konnte einen Vorgang nicht beenden, weil nicht genügend Arbeitsspeicher verfügbar war.|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a>ON_NOTIFY: Verarbeiten von WM_NOTIFY-Nachrichten in MFC-Anwendungen

Die-Funktion `CWnd::OnNotify` die Benachrichtigungs Meldungen verarbeitet. Die Standard Implementierung überprüft die Meldungs Zuordnung für Benachrichtigungs Handler, um aufzurufen. Im allgemeinen überschreiben Sie `OnNotify`nicht. Stattdessen stellen Sie eine Handlerfunktion bereit und fügen einen Meldungs Zuordnungs Eintrag für diesen Handler der Meldungs Zuordnung der Klasse des Besitzer Fensters hinzu.

Mit dem Klassen-Assistenten können Sie über das Klassen-Assistent-Eigenschaften Blatt den ON_NOTIFY Message-Map-Eintrag erstellen und eine Skeleton-Handlerfunktion bereitstellen. Weitere Informationen zur einfacheren Verwendung von ClassWizard finden Sie unter [Mapping messages to Functions](../mfc/reference/mapping-messages-to-functions.md).

Das ON_NOTIFY Message-Map-Makro weist die folgende Syntax auf:

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

mit folgenden Parametern:

*wNotifyCode*<br/>
Der Code für die zu behandelnde Benachrichtigungs Meldung, z. b. LVN_KEYDOWN.

*ID*<br/>
Der untergeordnete Bezeichner des Steuer Elements, für das die Benachrichtigung gesendet wird.

*memberFxn*<br/>
Die Member-Funktion, die beim Senden dieser Benachrichtigung aufgerufen werden soll.

Die Member-Funktion muss mit dem folgenden Prototyp deklariert werden:

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

mit folgenden Parametern:

*pNotifyStruct*<br/>
Ein Zeiger auf die Benachrichtigungs Struktur, wie im obigen Abschnitt beschrieben.

*result*<br/>
Ein Zeiger auf den Ergebniscode, den Sie vor der Rückgabe festlegen.

## <a name="example"></a>Beispiel

Um anzugeben, dass die Element Funktion `OnKeydownList1` LVN_KEYDOWN Nachrichten aus dem `CListCtrl` verarbeiten soll, dessen ID `IDC_LIST1`ist, verwenden Sie ClassWizard, um der Meldungs Zuordnung Folgendes hinzuzufügen:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

Im obigen Beispiel lautet die von ClassWizard bereitgestellte Funktion wie folgt:

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

Beachten Sie, dass ClassWizard einen Zeiger vom richtigen Typ automatisch bereitstellt. Sie können entweder über *pNMHDR* oder *plvkeydow*auf die Benachrichtigungs Struktur zugreifen.

##  <a name="_mfcnotes_on_notify_range"></a>ON_NOTIFY_RANGE

Wenn Sie dieselbe WM_NOTIFY Nachricht für eine Reihe von Steuerelementen verarbeiten müssen, können Sie ON_NOTIFY_RANGE anstelle von ON_NOTIFY verwenden. Beispielsweise können Sie über eine Reihe von Schaltflächen verfügen, für die Sie die gleiche Aktion für eine bestimmte Benachrichtigungs Meldung ausführen möchten.

Wenn Sie ON_NOTIFY_RANGE verwenden, geben Sie einen zusammenhängenden Bereich von untergeordneten bezeichaten an, für die die Benachrichtigungs Meldung verarbeitet werden soll, indem Sie die untergeordneten Elemente für den Anfang und das Ende des Bereichs angeben.

Der ClassWizard behandelt ON_NOTIFY_RANGE nicht. um es zu verwenden, müssen Sie Ihre Meldungs Zuordnung selbst bearbeiten.

Der Nachrichten Zuordnungs Eintrag und der Funktionsprototyp für ON_NOTIFY_RANGE lauten wie folgt:

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

mit folgenden Parametern:

*wNotifyCode*<br/>
Der Code für die zu behandelnde Benachrichtigungs Meldung, z. b. LVN_KEYDOWN.

*ID*<br/>
Der erste Bezeichner im zusammenhängenden Bereich von Bezeichnern.

*idLast*<br/>
Der letzte Bezeichner im zusammenhängenden Bereich von Bezeichnern.

*memberFxn*<br/>
Die Member-Funktion, die beim Senden dieser Benachrichtigung aufgerufen werden soll.

Die Member-Funktion muss mit dem folgenden Prototyp deklariert werden:

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

mit folgenden Parametern:

*ID*<br/>
Der untergeordnete Bezeichner des Steuer Elements, das die Benachrichtigung gesendet hat.

*pNotifyStruct*<br/>
Ein Zeiger auf die Benachrichtigungs Struktur, wie oben beschrieben.

*result*<br/>
Ein Zeiger auf den Ergebniscode, den Sie vor der Rückgabe festlegen.

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a>ON_NOTIFY_EX ON_NOTIFY_EX_RANGE

Wenn Sie mehr als ein Objekt im Benachrichtigungs Routing verwenden möchten, um eine Nachricht zu verarbeiten, können Sie ON_NOTIFY_EX (oder ON_NOTIFY_EX_RANGE) anstelle ON_NOTIFY (oder ON_NOTIFY_RANGE) verwenden. Der einzige Unterschied zwischen der **Ex** -Version und der regulären Version besteht darin, dass die für die **Ex** -Version aufgerufene Element Funktion einen **booleschen** Wert zurückgibt, der angibt, ob die Nachrichtenverarbeitung fortgesetzt werden soll Durch das Zurückgeben von " **false** " aus dieser Funktion können Sie dieselbe Nachricht in mehr als einem Objekt verarbeiten.

Der Klassen-Assistent verarbeitet ON_NOTIFY_EX oder ON_NOTIFY_EX_RANGE nicht. Wenn Sie einen von beiden verwenden möchten, müssen Sie Ihre Meldungs Zuordnung selbst bearbeiten.

Der Nachrichten Zuordnungs Eintrag und der Funktionsprototyp für ON_NOTIFY_EX und ON_NOTIFY_EX_RANGE lauten wie folgt. Die Bedeutungen der Parameter sind die gleichen wie für die nicht-**Ex** -Versionen.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

Der Prototyp für beide oben genannten ist identisch:

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

In beiden Fällen enthält *ID* den untergeordneten Bezeichner des Steuer Elements, das die Benachrichtigung gesendet hat.

Die Funktion muss " **true** " zurückgeben, wenn die Benachrichtigungs Meldung vollständig verarbeitet wurde, oder " **false** ", wenn andere Objekte im Befehls Routing die Möglichkeit haben sollen, die Nachricht zu verarbeiten.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
