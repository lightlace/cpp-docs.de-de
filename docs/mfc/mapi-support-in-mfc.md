---
title: MAPI-Unterstützung in MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 301e15b11b05f9ccbeaee63aead486f1cc6c405c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931901"
---
# <a name="mapi-support-in-mfc"></a>MAPI-Unterstützung in MFC
MFC bietet Unterstützung für eine Teilmenge von der Microsoft Programm Schnittstelle MAPI (Messaging Application) in Klasse `CDocument`. Insbesondere `CDocument` verfügt über Memberfunktionen, die bestimmen, ob e-Mail-Unterstützung auf dem Computer des Endbenutzers vorhanden ist und wenn dies der Fall ist, einen Befehl "Mail senden, deren standard Befehls-ID ID_FILE_SEND_MAIL ist, aktivieren". Die MFC-Handlerfunktion für diesen Befehl ermöglicht dem Benutzer ein Dokument per e-Mail senden.  
  
> [!TIP]
>  Obwohl MFC nicht den gesamten Satz der MAPI-Funktion kapseln, können Sie weiterhin MAPI-Funktionen aufrufen direkt, genau wie Win32 API-Funktionen direkt aus MFC-Programmen aufgerufen werden können.  
  
 Bereitstellen der Mail senden ist Befehl in der Anwendung sehr einfach. MFC stellt die Implementierung zum Packen von einem Dokument (d. h. eine `CDocument`-abgeleitetes Objekt) als Anlage und als e-Mail-Nachrichten zu senden. Diese Anlage ist gleichbedeutend mit einer Datei speichern-Befehl, der speichert (serialisiert) den Dokumentinhalt in der e-Mail-Nachricht. Diese Implementierung ruft die e-Mail-Client auf dem Computer des Benutzers, Benutzern die Möglichkeit, um die e-Mail-Adresse und Betreff und den Nachrichtentext der e-Mail-Nachricht hinzufügen. Benutzer finden Sie unter der Benutzeroberfläche ihre vertraut Mail-Anwendung aus. Diese Funktionalität wird durch zwei bereitgestellt `CDocument` Memberfunktionen: `OnFileSendMail` und `OnUpdateFileSendMail`.  
  
 MAPI muss zum Lesen der Datei, um die Anlage zu senden. Wenn die Anwendung beim Öffnen der Datendatei beibehält ein `OnFileSendMail` Funktionsaufruf, die Datei muss mit einem Share Modus geöffnet werden, die mehrere Prozesse auf die Datei zugreifen können.  
  
> [!NOTE]
>  Eine überschreibende Version der `OnFileSendMail` für Klasse `COleDocument` ordnungsgemäß Handles zusammengesetzte Dokumente.  
  
#### <a name="to-implement-a-send-mail-command-with-mfc"></a>So implementieren Sie einen E-Mail senden-Befehl mit MFC  
  
1.  Verwenden Sie im Menü-Editor von Visual C++, um ein Menüelement hinzufügen, dessen ID ID_FILE_SEND_MAIL lautet.  
  
     Dieses Befehls-ID wird vom Framework in AFXRES bereitgestellt. H. Der Befehl kann in keinem Menü hinzugefügt werden, aber es wird in der Regel hinzugefügt der **Datei** Menü.  
  
2.  Fügen Sie Folgendes manuell zu Ihrem Dokumentstruktur Nachricht:  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  Diese meldungszuordnung eignet sich für ein Dokument, das entweder abgeleitet `CDocument` oder `COleDocument` – er der richtigen Basisklasse in beiden Fällen übernimmt, obwohl die meldungszuordnung in Ihrer Dokumentklasse abgeleiteten ist.  
  
3.  Erstellen Sie die Anwendung.  
  
 Wenn e-Mail-Unterstützung verfügbar ist, können Sie MFC das Menüelement mit `OnUpdateFileSendMail` und verarbeitet anschließend den Befehl mit `OnFileSendMail`. Wenn e-Mail-Unterstützung nicht verfügbar ist, entfernt MFC automatisch das Menüelement klicken, damit der Benutzer nicht sichtbar ist.  
  
> [!TIP]
>  Anstatt manuellen Hinzufügen von Meldungszuordnungseinträgen wie oben beschrieben, können Sie das Eigenschaftenfenster Klasse Nachrichten Funktionen zuordnen. Weitere Informationen finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
 Weitere Informationen finden Sie unter der [MAPI](../mfc/mapi.md) (Übersicht).  
  
 Weitere Informationen zu den `CDocument` Memberfunktionen, mit denen MAPI, finden Sie unter:  
  
-   [CDocument:: OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)  
  
-   [CDocument:: OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)  
  
-   [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)  
  
## <a name="see-also"></a>Siehe auch  
 [MAPI](../mfc/mapi.md)

