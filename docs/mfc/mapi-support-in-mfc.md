---
title: MAPI-Unterstützung in MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: e46eaf2bd84d4cebd2215ab2752ce3bb8e1eb9b3
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907678"
---
# <a name="mapi-support-in-mfc"></a>MAPI-Unterstützung in MFC

MFC bietet Unterstützung für eine Teilmenge der Microsoft Messaging Application Program Interface (MAPI) in der `CDocument`-Klasse. `CDocument` Insbesondere verfügt über Member-Funktionen, die bestimmen, ob die e-Mail-Unterstützung auf dem Computer des Endbenutzers vorhanden ist. wenn dies der Fall ist, aktivieren Sie einen Send Mail-Befehl, dessen Standard Befehls-ID ID_FILE_SEND_MAIL Die MFC-Handlerfunktion für diesen Befehl ermöglicht dem Benutzer das Senden eines Dokuments per elektronischer e-Mail.

> [!TIP]
>  Obwohl MFC den gesamten MAPI-Funktions Satz nicht kapist, können Sie MAPI-Funktionen weiterhin direkt aufzurufen, genauso wie Sie Win32-API-Funktionen direkt aus MFC-Programmen abrufen können.

Das Bereitstellen des Befehls "Mail senden" in der Anwendung ist sehr einfach. MFC stellt die-Implementierung bereit, um ein Dokument (d. `CDocument`h. ein von abgeleitetes Objekt) als Anlage zu verpacken und als e-Mail zu senden. Diese Anlage entspricht einem File Save-Befehl, der den Inhalt des Dokuments in der e-Mail-Nachricht speichert (serialisiert). Diese Implementierung ruft den e-Mail-Client auf dem Computer des Benutzers auf, um dem Benutzer die Möglichkeit zu geben, die e-Mail zu adressieren und der e-Mail-Nachricht Betreff und Nachrichtentext hinzuzufügen. Benutzern wird die Benutzeroberfläche der vertrauten Mail Anwendung angezeigt. Diese Funktion wird von zwei `CDocument` Element Funktionen bereitgestellt: `OnUpdateFileSendMail` `OnFileSendMail` und.

MAPI muss die Datei lesen, um die Anlage zu senden. Wenn die Anwendung die Datendatei während eines `OnFileSendMail` Funktions Aufrufes geöffnet hält, muss die Datei mit einem Freigabe Modus geöffnet werden, der mehreren Prozessen den Zugriff auf die Datei ermöglicht.

> [!NOTE]
>  Eine über schreibende `OnFileSendMail` Version von `COleDocument` für die-Klasse verarbeitet Verbund Dokumente ordnungsgemäß.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>So implementieren Sie einen Befehl "Mail senden" mit MFC

1. Verwenden Sie den C++ Editor für den visuellen Menübefehl, um ein Menü Element mit der Befehls-ID ID_FILE_SEND_MAIL hinzuzufügen.

   Diese Befehls-ID wird vom Framework in AFXRES bereitgestellt. Micha. Der Befehl kann einem beliebigen Menü hinzugefügt werden, wird aber normalerweise dem Menü **Datei** hinzugefügt.

1. Fügen Sie der Meldungs Zuordnung Ihres Dokuments manuell Folgendes hinzu:

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Diese Nachrichten Zuordnung funktioniert für ein Dokument, das entweder `CDocument` von `COleDocument` oder abgeleitet ist – die richtige Basisklasse wird in beiden Fällen übernommen, auch wenn sich die Meldungs Zuordnung in der abgeleiteten Dokument Klasse befindet.

1. Erstellen Sie Ihre Anwendung.

Wenn e-Mail-Unterstützung verfügbar ist, aktiviert MFC `OnUpdateFileSendMail` das Menü Element mit und verarbeitet `OnFileSendMail`anschließend den Befehl mit. Wenn die e-Mail-Unterstützung nicht verfügbar ist, wird das Menü Element von MFC automatisch entfernt, sodass es dem Benutzer nicht angezeigt wird.

> [!TIP]
>  Anstatt Nachrichten Zuordnungs Einträge wie zuvor beschrieben manuell hinzuzufügen, können Sie den Klassen [Klassen-Assistenten](reference/mfc-class-wizard.md) verwenden, um Nachrichten zu Funktionen zuzuordnen. Weitere Informationen finden Sie unter [Mapping von Nachrichten zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

Weitere Informationen finden Sie in der Übersicht über [MAPI](../mfc/mapi.md) .

Weitere Informationen zu den `CDocument` Member-Funktionen, die MAPI aktivieren, finden Sie unter:

- [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Siehe auch

[MAPI](../mfc/mapi.md)
