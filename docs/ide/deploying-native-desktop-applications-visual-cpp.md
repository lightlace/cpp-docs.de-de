---
title: Bereitstellen von systemeigenen Desktopanwendungen (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f4aa355c132b4c94f085cbdf7aa73785357d0f0
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Bereitstellen von systemeigenen Desktopanwendungen (Visual C++)

Die Verteilung einer fertigen Anwendung oder Komponente zur Installation auf anderen Computern wird als Bereitstellung bezeichnet. Die Bereitstellungsplanung beginnt, wenn eine Anwendung auf dem Computer eines Entwicklers erstellt wird. Die Bereitstellung endet, wenn die Anwendung installiert wurde und auf dem Computer eines Benutzers ausgeführt werden kann.

Visual Studio bietet verschiedene Technologien für die Bereitstellung von Windows-Anwendungen. Dazu gehören die ClickOnce-Bereitstellung und Windows Installer-Bereitstellung.

- ClickOnce kann verwendet werden, um C++-Anwendungen bereitgestellt, die die common Language Runtime (CLR) ausgerichtet – gemischte, reine und überprüfbare Assemblys. Obwohl Sie mit Windows Installer eine verwaltete Anwendung bereitstellen können, wird empfohlen, dass Sie ClickOnce verwenden, da es .NET Framework-Sicherheitsfeatures wie das manifest Signieren von Manifesten. ClickOnce unterstützt keine Bereitstellung von systemeigenen C++-Anwendungen. Weitere Informationen finden Sie unter [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md).

- Mithilfe der Windows Installer-Technologie können systemeigene C++-Anwendungen oder C++-Anwendungen bereitgestellt werden, die auf die Common Language Runtime (CLR) ausgerichtet sind.

In den Artikeln dieses Abschnitts der Dokumentation wird erläutert, wie sichergestellt werden kann, dass eine systemeigene Visual C++-Anwendung auf jedem Computer ausgeführt werden kann, der eine unterstützte Zielplattform bietet. Zudem werden die in ein Installationspaket einzubeziehenden Dateien und die empfohlenen Methoden zum Verteilen von Komponenten beschrieben, von denen die Anwendung abhängt.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Bereitstellung in Visual C++](../ide/deployment-in-visual-cpp.md)

- [Bereitstellungskonzepte](../ide/deployment-concepts.md)

- [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)

- [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md)

- [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md)

- [Universal CRT-Bereitstellung](universal-crt-deployment.md).

- [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)

- [Bereitstellungsbeispiele](../ide/deployment-examples.md)

- [Neuverteilen von Webclientanwendungen](../ide/redistributing-web-client-applications.md)

- [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)

- [C++/CLR-Anwendung auf einer früheren Version der Common Language Runtime ausgeführt wird.](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>Verwandte Abschnitte

- [Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [Bereitstellung](/dotnet/framework/deployment/index)

- [Problembehandlung bei isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)