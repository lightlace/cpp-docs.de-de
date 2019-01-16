---
title: 'Vorgehensweise: Verwenden von winmdidl.exe und midlrt.exe zum Erstellen von .h-Dateien aus Windows-Metadaten'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
ms.openlocfilehash: b81f6901e60f27ada27f14d7dbc7c10fa3faec34
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335990"
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Vorgehensweise: Verwenden von winmdidl.exe und midlrt.exe zum Erstellen von .h-Dateien aus Windows-Metadaten

"Winmdidl.exe" und "midlrt.exe" aktivieren Interaktionen auf COM-Ebene zwischen systemeigenem C++-Code und Komponenten für Windows-Runtime. "Winmdidl.exe" verwendet als Eingabe eine WINMD-Datei, die Metadaten für eine Komponente für Windows-Runtime enthält, und gibt eine IDL-Datei aus. "Midlrt.exe" konvertiert diese IDL-Datei in Headerdateien, die der C++-Code verarbeiten kann. Beide Tools werden an der Befehlszeile ausgeführt.

Sie verwenden diese Tools in zwei Hauptszenarien:

- Erstellen von benutzerdefinierten IDL-Dateien und Headerdateien, sodass eine C++-App, die mithilfe der Vorlagenbibliothek für Windows-Runtime geschrieben wurde, eine benutzerdefinierte Komponente für Windows-Runtime verarbeiten kann

- Generieren von Proxy- und Stub-Dateien für benutzerdefinierte Ereignistypen in einer Komponente für Windows-Runtime Weitere Informationen finden Sie unter [benutzerdefinierte Ereignisse und ereigniszugriffsmethoden in Windows-Runtime-Komponenten](/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components).

Diese Tools sind nur für das Analysieren von benutzerdefinierten WINMD-Dateien erforderlich. Die IDL- und H-Dateien für Komponenten des Windows-Betriebssystems sind bereits für Sie generiert. Wird standardmäßig in Windows 8.1, befinden sie sich die Dateien (x86) \Windows Kits\8.1\Include\winrt \Programme\\.

## <a name="location-of-the-tools"></a>Speicherort der Tools

Standardmäßig in [Windows 8.1, winmdidl.exe und midlrt.exe befinden sich in C:\Program Files (x86) \Windows Kits\8.1\\. Versionen der Tools sind auch in den Ordnern "\bin\x86\" und "\bin\x64\" verfügbar.

## <a name="winmdidl-command-line-arguments"></a>Winmdidl-Befehlszeilenargumente

```
Winmdidl.exe [/nologo] [/suppressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile
```

**/nologo**<br/>
Verhindert die Anzeige der winmdidl-Copyrightmeldung und -Versionsnummer auf der Konsole.

**/suppressversioncheck**<br/>
Nicht verwendet.

**/time**<br/>
Zeigt die gesamte Ausführungszeit in der Konsolenausgabe an.

**/outdir:**<em>dir</em><br/>
Gibt ein Ausgabeverzeichnis an. Wenn der Pfad Leerzeichen enthält, verwenden Sie Anführungszeichen. Das standardausgabeverzeichnis ist  *\<Laufwerk >*: \Users\\*\<Benutzername >* \AppData\Local\VirtualStore\Program Files (x86) \Microsoft Visual Studio 12.0\\.

**/banner:**<em>file</em><br/>
Gibt eine Datei an, die benutzerdefinierten Text enthält, der am Anfang der generierten IDL-Datei der standardmäßigen Copyrightmeldung und winmdidl-Versionsnummer vorangestellt wird. Wenn der Pfad Leerzeichen enthält, verwenden Sie Anführungszeichen.

**/utf8**<br/>
Bewirkt, dass die Datei als UTF-8 formatiert wird.

*Winmdfile*<br/>
Der Dateiname der zu analysierenden WINMD-Datei. Wenn der Pfad Leerzeichen enthält, verwenden Sie Anführungszeichen.

## <a name="midlrt-command-line-arguments"></a>Midlrt-Befehlszeilenargumente

Finden Sie unter [MIDLRT und Windows-Runtime-Komponenten](/windows/desktop/Midl/midlrt-and-windows-runtime-components).

## <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt einen winmdidl-Befehl an einer Visual Studio-x86-Eingabeaufforderung. Es wird ein Ausgabeverzeichnis und eine Datei angegeben, die speziellen Bannertext enthält, der der generierten IDL-Datei hinzugefügt wird.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0>winmdidl /nologo /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt "C:\Users\giraffe\Documents\Visual Studio 2013\Projects\Test_for_winmdidl\Debug\Test_for_winmdidl\test_for_winmdidl.winmd"`

Im folgenden Beispiel wird die Konsolenanzeige von "winmdidl" gezeigt, die angibt, dass der Vorgang erfolgreich war.

**Generieren von c:\users\giraffe\documents\\\Test_for_winmdidl.idl**

Anschließend wird "midlrt" auf der generierten IDL-Datei ausgeführt. Beachten Sie, dass die **Metadata_dir** Argument nach dem Namen der IDL-Datei angegeben ist. Der Pfad von "\WinMetadata\" ist erforderlich – es ist der Speicherort für "windows.winmd".

`C:\Program Files (x86)\Microsoft Visual Studio 12.0> midlrt "c:\users\mblome\documents\test_for_winmdidl.idl" /metadata_dir "C:\Windows\System32\WinMetadata"`

## <a name="remarks"></a>Hinweise

Die Ausgabedatei eines winmdidl-Vorgangs weist denselben Namen wie die Eingabedatei auf, hat aber die Dateinamenerweiterung IDL.

Wenn Sie eine Komponente für Windows-Runtime entwickeln, auf die von WRL zugegriffen wird, können Sie "winmdidl.exe" und "midlrt.exe" angeben, um als Postbuildschritte ausgeführt zu werden, sodass die IDL- und H-Dateien für jedes Build erzeugt werden. Ein Beispiel finden Sie unter [Auslösen von Ereignissen in Windows-Runtime-Komponenten](/uwp/winrt-components/raising-events-in-windows-runtime-components).