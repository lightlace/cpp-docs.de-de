---
title: 'TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4afa05fa8bf21b6e324e9ac14a1b092933a99d55
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954421"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY- und WM_NOTIFY-Meldungen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem technischen Hinweis enthält Hintergrundinformationen zu den neuen WM_NOTIFY-Meldung und wird beschrieben, wie empfohlen (und häufigste) verarbeiten WM_NOTIFY-Meldungen in der MFC-Anwendung.  
  
 **Benachrichtigungsmeldungen in Windows 3.x**  
  
 In Windows 3.x, Benachrichtigung ihren übergeordneten Elementen von Ereignissen wie Mausklicks, Steuerelemente im Inhalt und die Auswahl und Kontrolle Hintergrund Zeichnen durch Senden einer Nachricht an das übergeordnete Element ändert. Einfache Benachrichtigungen als spezielle WM_COMMAND-Meldungen, mit der Benachrichtigungscode (z. B. BN_CLICKED) gesendet, und die Steuerelement-ID zurück, der in *wParam* und das Handle des Steuerelements in *lParam*. Beachten Sie, dass seit *wParam* und *lParam* voll ist, besteht keine Möglichkeit, zusätzlichen Daten übergeben werden, diese Nachrichten können nur einfache Benachrichtigung sein. Für die Instanz, in der Benachrichtigung BN_CLICKED besteht keine Möglichkeit zum Senden von Informationen über den Speicherort des Mauszeigers auf die Schaltfläche geklickt wurde.  
  
 Wenn Steuerelemente in Windows müssen 3.x eine Benachrichtigung, die zusätzliche Daten enthält senden, verwenden sie eine Vielzahl von zweckgebundene Nachrichten, einschließlich WM_CTLCOLOR WM_VSCROLL WM_HSCROLL WM_DRAWITEM WM_MEASUREITEM WM_COMPAREITEM WM_DELETEITEM, WM_ CHARTOITEM WM_VKEYTOITEM und So weiter. Diese Nachrichten werden an das Steuerelement sichtbar, die sie gesendet wurden. Weitere Informationen finden Sie unter [TN062: Meldung Reflektion für Windows-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
 **Benachrichtigungsmeldungen in Win32**  
  
 Für Steuerelemente, die in Windows 3.1 oder höher vorhanden waren, verwendet die Win32-API die benachrichtigungsmeldungen, mit denen, die meisten in Windows 3.x. Win32 auch bewirkt allerdings eine Anzahl von anspruchsvolle und komplexe Steuerelemente in Windows unterstützt 3.x. Häufig müssen diese Steuerelemente, um zusätzliche Daten mit ihren benachrichtigungsmeldungen zu senden. Anstatt das Hinzufügen eines neuen **WM_\***  Nachricht für jede neue Benachrichtigung, die zusätzliche Daten, die Entwickler von Win32-API benötigt ausgewählt haben, nur eine Nachricht, WM_NOTIFY, hinzufügen, die beliebige Anzahl von zusätzlichen Daten im übergeben können eine standardisierte.  
  
 WM_NOTIFY-Meldungen enthalten, die ID des Steuerelements, das Senden der Nachricht in *wParam* und einen Zeiger auf eine Struktur in *lParam*. Diese Struktur ist entweder ein **NMHDR** Struktur oder einige größere-Struktur, eine **NMHDR** Struktur als des ersten Elements. Beachten Sie, dass seit der **NMHDR** angehört, die erste, ein Zeiger auf diese Struktur kann verwendet werden, als entweder einen Zeiger auf eine **NMHDR** oder als Zeiger auf den größeren Struktur je nachdem, wie Sie umwandeln.  
  
 Klicken Sie in den meisten Fällen zeigen der Mauszeiger auf einer größeren Struktur, und Sie müssen es umwandeln, wenn Sie ihn verwenden. In nur wenigen Benachrichtigungen, z. B. die allgemeinen Benachrichtigungen (, deren Namen beginnen mit **NM_**) und das Tool Tipp des Steuerelements TTN_SHOW und TTN_POP Benachrichtigungen, ist ein **NMHDR** Struktur tatsächlich verwendet.  
  
 Die **NMHDR** Struktur oder das erste Element enthält, das Handle und die ID des Steuerelements, das Senden der Nachricht und die Benachrichtigungscode (z. B. TTN_SHOW). Das Format der **NMHDR** Struktur wird unten gezeigt:  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 Für eine Nachricht TTN_SHOW der **Code** Element würde auf TTN_SHOW festgelegt werden.  
  
 Die meisten Benachrichtigungen übergeben einen Zeiger auf einen größeren Struktur, enthält ein **NMHDR** Struktur als des ersten Elements. Betrachten Sie beispielsweise die Struktur von Listenansicht-Steuerelement des LVN_KEYDOWN-Benachrichtigung, die gesendet wird, wenn eine Taste, in einem Listenansicht-Steuerelement gedrückt wird verwendet. Der Zeiger verweist auf ein **LV_KEYDOWN** -Struktur, die definiert wird, wie unten dargestellt:  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 Beachten Sie, dass seit der **NMHDR** Member an erster Stelle in dieser Struktur, der Sie in der Benachrichtigung übergebenen sind Zeiger umgewandelt werden kann, entweder einen Zeiger auf eine **NMHDR** oder ein Zeiger auf ein **LV_KEYDOWN** .  
  
 **Benachrichtigungen, die alle neuen Windows-Steuerelementen gemeinsam sind**  
  
 Einige Benachrichtigungen beziehen sich auf alle neuen Windows-Steuerelemente. Diese Benachrichtigungen übergeben, einen Zeiger auf ein **NMHDR** Struktur.  
  
|Benachrichtigungscode|Da gesendet|  
|-----------------------|------------------|  
|NM_CLICK|Benutzer auf die linke Maustaste in das Steuerelement geklickt|  
|NM_DBLCLK|Benutzer doppelgeklickt linke Maustaste in das Steuerelement|  
|NM_RCLICK|Geklickt rechten Maustaste in das Steuerelement|  
|NM_RDBLCLK|Benutzer doppelgeklickt rechten Maustaste in das Steuerelement|  
|NM_RETURN|Benutzer, die die EINGABETASTE gedrückt, während das Steuerelement den Eingabefokus besitzt|  
|NM_SETFOCUS|Steuerelement Eingabefokus erhält|  
|NM_KILLFOCUS|Steuerelement hat Eingabefokus verloren.|  
|NM_OUTOFMEMORY|Steuerelement konnte einen Vorgang nicht abgeschlossen, da nicht genügend Arbeitsspeicher verfügbar war|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON_NOTIFY: Behandlung von WM_NOTIFY-Meldungen in MFC-Anwendungen  
 Die Funktion `CWnd::OnNotify` benachrichtigungsmeldungen behandelt. Die standardmäßige Implementierung überprüft die meldungszuordnung für Benachrichtigungshandler aufrufen. Im Allgemeinen nicht überschreiben `OnNotify`. Stattdessen geben Sie eine Handlerfunktion und die meldungszuordnung Ihres Besitzerfensters Klasse eine Meldungszuordnungseintrags für diesen Handler hinzuzufügen.  
  
 Klassen-Assistent, über das Eigenschaftenblatt ClassWizard kann erstellt die Meldungszuordnungseintrags ON_NOTIFY und bieten Ihnen eine Skeleton-Funktion. Weitere Informationen zur Verwendung von ClassWizard um dies zu vereinfachen, finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
 Das ON_NOTIFY meldungszuordnung Makro hat die folgende Syntax:  
  
```  
 
ON_NOTIFY(
wNotifyCode  ,  
id  ,
    memberFxn)  
 
```  
  
 wobei die kursiv Parameter durch ersetzt werden:  
  
 *wNotifyCode schalten*  
 Der Code für die Benachrichtigung, z. B. LVN_KEYDOWN behandelt werden.  
  
 *ID*  
 Der untergeordnete Bezeichner des Steuerelements für die die Benachrichtigung gesendet wird.  
  
 *memberFxn*  
 Die Memberfunktion aufgerufen werden, wenn diese Benachrichtigung gesendet wird.  
  
 Member-Funktion muss mit dem folgenden Prototyp deklariert werden:  
  
```  
 
afx_msg void  
memberFxn  
(NMHDR* 
pNotifyStruct  , LRESULT* result);

 
```  
  
## <a name="remarks"></a>Hinweise  
 wobei kursiv Parameter sind:  
  
 *pNotifyStruct*  
 Ein Zeiger auf die Benachrichtigungsstruktur, wie im vorherigen Abschnitt beschrieben.  
  
 *Ergebnis*  
 Ein Zeiger auf den Ergebniscode müssen Sie festlegen, bevor Sie zurückkehren.  
  
## <a name="example"></a>Beispiel  
 Zum angeben, dass Sie die Memberfunktion `OnKeydownList1` LVN_KEYDOWN Nachrichten von behandelt die `CListCtrl` , deren ID ist `IDC_LIST1`, verwenden Sie ClassWizard die meldungszuordnung Folgendes hinzu:  
  
```  
ON_NOTIFY(LVN_KEYDOWN,
    IDC_LIST1,
    OnKeydownList1)  
```  
  
 Im obigen Beispiel ist die Funktion von ClassWizard bereitgestellt:  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR; *// TODO: Add your control notification handler *//       code here  
 
 *pResult = 0;  
}  
```  
  
 Beachten Sie, dass Klassen-Assistent automatisch einen Zeiger des erforderlichen Typs bereitstellt. Sie können auf die Benachrichtigungsstruktur zugreifen, entweder durch *pNMHDR* oder *pLVKeyDow*.  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE  
 Wenn Sie die gleiche WM_NOTIFY-Meldung für einen Satz von Steuerelementen verarbeiten müssen, können Sie ON_NOTIFY_RANGE anstelle von ON_NOTIFY verwenden. Beispielsweise kann eine Reihe von Schaltflächen stehen Ihnen für die Sie die gleiche Aktion für eine bestimmte Meldung ausführen möchten.  
  
 Wenn Sie ON_NOTIFY_RANGE verwenden, geben Sie einen zusammenhängenden Bereich von untergeordneten Bezeichner für das die benachrichtigungsmeldung behandelt, durch Angeben der Anfangs- und Beenden der untergeordneten Bezeichner des Bereichs.  
  
 ON_NOTIFY_RANGE behandelt ClassWizard nicht; um es verwenden zu können, müssen Sie Ihre meldungszuordnung selbst bearbeiten.  
  
 Die Meldungszuordnungseintrags und Funktionsprototyp für ON_NOTIFY_RANGE lauten wie folgt:  
  
```  
 
ON_NOTIFY_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 wobei die kursiv Parameter durch ersetzt werden:  
  
 *wNotifyCode schalten*  
 Der Code für die Benachrichtigung, z. B. LVN_KEYDOWN behandelt werden.  
  
 *ID*  
 Der erste Bezeichner in zusammenhängenden Bereich von Bezeichnern.  
  
 *idLast*  
 Der letzte Bezeichner in zusammenhängenden Bereich von Bezeichnern.  
  
 *memberFxn*  
 Die Memberfunktion aufgerufen werden, wenn diese Benachrichtigung gesendet wird.  
  
 Member-Funktion muss mit dem folgenden Prototyp deklariert werden:  
  
```  
 
afx_msg void  
memberFxn  
(UINT   
id  ,
    NMHDR* 
pNotifyStruct  ,
    LRESULT* result);

 
```  
  
## <a name="remarks"></a>Hinweise  
 wobei kursiv Parameter sind:  
  
 *ID*  
 Der untergeordnete Bezeichner des Steuerelements, das die Benachrichtigung gesendet werden soll.  
  
 *pNotifyStruct*  
 Ein Zeiger auf die Benachrichtigungsstruktur wie oben beschrieben.  
  
 *Ergebnis*  
 Ein Zeiger auf den Ergebniscode müssen Sie festlegen, bevor Sie zurückkehren.  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX ON_NOTIFY_EX_RANGE  
 Wenn Sie mehr als ein Objekt in der Benachrichtigung, routing, um eine Nachricht verarbeiten möchten, können Sie ON_NOTIFY_EX (oder ON_NOTIFY_EX_RANGE) anstatt ON_NOTIFY (oder ON_NOTIFY_RANGE) verwenden. Der einzige Unterschied zwischen der **EX** und die regulären Version ist, dass für die Memberfunktion aufgerufen der **EX** Version gibt ein **BOOL** , der angibt, und zwar unabhängig davon, ob Verarbeitung von Nachrichten sollte fortgesetzt werden. Zurückgeben von **"false"** von dieser Funktion können Sie die gleiche Nachricht in mehr als ein Objekt zu verarbeiten.  
  
 ON_NOTIFY_EX oder ON_NOTIFY_EX_RANGE behandelt ClassWizard nicht; Wenn Sie diese verwenden möchten, müssen Sie die nachrichtenzuordnung selbst bearbeiten.  
  
 Die Meldungszuordnungseintrags und Funktionsprototyp für ON_NOTIFY_EX und ON_NOTIFY_EX_RANGE sind wie folgt. Die Bedeutung der Parameter ist genauso wie bei nicht -**EX** Versionen.  
  
```  
 
ON_NOTIFY_EX(
nCode  ,  
id  ,
    memberFxn) ON_NOTIFY_EX_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 Der Prototyp für beide oben genannten ist identisch:  
  
```  
 
afx_msg BOOL  
memberFxn  
(UINT   
id  ,
    NMHDR* 
pNotifyStruct  ,
    LRESULT* result);

 
```  
  
## <a name="remarks"></a>Hinweise  
 In beiden Fällen *Id* enthält die untergeordneten Bezeichner des Steuerelements, das die Benachrichtigung gesendet.  
  
 Die Funktion muss zurückgeben **"true"** , wenn die Nachricht vollständig verarbeitet wurde oder **"false"** Wenn auf andere Objekte in der Befehlsrouting Möglichkeit, die die Nachricht verarbeitet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

