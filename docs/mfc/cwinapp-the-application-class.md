---
title: 'CWinApp: Die Anwendungsklasse'
ms.date: 11/04/2016
f1_keywords:
- CWinApp
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
ms.openlocfilehash: a19d510dc4c8835497ff9e1bb7d5ca6242206fe9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551319"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Die Anwendungsklasse

Die Hauptanwendungsklasse in MFC kapselt die Initialisierung, Ausführung und Beendigung einer Anwendung für das Windows-Betriebssystem. Eine Anwendung, die auf das Framework muss eine und nur ein Objekt einer Klasse abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md). Dieses Objekt wird erstellt, bevor Windows erstellt werden.

`CWinApp` stammt aus `CWinThread`, steht für den Hauptthread Ihrer Anwendung, die möglicherweise von einem oder mehreren Threads ausgeführt. In früheren Versionen von MFC die `InitInstance`, **ausführen**, `ExitInstance`, und `OnIdle` Memberfunktionen sind tatsächlich in Klasse `CWinThread`. Diese Funktionen werden hier erläutert, als wären sie `CWinApp` Member stattdessen, da es sich bei die Diskussion bezieht sich auf die Rolle des Objekts, als Application-Objekt und nicht als primären Thread.

> [!NOTE]
>  Ihrer Anwendungsklasse bildet Ihrer Anwendung primären Thread der Ausführung. Win32-API-Funktionen verwenden, können Sie auch den sekundären Ausführungsthreads erstellen. Diese Threads können die MFC-Bibliothek verwenden. Weitere Informationen finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Wie jedes andere Programm für das Windows-Betriebssystem, die Framework-Anwendung verfügt über eine `WinMain` Funktion. In einer Framework-Anwendung jedoch, Sie nicht schreiben `WinMain`. Es wird von der Klassenbibliothek bereitgestellt und wird aufgerufen, wenn die Anwendung wird gestartet. `WinMain` führt die Standarddienste, wie z. B. das Registrieren von Fensterklassen. Es ruft Sie Memberfunktionen des Anwendungsobjekts zu initialisieren und Ausführen der Anwendung. (Sie können anpassen, `WinMain` durch Überschreiben der `CWinApp` Memberfunktionen, die `WinMain` aufrufen.)

Zum Initialisieren der Anwendung `WinMain` Aufrufe des Anwendungsobjekts `InitApplication` und `InitInstance` Memberfunktionen. Zum Ausführen der Anwendung Meldungsschleife `WinMain` Aufrufe der **ausführen** Member-Funktion. Beim Beenden `WinMain` ruft des Anwendungsobjekts `ExitInstance` Member-Funktion.

> [!NOTE]
>  Im angezeigten Namen **fett** in dieser Dokumentation zeigen Sie Elemente, die von der Microsoft Foundation Class-Bibliothek und die Visual C++ bereitgestellt. Im angezeigten Namen `monospaced` Typ angeben, Elemente, die Sie erstellen oder überschreiben.

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CWinApp und der MFC-Anwendungs-Assistent](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[Überschreibbare CWinApp-Memberfunktionen](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Spezielle CWinApp-Dienste](../mfc/special-cwinapp-services.md)

