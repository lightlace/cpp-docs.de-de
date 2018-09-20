---
title: InitInstance-Memberfunktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- InitInstance
dev_langs:
- C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1dce40fd91f1b4345739f3dc38e13d2ee8d0997
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426379"
---
# <a name="initinstance-member-function"></a>InitInstance-Memberfunktion

Das Windows-Betriebssystem können Sie mehr als eine Kopie oder "Instanz" der gleichen Anwendung ausgeführt werden. `WinMain` Aufrufe [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) jedes Mal, wenn eine neue Instanz der Anwendung startet.

Der Standard `InitInstance` Implementierung vom MFC-Anwendungs-Assistenten erstellt wurde, führt die folgenden Aufgaben:

- Die zentrale Aktion erstellt die Dokumentvorlagen, die wiederum Dokumente, Ansichten und Rahmenfenster erstellen. Eine Beschreibung dieses Prozesses finden Sie unter [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md).

- Optionen für die standard-Datei aus einer INI-Datei oder der Windows-Registrierung, einschließlich der Namen der zuletzt verwendeten Dateien geladen.

- Registriert eine oder mehrere Dokumentvorlagen.

- Für eine MDI-Anwendung erstellt ein Hauptrahmenfenster.

- Verarbeitet die Befehlszeile zum Öffnen eines Dokuments in der Befehlszeile angegeben und ein neues, leeres Dokument öffnen.

Sie können Ihren eigenen Initialisierungscode hinzufügen oder ändern Sie den Code, der vom Assistenten geschrieben.

> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie aufrufen [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) in Ihre `InitInstance` außer Kraft setzen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED) an. Weitere Informationen finden Sie unter PRB: MFC-Anwendung nicht mehr reagiert, wenn Sie die Anwendung als eine Multithread-Apartment (828643) am initialisieren [ http://support.microsoft.com/default.aspxscid=kb; En-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
