---
title: Bereitstellung in Visual C++ | Microsoft Docs
ms.custom: 
ms.date: 9/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8ae663d5371626162cf3b98c1048128a61b1e1a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="deployment-in-visual-c"></a>Bereitstellung in Visual C++

Installation der Anwendung auf einem anderen Computer als Ihrem Entwicklungscomputer genannt *Bereitstellung*. Wenn Sie eine Visual C++-Anwendung auf einen anderen Computer bereitstellen, müssen Sie installieren die Anwendung und alle Bibliotheksdateien, von denen er abhängt. Visual Studio ermöglicht es drei Möglichkeiten zum Bereistellen der Visual C++-Bibliotheken zusammen mit der Anwendung: *zentrale Bereitstellung*, *lokale Bereitstellung*, und *statische Verknüpfung*. Zentrale Bereitstellung setzt die Bibliotheksdateien unter dem Windows-Verzeichnis, in dem der Windows Update-Dienst diese automatisch aktualisieren kann. Lokale Bereitstellung werden Bibliotheksdateien im selben Verzeichnis wie die Anwendung. Alle lokal bereitgestellten Bibliotheken muss erneut selbst aktualisieren. Statisches verknüpfen bindet des Bibliothekscodes in Ihrer Anwendung. Sie müssen die Neukompilierung und erneute Bereitstellung die Anwendung nutzen alle Updates an den Bibliotheken, wenn Sie statische Verknüpfung verwenden.

## <a name="central-deployment"></a>Zentrale Bereitstellung

Bei der zentralen Bereitstellung werden Library-DLL-Dateien im Verzeichnis "Windows\System32" oder für 32-Bit-Bibliotheksdateien auf X64 installiert, das Windows\SysWow64-Verzeichnis des Systems. Microsoft aktualisiert die zentral bereitgestellten Bibliotheken automatisch. Für Visual C++-Bibliotheken, die lokal bereitgestellt oder statisch verknüpft sind, müssen Sie die Updates bereitstellen.

Um Visual C++-Bibliotheken zentral bereitstellen zu können, können Sie einer der folgenden beiden Quellen für die Dateien verwenden, um zu installieren:

- *Verteilbare Paket* Dateien, die eigenständige ausführbare Befehlszeilendateien, die alle Visual C++ redistributable-Bibliotheken in komprimierter Form enthalten sind, oder

- *Weiter verteilbare Mergemodule* (MSM-Dateien), mit denen Sie bestimmte Bibliotheken bereitstellen können, und die Sie in der Datei der Anwendung Windows Installer (MSI) einschließen.

Eine weiter verteilbare Paketdatei installiert alle von der Visual C++-Bibliotheken für eine bestimmte Systemarchitektur. Z. B. Wenn Ihre Anwendung für X64 erstellt wird, können das verteilbare Paket von vcredist_x64.exe Sie die Visual C++-Bibliotheken zu installieren, die Ihre Anwendung verwendet. Sie können das Installationsprogramm der Anwendung als Voraussetzung für das verteilbare Paket auszuführen, bevor Sie Ihre Anwendung installieren programmieren.

Ein Mergemodul aktiviert die Einbeziehung von setuplogik für eine bestimmte Visual C++-Bibliothek in einer anwendungssetupdatei von Windows Installer. Sie können beliebig viele oder so wenig Mergemodule einschließen, die Anwendung erforderlich sind. Verwenden Sie Mergemodule, wenn Sie die Größe der Binärdateien für Ihre Bereitstellung zu minimieren müssen.

Da zentrale Bereitstellung mithilfe von verteilbares Paket oder Mergemodule Windows Update, um die Visual C++-Bibliotheken automatisch zu aktualisieren kann, wird empfohlen, dass die Bibliothek-DLLs in Ihrer Anwendung anstelle von statischen Bibliotheken, und nutzen Sie zentrale Bereitstellung anstelle der lokalen Bereitstellung.

## <a name="local-deployment"></a>Lokale Bereitstellung

Bei der lokalen Bereitstellung werden Bibliotheksdateien im Anwendungsordner zusammen mit der ausführbaren Datei installiert. Verschiedene Versionen von Visual C++ redistributable-Bibliotheken können im selben Ordner installiert werden, da der Dateiname jeder Version die Versionsnummer enthält. Beispielsweise ist die Version 12 der C++-Laufzeitbibliothek msvcp120.dll und Version 14 msvcp140.dll ist.

Da Microsoft automatisch kann nicht lokal Update bereitgestellt Visual C++-Bibliotheken, wir empfehlen nicht die lokale Bereitstellung dieser Bibliotheken. Wenn Sie sich für die lokale Bereitstellung von weiter verteilbaren Bibliotheken entscheiden, wird empfohlen, dass Sie eine eigene Methode zur automatischen Aktualisierung von lokal bereitgestellten Bibliotheken implementieren.

## <a name="static-linking"></a>Statische Verknüpfung

Zusätzlich zu den dynamisch verknüpften Bibliotheken stellt Visual Studio die meisten Bibliotheken als statische Bibliotheken bereit. Sie können statisch verknüpfen eine statische Bibliothek für Ihre Anwendung, d. h., verknüpfen den Objektcode für die Bibliothek direkt in der Anwendung. Dies erstellt eine Binärdatei, ohne eine Abhängigkeit, die DLL, damit Sie nicht die Visual C++-Bibliotheksdateien separat bereitstellen. Jedoch empfohlen nicht diese Vorgehensweise, da statisch verknüpfte Bibliotheken nicht an Ort aktualisiert werden können. Wenn Sie statische Verknüpfung verwenden und eine verknüpfte Bibliothek aktualisieren möchten, müssen Sie die Anwendung erneut kompilieren und erneut bereitstellen.

## <a name="troubleshooting-deployment-issues"></a>Problembehandlung bei Bereitstellungsproblemen

Die Ladereihenfolge von Visual C++-Bibliotheken ist systemabhängig. Verwenden Sie "depends.exe" oder "where.exe", um Ladeprogrammprobleme zu diagnostizieren. Weitere Informationen finden Sie unter [Dynamic Link Library-Suchreihenfolge (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).

## <a name="see-also"></a>Siehe auch

[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)