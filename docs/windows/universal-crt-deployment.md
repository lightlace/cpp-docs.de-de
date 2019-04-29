---
title: Bereitstellung der universellen CRT
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 7952d2ec6e8f502b0edf776811a492c67f495cce
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344172"
---
# <a name="universal-crt-deployment"></a>Bereitstellung der universellen CRT

Von Visual Studio .NET bis Visual Studio 2013 enthielt jedes Hauptrelease der C++-Compiler und -Tools eine neue, eigenständige Version der Microsoft C-Laufzeitbibliothek (CRT). Diese eigenständigen Versionen der CRT waren unabhängig voneinander und teilweise nicht miteinander kompatibel. Die CRT-Bibliothek, die von Visual Studio 2012 verwendet wurde, war beispielsweise Version 11 (msvcr110.dll), und die CRT, die von Visual Studio 2013 verwendet wurde, war Version 12 (msvcr120.dll). Ab Visual Studio 2015 ist dies nicht mehr der Fall. Visual Studio 2015 und höhere Versionen von Visual Studio verwenden die universelle CRT.

Die universelle CRT ist eine Betriebssystemkomponente von Microsoft Windows. Sie ist als Teil des Betriebssystems in Windows 10 enthalten und für ältere Betriebssysteme von Windows Vista bis Windows 8.1 über Windows Update verfügbar. Zusätzlich wird die lokale Bereitstellung der universellen CRT mit einigen Einschränkungen unterstützt.

## <a name="central-deployment"></a>Zentrale Bereitstellung

Die bevorzugte Methode zur zentralen Installation der universellen CRT ist die Verwendung von Microsoft Windows Update. Bei der universellen CRT handelt es sich um ein empfohlenes Update für alle unterstützten Microsoft Windows-Betriebssysteme. Deshalb wird sie auf den meisten Computern standardmäßig im Rahmen des regulären Updatevorgangs installiert. Das erste Release der universellen CRT war [KB2999226](https://support.microsoft.com/kb/2999226). Ein nachfolgendes Update mit verschiedenen Fehlerbehebungen wurde in [KB3118401](https://support.microsoft.com/kb/3118401) durchgeführt, außerdem gab es zusätzliche Updates mit weiteren Fehlerbehebungen und neuen Features. Weitere Informationen zu aktuelleren Updates finden Sie, wenn Sie [support.microsoft.com](https://support.microsoft.com) nach „Universal C Runtime“ oder „Universal CRT“ durchsuchen.

Nicht alle Microsoft Windows-Computer installieren regelmäßig Updates über Windows Update, und manche installieren möglicherweise nicht alle empfohlenen Updates. Es sind verteilbare Komponenten der universellen CRT verfügbar, die offline verteilt werden können und so die Verwendung von Anwendungen unterstützen, die auf diesen Computern mithilfe von Visual Studio 2015 und höheren C++-Toolsets erstellt wurden. Diese verteilbaren Komponenten können unter einem der obenstehenden KB-Links heruntergeladen werden. Beachten Sie, dass die verteilbaren Komponenten der universellen CRT erfordern, dass der Computer auf das aktuelle Service Pack aktualisiert wurde. Die verteilbare Komponente für Windows 7 kann also beispielsweise nur unter Windows 7 SP1, nicht unter Windows 7 RTM installiert werden.

Da der Universal CRT eine grundlegende Abhängigkeit ist die C++ Bibliotheken, die Visualisierung C++ redistributable (VCRedist) wird die erste Version der Universal CRT (Version 10.0.10240) installiert, auf Computern, die nicht über eine bereits installierte Version verfügen. Diese Version ist ausreichend, um das erfüllen der C++ bibliotheksabhängigkeiten. Wenn Ihre Anwendung auf eine neuere Version der Universal CRT abhängig ist, müssen Sie um Ihren Computer auf dem neuesten Stand zu bringen mithilfe von Windows Update oder installieren diese Version explizit. Es wird empfohlen, um die universelle C-Laufzeit bereits über Windows Update oder über MSU installiert, vor der Installation der Komponente Vcredist installiert werden, um potenzielle zu vermeiden mehrere erforderlichen Neustarts zu erhalten.

Nicht alle Betriebssysteme sind für die letzten universelle C-Laufzeit über Windows Update. Unter Windows 10 entspricht die zentral bereitgestellte Version die Version des Betriebssystems. Darüber hinaus müssen Sie das Betriebssystem aktualisieren, um die universelle C-Laufzeit zu aktualisieren. Für Windows Vista über Windows 8.1 basiert die neueste verfügbare Universal C Runtime derzeit auf die Version, in das Windows 10 Anniversary Update mit zusätzlichen Fixes (Version 10.0.14393) enthalten.

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
