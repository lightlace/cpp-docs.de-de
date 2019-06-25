---
title: Bereitstellung der universellen CRT
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 1f6e685cca65c4b31ac2e6147341c4b5a3fe8228
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344459"
---
# <a name="universal-crt-deployment"></a>Bereitstellung der universellen CRT

Von Visual Studio .NET bis Visual Studio 2013 enthielt jedes Hauptrelease der C++-Compiler und -Tools eine neue, eigenständige Version der Microsoft C-Laufzeitbibliothek (CRT). Diese eigenständigen Versionen der CRT waren unabhängig voneinander und teilweise nicht miteinander kompatibel. Die CRT-Bibliothek, die von Visual Studio 2012 verwendet wurde, war beispielsweise Version 11 (msvcr110.dll), und die CRT, die von Visual Studio 2013 verwendet wurde, war Version 12 (msvcr120.dll). Ab Visual Studio 2015, ist es nicht mehr der Fall. Visual Studio 2015 und höhere Versionen von Visual Studio verwenden die universelle CRT.

Der Universal CRT ist eine Komponente des Betriebssystems Microsoft Windows als Teil des Betriebssystems in Windows 10 enthalten. Es steht für ältere Betriebssysteme Windows Vista über Windows 8.1, mithilfe von Windows Update zur Verfügung. Lokale Bereitstellung der Universal CRT wird mit einigen Einschränkungen unterstützt.

## <a name="central-deployment"></a>Zentrale Bereitstellung

Die bevorzugte Methode zur zentralen Installation der universellen CRT ist die Verwendung von Microsoft Windows Update. Bei der universellen CRT handelt es sich um ein empfohlenes Update für alle unterstützten Microsoft Windows-Betriebssysteme. Deshalb wird sie auf den meisten Computern standardmäßig im Rahmen des regulären Updatevorgangs installiert. Die erste Version der Universal CRT wurde [KB2999226](https://support.microsoft.com/kb/2999226). Ein neueres Update mit verschiedenen Fehlerkorrekturen erfolgte [KB3118401](https://support.microsoft.com/kb/3118401), und es wurden zusätzliche Updates mit weiteren Fehlerbehebungen und neuen Features. Weitere Informationen zu aktuelleren Updates finden Sie, wenn Sie [support.microsoft.com](https://support.microsoft.com) nach „Universal C Runtime“ oder „Universal CRT“ durchsuchen.

Nicht alle Microsoft Windows-Computer installieren regelmäßig Updates über Windows Update, und manche installieren möglicherweise nicht alle empfohlenen Updates. Zur Unterstützung von Anwendungen mithilfe von Visual Studio 2015 erstellte und höher C++ Toolsets auf diesen Computern stehen Universal CRT weitervertreibbare Dateien für die offline-Verteilung. Die verteilbaren Dateien möglicherweise von einem der oben angezeigten Links KB heruntergeladen werden. Der Universal CRT redistributable erfordert, dass der Computer auf das aktuelle Servicepack aktualisiert wurde. Die verteilbare Komponente für Windows 7 kann also beispielsweise nur unter Windows 7 SP1, nicht unter Windows 7 RTM installiert werden.

Da der Universal CRT eine grundlegende Abhängigkeit ist die C++ Bibliotheken, die Visualisierung C++ redistributable (VCRedist) wird die erste Version der Universal CRT (Version 10.0.10240) auf Computern, die Installation noch nicht installiert. Diese Version ist ausreichend, um das erfüllen der C++ bibliotheksabhängigkeiten. Wenn Ihre Anwendung auf eine neuere Version der Universal CRT abhängig ist, müssen Sie um Ihren Computer auf dem neuesten Stand zu bringen mithilfe von Windows Update oder installieren diese Version explizit. Es wird empfohlen, installieren die universelle C-Laufzeit über Windows Update oder eine MSU vor dem Neustart installieren die Komponente Vcredist installiert werden, um potenzielle mehrere erforderlich zu vermeiden.

Nicht alle Betriebssysteme sind für die letzten universelle C-Laufzeit über Windows Update. Unter Windows 10 entspricht die zentral bereitgestellte Version die Version des Betriebssystems. Darüber hinaus müssen Sie das Betriebssystem aktualisieren, um die universelle C-Laufzeit zu aktualisieren. Für Windows Vista über Windows 8.1 basiert die neueste verfügbare Universal C Runtime derzeit auf die Version, in das Windows 10 Anniversary Update mit zusätzlichen Fixes (Version 10.0.14393) enthalten.

## <a name="local-deployment"></a>Lokale Bereitstellung

Die lokale Bereitstellung der App der universellen CRT wird zwar unterstützt, aber aus Leistungs- und Sicherheitsgründen nicht empfohlen. Die DLLs für die lokale Bereitstellung sind im Windows SDK im Unterverzeichnis Windows Kits\\10\\Redist\\ucrt\\DLLs (je nach Computerarchitektur) enthalten. Die erforderlichen DLLs enthalten „ucrtbase.dll“ und mehrere APISet-Weiterleitungs-DLLs namens „api-ms-win-\*.dll“. Der Satz von DLLs, die erforderlich sind, unter jedem Betriebssystem variiert. Es wird dringend empfohlen, dass Sie alle DLLs, enthalten Wenn Sie lokal bereitstellen.

Es gibt zwei Einschränkungen bei der lokalen Bereitstellung, die Sie berücksichtigen müssen:

- Unter Windows 10 wird immer die universelle CRT im Systemverzeichnis verwendet, auch wenn eine Anwendung eine anwendungsspezifische Kopie der universellen CRT enthält. Es ist "true", auch wenn die lokale Kopie höher ist, da der Universal CRT eine Kernkomponente des Betriebssystems auf Windows 10 ist.

- Bei Versionen von Windows vor Windows 8 kann nicht der Universal CRT lokal mit einem Plug-in verpackt werden, es befindet sich in einem anderen Verzeichnis als dem Verzeichnis der ausführbaren Datei der Haupt-app. Die APISet-Weiterleitungs-DLLs können „ucrtbase.dll“ in diesem Fall nicht erfolgreich auflösen. Folgende alternative Lösungen werden empfohlen:

  - Verknüpfen Sie die universelle CRT statisch,
  - stellen Sie sie zentral bereit, oder
  - platzieren Sie die Dateien der universellen CRT im selben Verzeichnis wie die App.

## <a name="deployment-on-microsoft-windows-xp"></a>Bereitstellung unter Microsoft Windows XP

Visual Studio 2015 und Visual Studio 2017 unterstützen die Entwicklung von Software für Microsoft Windows XP weiterhin. Um diese Entwicklung zu unterstützen, kann eine Version der Universal CRT unter Microsoft Windows XP verwendet werden. Das Betriebssystem Microsoft Windows XP wird nicht mehr grundlegend oder erweitert unterstützt, deshalb unterscheidet die zentrale Bereitstellung der universellen CRT unter Microsoft Windows XP sich von der unter anderen Betriebssystemen.

Wenn das visuelle Element C++ redistributable ist installiert. unter Windows XP, ihn direkt der Universal CRT und alle seine Abhängigkeiten ins Systemverzeichnis installiert. Es nicht installieren oder ein Windows-Update abhängig. Für die verteilbaren Mergemodule (die Microsoft_VC*version*_CRT_\*.msm-Dateien) gilt das gleiche.

Die lokale Bereitstellung der universellen CRT unter Windows XP unterscheidet sich nicht von der auf anderen unterstützten Betriebssystemen.

## <a name="see-also"></a>Siehe auch

- [Bereitstellung in Visual C++](deployment-in-visual-cpp.md)
