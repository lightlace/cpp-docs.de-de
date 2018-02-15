---
title: "Optionen für Compiler und Linker (C + c++ / CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d8da922fd9f04bf7418094293f43b3fc501aff6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="compiler-and-linker-options-ccx"></a>Optionen für Compiler und Linker (C++/CX)
Eine Umgebungsvariable C + c++ / CX-Compileroptionen und Linkeroptionen unterstützen die Erstellung von apps für Windows-Runtime.  
  
## <a name="library-path"></a>Bibliothekspfad  
 Die %LIBPATH%-Umgebungsvariable gibt den Standardpfad für die Suche nach WINMD-Dateien an.  
  
## <a name="compiler-options"></a>Compileroptionen  
  
|Option|Beschreibung|  
|------------|-----------------|  
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW:nostdlib|Aktiviert spracherweiterungen für Windows-Runtime.<br /><br /> Der `nostdlib` -Parameter verhindert, dass der Compiler den standardmäßigen, vordefinierten Suchpfad verwendet, um Assembly- und WINMD-Dateien zu finden.<br /><br /> Die Compileroption **/ZW** gibt die folgenden Compileroptionen implizit an:<br /><br /> -   **/ Fi** "vccorlib.h", erzwingt die Einbindung der Headerdatei "vccorlib.h", die viele Typen definiert, die vom Compiler erforderlich sind.<br />-   [/ FU](../build/reference/fu-name-forced-hash-using-file.md) Windows.winmd, erzwingt die Einbindung der Windows.winmd-Metadatendatei, die vom Betriebssystem bereitgestellt wird, und viele Typen in Windows-Runtime definiert.<br />-   **/FU** Platform.winmd: Erzwingt die Einbindung der Platform.winmd-Metadatendatei, die vom Compiler bereitgestellt wird und die meisten Typen in der Plattformfamilie von Namespaces definiert.|  
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|Fügt ein durch den *dir* -Parameter angegebenes Verzeichnis zum Suchpfad hinzu, der vom Compiler für die Suche nach Assembly- und WINMD-Dateien verwendet wird.|  
|**/FU**  *Datei*|Erzwingt die Einbindung des angegebenen Moduls oder der WINMD-Datei. D. h., Sie geben keine `#using` *Datei* im Quellcode. Der Compiler erzwingt automatisch die Einbindung der eigenen Windows-Metadatendatei „Platform.winmd“.|  
|/D "WINAPI_FAMILY=2"|Erstellt eine Definition, die die Verwendung einer Teilmenge des Win32-SDKS ermöglicht, die mit der Windows-Runtime kompatibel ist.|  
  
## <a name="linker-options"></a>Linkeroptionen  
  
|Option|Beschreibung|  
|------------|-----------------|  
|/APPCONTAINER[:NO]|Markiert die ausführbare Datei als (nur) „im App-Container ausführbar“.|  
|/WINMD[:{NO&#124;ONLY}]|Gibt eine WINMD-Datei und eine zugeordnete Binärdatei aus. Diese Option muss an den Linker übergeben werden, damit eine WINMD-Datei ausgegeben wird.<br /><br /> **NO**– Gibt keine WINMD-Datei, aber eine Binärdatei aus<br /><br /> **ONLY**– Gibt eine WINMD-Datei, aber keine Binärdatei aus|  
|/WINMDFILE:*Dateiname*|Der Name der auszugebenden WINMD-Datei, anstelle des Namens der WINMD-Standarddatei. Wenn mehrere Dateinamen in der Befehlszeile angegeben werden, wird der letzte Name verwendet.|  
|/WINMDDELAYSIGN[:NO]|Signiert die WINMD-Datei teilweise und platziert den öffentlichen Schlüssel in der Binärdatei.<br /><br /> **NO**– (Standard) Die WINMD-Datei wird nicht signiert.<br /><br /> /WINMDDELAYSIGN hat keine Auswirkung, sofern nicht /WINMDKEYFILE oder /WINMDKEYCONTAINER ebenfalls angegeben sind.|  
|/WINMDKEYCONTAINER:*Name*|Gibt einen Schlüsselcontainer zum Signieren einer Assembly an. Der *Name* -Parameter entspricht dem Schlüsselcontainer, der zum Signieren der Metadatendatei verwendet wird.|  
|/WINMDKEYFILE:*Dateiname*|Gibt einen Schlüssel oder ein Schlüsselpaar zum Signieren der Assembly an. Der *Dateiname* -Parameter entspricht dem Schlüssel, der zum Signieren der Metadatendatei verwendet wird.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie **/ZW**verwenden, stellt der Compiler automatisch eine Verknüpfung zur DLL-Version der C-Laufzeit (CRT) her. Verknüpfen mit der statischen Bibliotheksversion ist nicht zulässig, und jede Verwendung von CRT-Funktionen, die in einer universellen Windows-Plattform-app nicht zulässig sind verursachen einen Kompilierzeitfehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)