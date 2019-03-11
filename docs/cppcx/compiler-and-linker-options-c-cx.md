---
title: Optionen für Compiler und Linker (C++/CX)
ms.date: 01/22/2017
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
ms.openlocfilehash: cc1964c57d6700995bb283c245e4c63c8e9e313b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750909"
---
# <a name="compiler-and-linker-options-ccx"></a>Optionen für Compiler und Linker (C++/CX)

Eine Umgebungsvariable, C++ / CX-Compileroptionen und Linkeroptionen unterstützen die Erstellung von apps, für die Windows-Runtime.

## <a name="library-path"></a>Bibliothekspfad

Die %LIBPATH%-Umgebungsvariable gibt den Standardpfad für die Suche nach WINMD-Dateien an.

## <a name="compiler-options"></a>Compileroptionen

|Option|Beschreibung|
|------------|-----------------|
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW:nostdlib|Ermöglicht es Windows-Runtime-spracherweiterungen.<br /><br /> Der `nostdlib` -Parameter verhindert, dass der Compiler den standardmäßigen, vordefinierten Suchpfad verwendet, um Assembly- und WINMD-Dateien zu finden.<br /><br /> Die Compileroption **/ZW** gibt die folgenden Compileroptionen implizit an:<br /><br />- **/Fi** vccorlib.h: Erzwingt die Einbindung der Headerdatei „vccorlib.h“, die viele für den Compiler erforderliche Typen definiert.<br />- [/ FU](../build/reference/fu-name-forced-hash-using-file.md) Windows.winmd, erzwingt die Einbindung der Windows.winmd-Metadatendatei, die vom Betriebssystem bereitgestellt wird, und viele Typen in der Windows-Runtime definiert.<br />- **/FU** Platform.winmd: Erzwingt die Einbindung der Platform.winmd-Metadatendatei, die vom Compiler bereitgestellt wird und die meisten Typen in der Plattformfamilie von Namespaces definiert.|
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|Fügt ein durch den *dir* -Parameter angegebenes Verzeichnis zum Suchpfad hinzu, der vom Compiler für die Suche nach Assembly- und WINMD-Dateien verwendet wird.|
|**/FU**  *Datei*|Erzwingt die Einbindung des angegebenen Moduls oder der WINMD-Datei. D. h. Sie müssen keine geben `#using` *Datei* in Ihrem Quellcode. Der Compiler erzwingt automatisch die Einbindung der eigenen Windows-Metadatendatei „Platform.winmd“.|
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

Wenn Sie **/ZW**verwenden, stellt der Compiler automatisch eine Verknüpfung zur DLL-Version der C-Laufzeit (CRT) her. Verknüpfen mit der statischen Bibliotheksversion ist nicht zulässig, und jede Verwendung der CRT-Funktionen, die nicht in einer universellen Windows-Plattform-app dürfen führt dazu, dass einen Fehler während der Kompilierung.

## <a name="see-also"></a>Siehe auch

[Erstellen von apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)
