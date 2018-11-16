---
title: Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
ms.openlocfilehash: 5d487e8a124d2edd7ce5a658d4965f1567756d5a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694152"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)

Visual C++ unterstützt ein Bereitstellungsmodell für Windows-Clientanwendungen, das auf der Idee von [isolierten Anwendungen](/windows/desktop/SbsCs/isolated-applications) und [parallelen Assemblys](/windows/desktop/SbsCs/about-side-by-side-assemblies-)basiert. Standardmäßig erstellt Visual C++ alle nativen C/C++-Anwendungen als isolierte Anwendungen, die [Manifeste](/windows/desktop/sbscs/manifests) verwenden, um ihre Abhängigkeiten von Visual C++-Bibliotheken zu beschreiben.

Das Erstellen von C/C++-Programmen als isolierte Anwendungen bietet eine Reihe von Vorteilen. Eine isolierte Anwendung ist beispielsweise nicht betroffen, wenn andere C/C++-Anwendungen Visual C++-Bibliotheken installieren oder deinstallieren. Visual C++-Bibliotheken, die von isolierten Anwendungen verwendet werden, können trotzdem entweder in den lokalen Ordner der Anwendung oder durch Installation in den nativen Assemblycache (WinSxS) neu verteilt werden. Dennoch kann die Wartung von Visual C++-Bibliotheken für bereits bereitgestellte Anwendungen durch die Verwendung einer [Herausgeberkonfigurationsdatei](/windows/desktop/SbsCs/publisher-configuration)vereinfacht werden. Mit dem isolierten Anwendungsbereitstellungsmodell können Sie einfacher sicherstellen, dass C/C++-Anwendungen, die auf einem bestimmten Computer ausgeführt werden, die neueste Version der Visual C++-Bibliotheken verwenden, aber gleichzeitig die Möglichkeit offenhalten, dass Systemadministratoren und Anwendungsentwickler die explizite Versionsbindung von Anwendungen an ihre abhängigen DLLs steuern können.

In diesem Abschnitt wird erläutert, wie Sie eine C/C++-Anwendung als isolierte Anwendung erstellen und sicherstellen können, dass sie über ein Manifest an Visual C++-Bibliotheken gebunden ist. Die Informationen in diesem Abschnitt gelten primäre für systemeigene, oder nicht verwaltete, Visual C++-Anwendungen. Informationen zur Bereitstellung mit Visual C++ erstellter nativer Anwendungen finden Sie unter [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Konzept der isolierten Anwendungen und der parallelen Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[Erstellen isolierter C/C++-Anwendungen](../build/building-c-cpp-isolated-applications.md)

[Erstellen von parallelen C/C++-Assemblys](../build/building-c-cpp-side-by-side-assemblies.md)

[Vorgehensweise: Erstellen von COM-Komponenten ohne Registrierung](../build/how-to-build-registration-free-com-components.md)

[Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)

[Manifestgenerierung für C/C++-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)

[Problembehandlung bei isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>Verwandte Abschnitte

[Isolierte Anwendungen und parallele Assemblys](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)