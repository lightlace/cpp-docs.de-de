---
title: Universal CRT-Bereitstellung | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="universal-crt-deployment"></a>Universal CRT-Bereitstellung

Aus Visual Studio .NET über Visual Studio 2013 ist jede Hauptversion von der C++-Compiler und Tools eine neue, eigenständige Version der Microsoft C Runtime (CRT)-Bibliothek enthalten. Diese eigenständigen Versionen der CRT wurden unabhängig aus, und klicken Sie auf verschiedenen Grad, nicht miteinander kompatibel. Z. B. die CRT-Bibliothek, die von Visual Studio 2012 verwendet wurde, Version 11, benannte msvcr110.dll, und die CRT verwendet, die für Visual Studio 2013 wurde Version 12, benannte msvcr120.dll. Ab Visual Studio 2015, ist dies nicht mehr der Fall. Verwenden Visual Studio 2015 und höheren Versionen von Visual Studio, die alle eine Universal CRT.

Universal CRT ist eine Komponente des Betriebssystems Microsoft Windows. Es wird als Teil des Betriebssystems in Windows 10 enthalten und steht für ältere Betriebssysteme Windows Vista über Windows 8.1, mithilfe von Windows Update. Darüber hinaus wird lokale Bereitstellung von Universal CRT, mit einigen Einschränkungen unterstützt.

## <a name="central-deployment"></a>Zentrale Bereitstellung

Die bevorzugte Methode, zentral Universal CRT installiert ist, Microsoft Windows Update zu verwenden. Universal CRT ist eine empfohlene Update für alle Microsoft Windows-Betriebssystemen unterstützte durch standardmäßig die meisten Computer im Rahmen des regulären Updateprozesses Installationsspeicherorts. Wurde der Erstveröffentlichung von Universal CRT [KB2999226](https://support.microsoft.com/en-us/kb/2999226); eine nachfolgende Aktualisierung mit verschiedenen Bugfixes wurde infolge von [KB3118401](https://support.microsoft.com/en-us/kb/3118401), und es wurden zusätzliche Updates mit weiteren Fehlerkorrekturen und neue Funktionen. Suchen Sie nach aktuellen Updates ["Support.Microsoft.com"](https://support.microsoft.com) für universelle C-Laufzeit oder Universal CRT.

Nicht alle Microsoft Windows-Computer mithilfe der Windows Update regelmäßig Updates installieren, und einige möglicherweise nicht alle empfohlene Updates installieren. Zur Unterstützung von Anwendungen, die mithilfe der Visual Studio 2015 und höher C++-Toolsets auf den Computern erstellt wurden, sind Universal CRT verteilbare Komponenten für die Verteilung offline verfügbar. Die verteilbaren Dateien möglicherweise von einer der oben angezeigten Links KB heruntergeladen werden. Bitte beachten Sie, dass der Universal CRT verteilbare Komponenten erfordert, dass der Computer auf das aktuelle Servicepack aktualisiert wurde. Deshalb wird z. B. die verteilbare Komponente für Windows 7 nur auf Windows 7 SP1, nicht Windows 7 RTM installieren.

Da der Universal CRT eine grundlegende Abhängigkeit von der C++-Bibliotheken ist, installiert das Visual C++ redistributable (VCRedist) eine Basisversion der Universal CRT auf Computern, auf denen eine Version, die bereits installierte, ausreichend, um die C++-Standardbibliothek erfüllen kein Abhängigkeiten. Wenn Ihre Anwendung auf eine neuere Version der Universal CRT abhängig ist, müssen Sie explizit, neuere Version installieren. Es wird empfohlen, zum Installieren dieses vor dem Installieren von VCRedist, zur Vermeidung von potenziellen mehrere erforderlich, neu gestartet wurde.

## <a name="local-deployment"></a>Lokale Bereitstellung

Lokale Bereitstellung von Universal CRT wird unterstützt, aber für Leistung und aus Sicherheitsgründen nicht empfohlen.  Die DLLs für die lokale Bereitstellung sind Bestandteil des Windows SDK, in der Windows-Kits\\10\\Redist\\Ucrt\\DLLs-Unterverzeichnis von Computerarchitektur. Die DLLs erforderlich sind, gehören ucrtbase.dll und einen Satz von APISet Weiterleitung DLLs, die mit dem Namen api-ms-Win -\*DLL. Der Satz von DLLs, die erforderlich sind, unter jedem Betriebssystem variiert, es wird dringend empfohlen, dass Sie alle DLLs, enthalten Wenn Sie lokal bereitstellen.

Es gibt zwei Einschränkungen bei der lokalen Bereitstellung zu berücksichtigen:

- Universal CRT in das Verzeichnis "System" wird unter Windows 10 immer verwendet, auch wenn eine Anwendung mit eine lokalen Kopie der Universal CRT enthält. Dies gilt auch, wenn die lokale Kopie der Universal CRT neuer ist. Dies ist der Universal CRT ist eine Kernkomponente des Betriebssystems auf Windows 10.

- Bei Versionen von Windows vor Windows 8 können nicht Universal CRT lokal mit einem Plug-in zusammengefasst werden, die in einem anderen Verzeichnis Verzeichnis befindet, der Hauptausführungsdatei für Ihre app enthält. Die Weiterleitung APISet DLLs kann die ucrtbase.dll in diesem Fall erfolgreich aufgelöst werden. Einige empfohlene alternativen Lösungen sind:

  - Universal CRT statisch zu verknüpfen,
  - Universal CRT zentral bereitstellen oder
  - Platzieren Sie die Universal CRT-Dateien im selben Verzeichnis wie die app an.

## <a name="deployment-on-microsoft-windows-xp"></a>Bereitstellung auf Microsoft Windows XP

Visual Studio 2015 und Visual Studio 2017 weiterhin Entwicklung von Software für die Verwendung in Microsoft Windows XP unterstützt. Um dies zu unterstützen, kann eine Universal CRT-Version unter Microsoft Windows XP verwendet werden. Das Betriebssystem Microsoft Windows XP ist nicht mehr in der grundlegenden oder erweiterten Unterstützung, also zentrale Bereitstellung von Universal CRT auf Microsoft Windows XP sich von anderen Betriebssystemen.

Wenn das Visual C++ redistributable auf Windows XP installiert ist, erfolgt die Installation direkt Universal CRT und alle abhängigen Elemente in das Systemverzeichnis ohne installieren oder abhängig von Windows Update. Die verteilbare Mergemodule der Microsoft_VC*Version*_CRT_\*MSM-Dateien, gehen Sie genauso vor.

Lokale Bereitstellung von Universal CRT unter Windows XP ist wie auf anderen unterstützten Betriebssysteme.

## <a name="see-also"></a>Siehe auch

- [Bereitstellung in Visual C++](deployment-in-visual-cpp.md)
