---
title: Vorbereiten eines Testcomputers zum Ausführen einer ausführbaren Debugdatei
ms.date: 11/04/2016
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 6d7e9c2e0a29c2871fd86922151f2226dd9078fc
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448454"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Vorbereiten eines Testcomputers zum Ausführen einer ausführbaren Debugdatei

Um einen Computer zum Testen der Debugversion einer Anwendung vorzubereiten, die in Visual C++ erstellt wurde, müssen Sie Debugversionen der Visual C++-Bibliothek-DLLs bereitstellen, die für die Anwendung erforderlich sind. Führen Sie die Anweisungen unter [Understanding the Dependencies of a Visual C++ Application (Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung)](understanding-the-dependencies-of-a-visual-cpp-application.md) aus, um zu ermitteln, welche DLLs bereitgestellt werden müssen. Die Namen der Debugversionen der DLLs für Visual C++-Bibliotheken enden in der Regel auf "d". Beispielsweise hat die Debugversion der "msvcr100.dll" den Namen "msvcr100d.dll".

> [!NOTE]
>  Beachten Sie, dass weder die Debugversionen einer Anwendung noch die Debugversionen der DLLs (Dynamic Link Libraries) von Visual C++-Bibliothek verteilt werden dürfen. Sie dürfen Debugversionen von Anwendungen und Visual C++-DLLs nur auf den anderen Computern, nur für den Zweck, eine Anwendung zu debuggen und zu testen auf einem Computer ohne Visual Studio bereitstellen. Weitere Informationen finden Sie unter [Redistributing Visual C++ Files](redistributing-visual-cpp-files.md).

Es gibt drei Möglichkeiten, Debugversionen von DLLs für Visual C++-Bibliotheken zusammen mit der Debugversion einer Anwendung bereitzustellen.

- Verwenden Sie zum Installieren der Debugversion einer bestimmten Visual C++-DLL im %windir%\system32\-Verzeichnis eine zentrale Bereitstellung, indem Sie ein Setup-Projekt mit Mergemodulen für die richtige Bibliotheksversion und Architektur der Anwendung verwenden. Mergemodule befinden sich im Verzeichnis „Programme“ oder „Programme (x86)“ unter „\Gemeinsame Dateien\Mergemodule\\\“. Bei der Debugversion eines Mergemoduls ist „Debug“ Bestandteil des Namens, z. B. Microsoft_VC110_DebugCRT_x86.msm. Ein Beispiel dieser Bereitstellung finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setupprojekts](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

- Verwenden Sie eine lokale Bereitstellung, um die Debugversion einer bestimmten Visual C++-DLL im Installationsverzeichnis der Anwendung zu installieren, indem Sie die im Verzeichnis „Programme“ oder „Programme (x86)“ unter „\Microsoft Visual Studio \<Version>\VC\redist\Debug_NonRedist\\“ bereitgestellten Dateien verwenden.

    > [!NOTE]
    >  Für das Remotedebuggen Ihrer Anwendung mit Visual Studio 2005 oder Visual Studio 2008 auf einem anderen Computer erstellt haben, müssen Sie Debugversionen der Visual bereitstellen C++ Bibliotheks-DLLs als freigegebene Side-by-Side Assemblys. Sie können ein Setup-Projekt oder Windows Installer zum Installieren von entsprechenden Mergemodulen verwenden.

- Verwenden Sie in Visual Studio die Option **Bereitstellen** im Dialogfeld **Konfigurations-Manager**, um die Ausgabe des Projekts und andere Dateien zum Remotecomputer zu kopieren.

Nach der Installation von Visual C++-DLLs können Sie einen Remotedebugger auf dem Remotecomputer ausführen. Weitere Informationen zum Remotedebuggen finden Sie unter [Remote Debugging (Remotedebuggen)](/visualstudio/debugger/remote-debugging.md).

## <a name="see-also"></a>Siehe auch

[Bereitstellung in Visual C++](deployment-in-visual-cpp.md)<br>
[Windows Installer-Befehlszeilenoptionen](/windows/desktop/Msi/command-line-options)<br>
[Bereitstellungsbeispiele](deployment-examples.md)<br>
[Remote Debugging](/visualstudio/debugger/remote-debugging.md)
