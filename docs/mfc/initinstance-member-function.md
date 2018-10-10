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
ms.openlocfilehash: bc9d1d1ff35755a966591e6f46f7742ddfa59e08
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890022"
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
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie aufrufen [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) in Ihre `InitInstance` außer Kraft setzen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED) an.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
