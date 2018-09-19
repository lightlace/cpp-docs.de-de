---
title: -SUBSYSTEM | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81c20f345b56f11179b37b4663d3cfc84d159116
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725958"
---
# <a name="subsystem"></a>/SUBSYSTEM

Gibt die vom ausführbaren Image benötigte Ausführungsumgebung an.

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]
```

## <a name="remarks"></a>Hinweise

Mit dieser Option wird das Image so bearbeitet, dass erkennbar ist, welches Subsystem vom Betriebssystem zur Ausführung aufgerufen werden muss.

Sie können jedes der folgenden Subsysteme angeben:

**BOOT_APPLICATION**<br/>
Eine in der Windows-Startumgebung ausgeführte Anwendung. Weitere Informationen zu startanwendungen finden Sie unter [Informationen zum BCD WMI-Anbieter](/previous-versions/windows/desktop/bcd/about-bcd).

**VERWALTUNGSKONSOLE**<br/>
Eine Windows-Zeichenmodusanwendung. Im Betriebssystem wird eine Konsole für Konsolenanwendungen zur Verfügung gestellt.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Extensible Firmware Interface (EFI)-Image

Die EFI-Subsystemoptionen beschreiben ausführbare Images, die in die Extensible Firmware Interface-Umgebung ausgeführt werden. Diese Umgebung wird in der Regel mit der Hardware bereitgestellt und ausgeführt, bevor das Betriebssystem geladen wird. Die Hauptunterschiede zwischen EFI-Imagetypen sind die Speicheradresse, in die das Image geladen wird und die Aktionen, die ausgeführt wird, wenn der Aufruf zum Image zurückgegeben wird. Ein EFI_APPLICATIONS-Image wird entladen, wenn die Steuerung zurückgegeben wird. Ein EFI_BOOT_SERVICE_DRIVER oder ein EFI_RUNTIME_DRIVER wird entladen, wenn die Steuerung mit einem Fehlercode zurückgegeben wird. Ein EFI_ROM-Image wird vom ROM ausgeführt. Weitere Informationen finden Sie unter den Spezifikationen für die [Unified EFI Forum](http://www.uefi.org/) Website.

**NATIVE**<br/>
Code, der ohne eine Subsystemumgebung ausgeführt wird – z. B. Gerätetreiber im Kernelmodus und systemeigene Systemprozesse. Diese Option ist üblicherweise für Windows-Systemfunktionen reserviert.

**POSIX**<br/>
Eine App, die im POSIX-Subsystem in Windows ausgeführt wird.

**WINDOWS**<br/>
Eine App, die in der grafischen Umgebung von Windows ausgeführt wird. Dies umfasst desktop-apps und apps der universellen Windows-Plattform (UWP).

**WINDOWS CE**<br/>
Das WINDOWSCE-Subsystem gibt an, dass die App dafür vorgesehen ist, auf einem Gerät mit einer Version von Windows CE-Kernels ausgeführt zu werden. Kernelversionen schließen PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0-6.0R3 und Windows Embedded Compact 7 ein.

Mit den optionalen `major` und `minor`-Werten werden die Mindestanforderungen in Bezug auf die Version des angegebenen Subsystems festgelegt:

- Der Ganzzahlenbereich der Versionsnummer (der Abschnitt links vom Dezimalpunkt) wird durch `major` wiedergegeben.

- Der Nachkommabereich der Versionsnummer (der Abschnitt rechts vom Dezimalpunkt) wird durch `minor` wiedergegeben.

- Die Werte für `major` und `minor` müssen in einem Bereich von 0 bis 65.535 liegen.

Die Wahl des Subsystems wirkt sich auf die Standardstartadresse des Programms aus. Weitere Informationen finden Sie unter [/Entry (Symbol für Einstiegspunkt)](../../build/reference/entry-entry-point-symbol.md), der Linkeroption/Entry:*Funktion* Option.

Weitere Informationen, einschließlich der Minimum- und Standardversionsnummern Werte für die Haupt-und Nebenversionsnummern Zahlen für jedes Subsystem, finden Sie unter den [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) -Linkeroption.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)