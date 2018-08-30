---
title: Erstellen von C/C++-Anwendungen und Seite-an-Seite-Assemblys isoliert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8d806af709d6d6e2a5754bc80a34a473900177f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212911"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)
Visual C++ unterstützt ein Bereitstellungsmodell für Windows-Clientanwendungen, die basierend auf der Idee von [isoliert Anwendungen](/windows/desktop/SbsCs/isolated-applications) und [Side-by-Side Assemblys](/windows/desktop/SbsCs/about-side-by-side-assemblies-). Standardmäßig erstellt Visual C++ alle nativen C/C++-Anwendungen als isolierte Anwendungen, mit denen [Manifeste](https://msdn.microsoft.com/library/aa375365) um ihre Abhängigkeiten von Visual C++-Bibliotheken zu beschreiben.  
  
 Das Erstellen von C/C++-Programmen als isolierte Anwendungen bietet eine Reihe von Vorteilen. Eine isolierte Anwendung ist beispielsweise nicht betroffen, wenn andere C/C++-Anwendungen Visual C++-Bibliotheken installieren oder deinstallieren. Visual C++-Bibliotheken, die von isolierten Anwendungen verwendet möglicherweise immer noch im lokalen Ordner der Anwendung oder durch Installation in den nativen Assemblycache (WinSxS); verteilt werden Allerdings Wartung von Visual C++-Bibliotheken für bereits bereitgestellte Anwendungen vereinfacht werden können, mit einem [Herausgeberkonfigurationsdatei](/windows/desktop/SbsCs/publisher-configuration). Mit dem isolierten Anwendungsbereitstellungsmodell können Sie einfacher sicherstellen, dass C/C++-Anwendungen, die auf einem bestimmten Computer ausgeführt werden, die neueste Version der Visual C++-Bibliotheken verwenden, aber gleichzeitig die Möglichkeit offenhalten, dass Systemadministratoren und Anwendungsentwickler die explizite Versionsbindung von Anwendungen an ihre abhängigen DLLs steuern können.  
  
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
 [Isolierte Anwendungen und Seite-an-Seite-Assemblys](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)  
  
 [Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)