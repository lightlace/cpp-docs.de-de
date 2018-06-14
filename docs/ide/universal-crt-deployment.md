---
title: Bereitstellung der universellen CRT | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20006118d4bf27c379b78b84dc8807a4fd6c5e6c
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256270"
---
# <a name="universal-crt-deployment"></a>Bereitstellung der universellen CRT

Von Visual Studio .NET bis Visual Studio 2013 enthielt jedes Hauptrelease der C++-Compiler und -Tools eine neue, eigenständige Version der Microsoft C-Laufzeitbibliothek (CRT). Diese eigenständigen Versionen der CRT waren unabhängig voneinander und teilweise nicht miteinander kompatibel. Die CRT-Bibliothek, die von Visual Studio 2012 verwendet wurde, war beispielsweise Version 11 (msvcr110.dll), und die CRT, die von Visual Studio 2013 verwendet wurde, war Version 12 (msvcr120.dll). Ab Visual Studio 2015 ist dies nicht mehr der Fall. Visual Studio 2015 und höhere Versionen von Visual Studio verwenden die universelle CRT.

Die universelle CRT ist eine Betriebssystemkomponente von Microsoft Windows. Sie ist als Teil des Betriebssystems in Windows 10 enthalten und für ältere Betriebssysteme von Windows Vista bis Windows 8.1 über Windows Update verfügbar. Zusätzlich wird die lokale Bereitstellung der universellen CRT mit einigen Einschränkungen unterstützt.

## <a name="central-deployment"></a>Zentrale Bereitstellung

Die bevorzugte Methode zur zentralen Installation der universellen CRT ist die Verwendung von Microsoft Windows Update. Bei der universellen CRT handelt es sich um ein empfohlenes Update für alle unterstützten Microsoft Windows-Betriebssysteme. Deshalb wird sie auf den meisten Computern standardmäßig im Rahmen des regulären Updatevorgangs installiert. Das erste Release der universellen CRT war [KB2999226](https://support.microsoft.com/en-us/kb/2999226). Ein nachfolgendes Update mit verschiedenen Fehlerbehebungen wurde in [KB3118401](https://support.microsoft.com/en-us/kb/3118401) durchgeführt, außerdem gab es zusätzliche Updates mit weiteren Fehlerbehebungen und neuen Features. Weitere Informationen zu aktuelleren Updates finden Sie, wenn Sie [support.microsoft.com](https://support.microsoft.com) nach „Universal C Runtime“ oder „Universal CRT“ durchsuchen.

Nicht alle Microsoft Windows-Computer installieren regelmäßig Updates über Windows Update, und manche installieren möglicherweise nicht alle empfohlenen Updates. Es sind verteilbare Komponenten der universellen CRT verfügbar, die offline verteilt werden können und so die Verwendung von Anwendungen unterstützen, die auf diesen Computern mithilfe von Visual Studio 2015 und höheren C++-Toolsets erstellt wurden. Diese verteilbaren Komponenten können unter einem der obenstehenden KB-Links heruntergeladen werden. Beachten Sie, dass die verteilbaren Komponenten der universellen CRT erfordern, dass der Computer auf das aktuelle Service Pack aktualisiert wurde. Die verteilbare Komponente für Windows 7 kann also beispielsweise nur unter Windows 7 SP1, nicht unter Windows 7 RTM installiert werden.

Da die universelle CRT grundlegend von den C++-Bibliotheken abhängt, installiert die verteilbare Visual C++-Komponente (VCRedist) eine Basisversion der universellen CRT auf den Computern, auf denen noch keine Version installiert ist, die für die C++-Bibliotheksabhängigkeiten ausreichend ist. Wenn Ihre Anwendung von einer aktuelleren Version der universellen CRT abhängt, müssen Sie diese Version explizit installieren. Es wird empfohlen, diese zu installieren, bevor Sie „VCRedist“ installieren, um mehrere möglicherweise erforderliche Neustarts zu verhindern.

## <a name="local-deployment"></a>Lokale Bereitstellung

Die lokale Bereitstellung der App der universellen CRT wird zwar unterstützt, aber aus Leistungs- und Sicherheitsgründen nicht empfohlen.  Die DLLs für die lokale Bereitstellung sind im Windows SDK im Unterverzeichnis Windows Kits\\10\\Redist\\ucrt\\DLLs (je nach Computerarchitektur) enthalten. Die erforderlichen DLLs enthalten „ucrtbase.dll“ und mehrere APISet-Weiterleitungs-DLLs namens „api-ms-win-\*.dll“. Da die erforderlichen DLLs auf jedem Betriebssystem variieren, wird empfohlen, dass Sie bei der lokalen Bereitstellung alle DLLs einschließen.

Es gibt zwei Einschränkungen bei der lokalen Bereitstellung, die Sie berücksichtigen müssen:

- Unter Windows 10 wird immer die universelle CRT im Systemverzeichnis verwendet, auch wenn eine Anwendung eine anwendungsspezifische Kopie der universellen CRT enthält. Dies gilt auch, wenn die lokale Kopie der universellen CRT aktueller ist. Dies liegt daran, dass die universelle CRT unter Windows 10 eine Kernkomponente des Betriebssystems ist.

- Auf Versionen vor Windows 8 kann die universelle CRT nicht lokal mit einem Plug-In gepackt werden, das sich in einem anderen Verzeichnis als die ausführbare Hauptdatei Ihrer App befindet. Die APISet-Weiterleitungs-DLLs können „ucrtbase.dll“ in diesem Fall nicht erfolgreich auflösen. Folgende alternative Lösungen werden empfohlen:

  - Verknüpfen Sie die universelle CRT statisch,
  - stellen Sie sie zentral bereit, oder
  - platzieren Sie die Dateien der universellen CRT im selben Verzeichnis wie die App.

## <a name="deployment-on-microsoft-windows-xp"></a>Bereitstellung unter Microsoft Windows XP

Visual Studio 2015 und Visual Studio 2017 unterstützen die Entwicklung von Software für Microsoft Windows XP weiterhin. Deshalb gibt es eine Version der universellen CRT, die unter Microsoft Windows XP funktioniert. Das Betriebssystem Microsoft Windows XP wird nicht mehr grundlegend oder erweitert unterstützt, deshalb unterscheidet die zentrale Bereitstellung der universellen CRT unter Microsoft Windows XP sich von der unter anderen Betriebssystemen.

Wenn die verteilbare Visual C++-Komponente unter Windows XP installiert wird, installiert diese die universelle CRT und alle Abhängigkeiten direkt im Systemverzeichnis, ohne Windows-Updates zu installieren und ohne Abhängigkeiten von diesen. Für die verteilbaren Mergemodule (die Microsoft_VC*version*_CRT_\*.msm-Dateien) gilt das gleiche.

Die lokale Bereitstellung der universellen CRT unter Windows XP unterscheidet sich nicht von der auf anderen unterstützten Betriebssystemen.

## <a name="see-also"></a>Siehe auch

- [Bereitstellung in Visual C++](deployment-in-visual-cpp.md)
