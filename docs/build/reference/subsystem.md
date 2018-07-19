---
title: -SUBSYSTEM | Microsoft Docs
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
ms.openlocfilehash: c12df1a2166c9ef5a1af8a33a5764a8899909edb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377622"
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
  
 BOOT_APPLICATION  
 Eine in der Windows-Startumgebung ausgeführte Anwendung. Weitere Informationen zu startanwendungen finden Sie unter [zu der BCD WMI-Provider](http://msdn.microsoft.com/library/aa362639.aspx).  
  
 CONSOLE  
 Eine Windows-Zeichenmodusanwendung. Im Betriebssystem wird eine Konsole für Konsolenanwendungen zur Verfügung gestellt.  
  
 Extensible Firmware Interface (EFI)-Image  
 Die EFI-Subsystemoptionen beschreiben ausführbare Images, die in die Extensible Firmware Interface-Umgebung ausgeführt werden. Diese Umgebung wird in der Regel mit der Hardware bereitgestellt und ausgeführt, bevor das Betriebssystem geladen wird. Die Hauptunterschiede zwischen EFI-Imagetypen sind die Speicheradresse, in die das Image geladen wird und die Aktionen, die ausgeführt wird, wenn der Aufruf zum Image zurückgegeben wird. Ein EFI_APPLICATIONS-Image wird entladen, wenn die Steuerung zurückgegeben wird. Ein EFI_BOOT_SERVICE_DRIVER oder ein EFI_RUNTIME_DRIVER wird entladen, wenn die Steuerung mit einem Fehlercode zurückgegeben wird. Ein EFI_ROM-Image wird vom ROM ausgeführt. Weitere Informationen finden Sie unter den Spezifikationen für die [Unified EFI Forum](http://www.uefi.org/) Website.  
  
 NATIVE  
 Code, der ohne eine Subsystemumgebung ausgeführt wird – z. B. Gerätetreiber im Kernelmodus und systemeigene Systemprozesse. Diese Option ist üblicherweise für Windows-Systemfunktionen reserviert.  
  
 POSIX  
 Eine App, die im POSIX-Subsystem in Windows ausgeführt wird.  
  
 WINDOWS  
 Eine App, die in der grafischen Umgebung von Windows ausgeführt wird. Dies umfasst desktop-apps und apps der universellen Windows-Plattform (UWP).  
  
 WINDOWSCE  
 Das WINDOWSCE-Subsystem gibt an, dass die App dafür vorgesehen ist, auf einem Gerät mit einer Version von Windows CE-Kernels ausgeführt zu werden. Kernelversionen schließen PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0-6.0R3 und Windows Embedded Compact 7 ein.  
  
 Mit den optionalen `major` und `minor`-Werten werden die Mindestanforderungen in Bezug auf die Version des angegebenen Subsystems festgelegt:  
  
-   Der Ganzzahlenbereich der Versionsnummer (der Abschnitt links vom Dezimalpunkt) wird durch `major` wiedergegeben.  
  
-   Der Nachkommabereich der Versionsnummer (der Abschnitt rechts vom Dezimalpunkt) wird durch `minor` wiedergegeben.  
  
-   Die Werte für `major` und `minor` müssen in einem Bereich von 0 bis 65.535 liegen.  
  
 Die Wahl des Subsystems wirkt sich auf die Standardstartadresse des Programms aus. Weitere Informationen finden Sie unter [/Entry (Symbol für Einstiegspunkt)](../../build/reference/entry-entry-point-symbol.md), der Linker/Entry:*Funktion* Option.  
  
 Weitere Informationen, einschließlich der Minimum- und Standardversionsnummern Werte für die Haupt- und Nebenversionsnummern Versionsnummern für jedes Subsystem, finden Sie unter der [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) (Linkeroption).  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)