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
ms.openlocfilehash: 9b873ca1b3384adab6487fb3af9dc1401aaad12c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225525"
---
# <a name="mapi-support-in-mfc"></a>MAPI-Unterstützung in MFC

MFC bietet Unterstützung für eine Teilmenge von der Microsoft Program Schnittstelle MAPI (Messaging Application) in Klasse `CDocument`. Insbesondere `CDocument` bietet Memberfunktionen, die bestimmen, ob e-Mail-Unterstützung auf die End-Computer des Benutzers vorhanden ist und, wenn dies der Fall ist, aktivieren Sie einen standard-Befehls-ID ID_FILE_SEND_MAIL ist Mail senden-Befehl. Die MFC-Handler-Funktion für diesen Befehl ermöglicht den Benutzer, ein Dokument per e-Mail zu senden.

> [!TIP]
>  Obwohl MFC nicht den gesamten Satz von MAPI-Funktion gekapselt ist, können Sie weiterhin MAPI-Funktionen aufrufen direkt, wie Win32-API-Funktionen direkt von MFC-Programmen aufgerufen werden können.

Bereitstellen von E-Mail zu senden ist Befehl in Ihrer Anwendung sehr einfach. MFC stellt die Implementierung zum Packen eines Dokuments (d. h. eine `CDocument`-abgeleitetes Objekt) als Anlage und als e-Mail senden. Diese Anlage entspricht einer Datei speichern-Befehl, der die speichert (serialisiert) die Inhalte des Dokuments auf die e-Mail-Nachricht. Diese Implementierung ruft den e-Mail-Client auf dem Computer des Benutzers, Benutzern die Möglichkeit, die e-Mail-Adresse und Betreff und den Nachrichtentext der e-Mail-Nachricht hinzu. Benutzer sehen die Benutzeroberfläche ihre vertrauten e-Mail-Anwendung. Diese Funktionalität wird bereitgestellt, um zwei `CDocument` Memberfunktionen: `OnFileSendMail` und `OnUpdateFileSendMail`.

MAPI muss zum Lesen der Datei, um die Anlage zu senden. Wenn die Anwendung öffnen, während der Datendatei behält eine `OnFileSendMail` Funktionsaufruf verwenden, muss die Datei mit einem Freigabemodus geöffnet werden, der mehrere Prozesse auf die Datei zugreifen können.

> [!NOTE]
>  Eine überschreibende Version der `OnFileSendMail` für Klasse `COleDocument` ordnungsgemäß behandelt zusammengesetzte Dokumente.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>Implementieren Sie einen Befehl Senden von E-Mails mit MFC

1. Verwenden des visuellen C++ Menü-Editor für ein Menüelement hinzufügen, dessen Befehls-ID ID_FILE_SEND_MAIL ist.

   Dieses Befehls-ID wird vom Framework in AFXRES bereitgestellt. H. Der Befehl kann keinem Menü hinzugefügt werden, aber es ist in der Regel hinzugefügt der **Datei** Menü.

1. Fügen Sie Folgendes manuell zur meldungszuordnung des Dokuments:

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Diese meldungszuordnung eignet sich für ein Dokument von einem abgeleiteten `CDocument` oder `COleDocument` – es der richtigen Basisklasse in beiden Fällen übernimmt, obwohl die meldungszuordnung in Ihrer Dokumentklasse abgeleiteten ist.

1. Erstellen Sie Ihre Anwendung.

Wenn e-Mail-Unterstützung verfügbar ist, werden die MFC ermöglicht des Menüelements mit `OnUpdateFileSendMail` und verarbeitet anschließend den Befehl mit `OnFileSendMail`. Wenn e-Mail-Unterstützung nicht verfügbar ist, entfernt der MFC automatisch das Menüelement, sodass dem Benutzer nicht angezeigt wird.

> [!TIP]
>  Anstatt manuell hinzuzufügen Meldungszuordnungseinträge wie zuvor beschrieben, können Sie das Eigenschaftenfenster für die Klasse, Nachrichten Funktionen zuzuordnen. Weitere Informationen finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

Weitere Informationen finden Sie unter den [MAPI](../mfc/mapi.md) Übersicht.

Weitere Informationen zu den `CDocument` Memberfunktionen, mit denen MAPI, finden Sie unter:

- [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Siehe auch

[MAPI](../mfc/mapi.md)
