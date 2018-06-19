---
title: 'CWinApp: Die Anwendungsklasse | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0c3641441554d73e0c7657dd220be86f0c0cab0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343004"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Die Anwendungsklasse
Die Hauptassembly der Anwendung-Klasse in MFC kapselt die Initialisierung, Ausführung und Beendigung einer Anwendung für Windows-Betriebssystems. Eine Anwendung, die auf das Framework benötigen eine und nur ein Objekt einer Klasse abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md). Dieses Objekt wird erstellt, bevor Windows erstellt werden.  
  
 `CWinApp` stammt aus `CWinThread`, der den Hauptthread der Ausführung Ihrer Anwendung, die möglicherweise einen oder mehrere Threads darstellt. In den neuesten Versionen der MFC die `InitInstance`, **ausführen**, `ExitInstance`, und `OnIdle` Memberfunktionen befinden sich nämlich in Klasse `CWinThread`. Diese Funktionen werden hier erläutert, als wären sie `CWinApp` Mitglieder stattdessen, da die Diskussion des Objekts Rolle als Application-Objekt und nicht als primären Thread bezieht.  
  
> [!NOTE]
>  Die Anwendungsklasse bildet die Anwendung primären Thread der Ausführung. Mithilfe von Win32-API-Funktionen können Sie auch sekundäre Ausführungsthreads erstellen. Diese Threads können die MFC-Bibliothek. Weitere Informationen finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Genau wie jedes Programm für Windows-Betriebssystems, die Framework-Anwendung verfügt eine `WinMain` Funktion. In einer Framework-Anwendung jedoch nicht schreiben Sie `WinMain`. Es wird von der Klassenbibliothek bereitgestellt und wird aufgerufen, wenn die Anwendung wird gestartet. `WinMain` führt die Standarddienste z. B. das Registrieren von Fensterklassen. Er ruft Sie Memberfunktionen des Anwendungsobjekts zu initialisieren, und führen Sie die Anwendung. (Sie können anpassen, `WinMain` durch Überschreiben der `CWinApp` Memberfunktionen, die `WinMain` aufrufen.)  
  
 Zum Initialisieren der Anwendung `WinMain` ruft des Anwendungsobjekts `InitApplication` und `InitInstance` Memberfunktionen. Zum Ausführen der Nachrichtenschleife für die Anwendung, `WinMain` Aufrufe der **ausführen** Memberfunktion. Beim Beenden `WinMain` ruft des Anwendungsobjekts `ExitInstance` Memberfunktion.  
  
> [!NOTE]
>  Im angezeigten Namen **fett** zeigen Sie in dieser Dokumentation Elemente, die von der Microsoft Foundation Class-Bibliothek und Visual C++ bereitgestellt. Im angezeigten Namen `monospaced` Typ anzugeben, Elemente, die Sie erstellen oder außer Kraft setzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [CWinApp und der MFC-Anwendungs-Assistent](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [Überschreibbare CWinApp-Memberfunktionen](../mfc/overridable-cwinapp-member-functions.md)   
 [Spezielle CWinApp-Dienste](../mfc/special-cwinapp-services.md)

