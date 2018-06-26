---
title: InitInstance-Memberfunktion | Microsoft Docs
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
ms.openlocfilehash: a9379fef6a1d676d6a3bc757ee51d5d27acd5f6f
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930175"
---
# <a name="initinstance-member-function"></a>InitInstance-Memberfunktion
Das Windows-Betriebssystem können Sie mehrere Kopien oder "Instanz" der gleichen Anwendung ausgeführt werden. `WinMain` Aufrufe [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) jedes Mal, wenn eine neue Instanz der Anwendung startet.  
  
 Der Standard `InitInstance` Implementierung vom MFC-Anwendungs-Assistenten erstellt wurde, führt die folgenden Aufgaben:  
  
-   Erstellt die zentrale Aktion die Dokumentvorlagen, die wiederum Dokumente, Ansichten und Rahmenfenster erstellen. Eine Beschreibung dieses Vorgangs finden Sie in [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md).  
  
-   Lädt standard Dateioptionen aus einer INI-Datei oder der Windows-Registrierung, einschließlich der Namen der zuletzt verwendeten Dateien.  
  
-   Registriert eine oder mehrere Dokumentvorlagen.  
  
-   Eine MDI-Anwendung wird erstellt in einem Hauptrahmenfenster.  
  
-   Verarbeitet die Befehlszeile zum Öffnen eines Dokuments in der Befehlszeile angegeben oder auf ein neues, leeres Dokument zu öffnen.  
  
 Sie können eigene Initialisierungscode hinzufügen oder ändern Sie den Code, der vom Assistenten geschrieben.  
  
> [!NOTE]
>  MFC-Anwendungen müssen als Singlethread-Apartment (STA) initialisiert werden. Beim Aufrufen [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in Ihrer `InitInstance` außer Kraft setzen, geben Sie COINIT_APARTMENTTHREADED (anstelle von COINIT_MULTITHREADED). Weitere Informationen finden Sie unter PRB: MFC-Anwendung nicht mehr reagiert, wenn Sie die Anwendung als eine Multithread-Apartment (828643) am initialisieren [ http://support.microsoft.com/default.aspxscid=kb; En-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
