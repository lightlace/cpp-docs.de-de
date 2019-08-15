---
title: InitInstance-Memberfunktion
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: c1f83f794cc40fa7f4d290fa4a147fe9f7e074be
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508371"
---
# <a name="initinstance-member-function"></a>InitInstance-Memberfunktion

Mit dem Windows-Betriebssystem können Sie mehr als eine Kopie oder eine "Instanz" derselben Anwendung ausführen. `WinMain`Ruft [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) bei jedem Start einer neuen Instanz der Anwendung auf.

Die vom `InitInstance` MFC-Anwendungs-Assistenten erstellte Standard Implementierung führt die folgenden Aufgaben aus:

- Als zentrale Aktion erstellt die Dokumentvorlagen, die wiederum Dokumente, Ansichten und Rahmen Fenster erstellen. Eine Beschreibung dieses Prozesses finden Sie unter [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md).

- Lädt Standarddatei Optionen aus einer INI-Datei oder der Windows-Registrierung, einschließlich der Namen der zuletzt verwendeten Dateien.

- Registriert eine oder mehrere Dokumentvorlagen.

- Erstellt bei einer MDI-Anwendung ein Hauptrahmen Fenster.

- Verarbeitet die Befehlszeile, um ein Dokument zu öffnen, das in der Befehlszeile angegeben ist, oder um ein neues, leeres Dokument zu öffnen.

Sie können Ihren eigenen Initialisierungs Code hinzufügen oder den vom Assistenten geschriebenen Code ändern.

> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Wenn Sie [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) in der `InitInstance` außer Kraft Setzung aufrufen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED) an.

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
