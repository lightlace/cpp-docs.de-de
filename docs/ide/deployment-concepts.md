---
title: Bereitstellungskonzepte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0960e94acdbe660474efbeeddd0f72fa4f0606f6
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34257061"
---
# <a name="deployment-concepts"></a>Bereitstellungskonzepte

In diesem Abschnitt werden die Hauptaspekte der Bereitstellung von C++-Anwendungen erläutert.

## <a name="windows-installer-deployment-in-c"></a>Windows Installer-Bereitstellung in C++

Visual C++-Projekte verwenden in der Regel das herkömmliche Windows Installer-Setup für die Bereitstellung. Packen Sie Ihre Anwendung in eine „setup.exe“-Datei zum Vorbereiten einer Windows Installer-Bereitstellung, und verteilen Sie diese Datei zusammen mit einem Installer-Paket (MSI). Benutzer führen dann die Datei „setup.exe“ aus, um Ihre Anwendung zu installieren.

Sie packen Ihre Anwendung, indem Sie Ihrer Projektmappe ein Setup-Projekt hinzufügen. Wenn es erstellt ist, erstellt es die Setup- und Installer-Paketdateien, die Sie an Benutzer verteilen. Weitere Informationen finden Sie unter [Choosing a Deployment Method (Auswählen einer Bereitstellungsmethode)](../ide/choosing-a-deployment-method.md).

## <a name="library-dependencies"></a>Bibliothekabhängigkeiten

Wenn eine C- oder C++-Anwendung mithilfe von Funktionen von Visual C++-Bibliotheken erstellt wird, wird sie abhängig von der Anwesenheit dieser Bibliotheken zur Laufzeit. Damit die Anwendung ausgeführt werden kann, muss sie entweder statisch oder dynamisch mit den erforderlichen Visual C++-Bibliotheken verknüpft sein. Wenn eine Anwendung dynamisch mit einer Visual C++-Bibliothek verknüpft ist, muss die Bibliothek bei der Ausführung anwesend sein, damit sie geladen werden kann. Wenn die Anwendung hingegen statisch mit einer Visual C++-Bibliothek verknüpft ist, müssen die entsprechenden DLLs nicht auf dem Computer des Benutzers vorhanden sein. Die statische Verknüpfung hat jedoch auch Nachteile, z.B. die größeren Anwendungsdateien und die potenzielle Erschwerung der Wartung. Weitere Informationen finden Sie unter [Advantages of using DLLs (Vorteile der Verwendung von DLLs)](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).

## <a name="packaging-and-redistributing"></a>Packen und Verteilen

Visual C++-Bibliotheken werden als DLLs gepackt, und alle erforderlichen C- und C++-Anwendungen werden auf dem Computer des Entwicklers von Visual Studio installiert. Wenn Sie Ihre Anwendung jedoch für Benutzer bereitstellen, ist es in den meisten Fällen nicht möglich, eine Installation von Visual Studio zum Ausführen der Anwendung vorauszusetzen. Es ist wichtig, nur die Teile von Visual C++ zu verteilen, die zum Ausführen der Anwendung erforderlich sind.

Weitere Informationen zum Packen und Verteilen finden Sie in den folgenden Artikeln:

- [Determining Which DLLs to Redistribute (Ermitteln der neu zu verteilenden DLLs)](../ide/determining-which-dlls-to-redistribute.md)

- [Choosing a Deployment Method (Auswählen einer Bereitstellungsmethode)](../ide/choosing-a-deployment-method.md)

- [Universal CRT deployment (Universelle CRT-Bereitstellung)](universal-crt-deployment.md)

Beispiele für die Bereitstellung und Vorschläge zur Problembehandlung finden Sie unter:

- [Deployment Examples (Bereitstellungsbeispiele)](../ide/deployment-examples.md)

- [Troubleshooting C/C++ Isolated Applications and Side-by-side Assemblies (Problembehandlung bei isolierten Anwendungen und parallelen Assemblys (C/C++))](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="see-also"></a>Siehe auch

- [Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)
- [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)
- [Windows Installer-Bereitstellung](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)
