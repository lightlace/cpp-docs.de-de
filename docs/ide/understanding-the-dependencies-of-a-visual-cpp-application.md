---
title: Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
ms.openlocfilehash: ed510e0d289349b1d7a0129a1c586b0bf1715b7e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751478"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung

Sie können die Projekteigenschaften anzeigen, um zu ermitteln, von welchen Visual C++-Bibliotheken eine Anwendung abhängt. (Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Eigenschaften**, um das Dialogfeld **Eigenschaftenseiten** zu öffnen.) Sie können auch den Dependency Walker (depends.exe) verwenden, der ein umfassenderes Bild der Abhängigkeiten verschafft.

Im Dialogfeld **Eigenschaftenseiten** können Sie verschiedene Seiten unter **Konfigurationseigenschaften** überprüfen, um die Abhängigkeiten zu verstehen. Wenn im Projekt beispielsweise die MFC-Bibliotheken verwendet werden und Sie **Verwendung von MFC** und **MFC in einer gemeinsam genutzten DLL verwenden** in den **Konfigurationseigenschaften** auf der Seite **Allgemein** wählen, ist Ihre Anwendung zur Laufzeit von MFC-DLLs abhängig, z.B. „mfc\<version>.dll“. Wenn die Anwendung MFC nicht verwendet, kann sie dennoch von der CRT-Bibliothek abhängig sein, wenn Sie einen **Laufzeitbibliothek**-Wert von **Multithreaded-Debug-DLL (/MDd)** oder **Multithreaded-DLL (/MD)** unter **Konfigurationseigenschaften** > **C/C++** > **Codegenerierung** auswählen.

Sie können umfassender bestimmen, von welchen DLLs eine Anwendung abhängt, indem Sie die Anwendung mit Dependency Walker (depends.exe) öffnen. Sie können das Tool von der [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640)-Website herunterladen.

Wenn Sie „depends.exe“ verwenden, können Sie eine Liste mit DLLs überprüfen, die zur Ladezeit mit der Anwendung verknüpft sind, sowie eine Liste mit den verzögert geladenen DLLs. Wenn Sie eine vollständige Liste mit DLLs erhalten möchten, die zur Laufzeit dynamisch geladen werden, können Sie die Profilerstellungsfunktion in „depends.exe“ verwenden. Hiermit können Sie die Anwendung testen, bis Sie sicher sind, dass alle Codepfade ausgeführt wurden. Nach Abschluss der Profilerstellungssitzung zeigt „depends.exe“ an, welche DLLs zur Laufzeit dynamisch geladen wurden.

Bedenken Sie bei Verwendung von depends.exe, dass eine DLL von einer anderen DLL oder einer bestimmten Version einer DLL abhängig sein kann. Sie können depends.exe sowohl auf dem Entwicklungscomputer als auch auf einem Zielcomputer verwenden. Auf dem Entwicklungscomputer gibt depends.exe die DLLs zurück, die zur Unterstützung einer Anwendung erforderlich sind. Wenn Sie Schwierigkeiten dabei haben, eine Anwendung auf einem Zielcomputer auszuführen, können Sie depends.exe dorthin kopieren und die Anwendung dann im Tool öffnen, sodass Sie bestimmen können, ob irgendwelche DLLs fehlen oder falsch sind.

Wenn Sie wissen, von welchen DLLs die Anwendung abhängt, können Sie bestimmen, welche davon Sie bei einer Bereitstellung auf einem anderen Computer gemeinsam mit der Anwendung verteilen müssen. System-DLLs müssen in den meisten Fällen nicht verteilt werden, eventuell aber DLLs für Visual C++-Bibliotheken. Weitere Informationen finden Sie unter [Determining Which DLLs to Redistribute (Ermitteln der zu verteilenden DLLs)](../ide/determining-which-dlls-to-redistribute.md).

## <a name="see-also"></a>Siehe auch

[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)
