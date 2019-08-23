---
title: Schema Verweis für "Launch. vs. JSON" (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: 362a329289107f74cca2f20af62c8a28b4192575
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69978455"
---
# <a name="launchvsjson-schema-reference-c"></a>Schema Verweis für "Launch. vs. JSON" (C++)

Verwenden Sie die Datei *Launch. vs. JSON* , um debuggingparameter zu konfigurieren. , Um die Datei zu erstellen. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf eine ausführbare Datei, und wählen Sie **Einstellungen Debuggen und starten** Wählen Sie die Option aus, die dem Projekt am ehesten entspricht, und verwenden Sie dann die folgenden Eigenschaften, um die Konfiguration nach Bedarf zu ändern:

## <a name="default-properties"></a>Standardeigenschaften

||||
|-|-|-|
|**Eigenschaft**|**Typ**|**Beschreibung**|
|`name`|string|Gibt den Namen des Eintrags in der Dropdown Liste "Debugziel" an.|
|`type`|string|Gibt an, ob das Projekt eine DLL oder exe ist (standardmäßig ". exe").|
|`project`|string|Gibt den relativen Pfad zur Projektdatei an.|
|`projectTarget`|string|Gibt das optionale Ziel an, das `project`beim entwickeln aufgerufen wird. Dies `projectTarget` muss bereits vorhanden sein und mit dem Namen in der Dropdown Liste **Debugziel** verglichen werden.|
|`debugType`|string|Gibt den Debugmodus gemäß dem Codetyp an (System eigen, verwaltet oder gemischt). Diese wird automatisch erkannt, es sei denn, dieser Parameter ist festgelegt. Zulässige Werte: "Native", "Managed", "Mixed".|
|`inheritEnvironments`|array|Gibt einen Satz von Umgebungsvariablen an, die von mehreren Quellen geerbt werden. Sie können einige Variablen in Dateien wie "cmakesettings. JSON" oder "cppproperties. JSON" definieren und für den Debugkontext verfügbar machen.|
|`args`|array|Gibt die Befehlszeilenargumente an, die an das gestartete Programm übermittelt werden.|
|`currentDir`|string|Gibt den vollständigen Verzeichnispfad zum Buildziel an. Diese wird automatisch erkannt, es sei denn, dieser Parameter ist festgelegt.|
|`noDebug`|boolean|Gibt an, ob das gestartete Programm debuggt wird. Der Standardwert für diesen Parameter ist `false` , wenn er nicht angegeben ist.|
|`stopOnEntry`|boolean|Gibt an, ob eine nach dem Start des Prozesses und dem Debugger unterbrechen soll. Der Standardwert für diesen Parameter ist `false`.|
|`remoteMachine`|string|Gibt den Namen des Remote Computers an, auf dem das Programm gestartet wird.|
|`env`|array| Gibt eine Schlüssel-Wert-Liste von benutzerdefinierten Umgebungsvariablen an. UMV: {"myeinv": "myVal"}.|
|`portName`|string|Gibt den Namen des Ports beim Anfügen an einen laufenden Prozess an.|
|`buildConfigurations`|array| Ein Schlüssel-Wert-Paar, das den Namen des Buildmodus angibt, auf den die Konfigurationen angewendet werden sollen. Beispielsweise oder `Debug` `Release` und die Konfigurationen, die gemäß dem ausgewählten Buildmodus verwendet werden sollen.

## <a name="c-linux-properties"></a>C++Linux-Eigenschaften

||||
|-|-|-|
|**Eigenschaft**|**Typ**|**Beschreibung**|
|`program`|string|Vollständiger Pfad zur ausführbaren Programmdatei auf dem Remote Computer. Bei Verwendung von cmake kann das `${debugInfo.fullTargetPath}` Makro als Wert für dieses Feld verwendet werden.|
|`processId`|Ganze Zahl|Optionale Prozess-ID, an die der Debugger angefügt werden soll.|
|`sourceFileMap`|Objekt|Optionale Quelldatei Zuordnungen, die an die Debug-Engine übermittelt werden. Format: `{ "\<Compiler source location>": "\<Editor source location>" }` oder `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`. Beispiel: `{ "/home/user/foo": "C:\\foo" }` oder `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`. Siehe [Optionen für die Quelldatei](#source_file_map_options)Zuordnung.|
|`additionalProperties`|string|Eine der sourcefilemapoptions. (Siehe unten.)|
|`MIMode`|string|Gibt den Typ des Mi-fähigen Konsolen Debuggers an, mit dem die midebugengine eine Verbindung herstellt. Zulässige Werte sind "gdb", "lldb".|
|`args`|array|Befehlszeilenargumente, die an das Programm übermittelt werden.|
|`environment`|array|Umgebungsvariablen, die der Umgebung für das Programm hinzugefügt werden sollen. Beispiel: [{"Name": "squid", "Value": "Clam"}].|
|`targetArchitecture`|string|Die Architektur der zu entbuggenden. Diese wird automatisch erkannt, es sei denn, dieser Parameter ist festgelegt. Zulässige Werte sind x86, arm, arm64, mips, x64, amd64, x86_64.|
|`visualizerFile`|string|natvis-Datei, die beim Debuggen dieses Prozesses verwendet werden soll. Diese Option ist nicht kompatibel mit dem globalen gdb-Druck. Wenn Sie diese Einstellung verwenden, sehen Sie "showdisplaystring".|
|`showDisplayString`|boolean|Wenn eine Schnellansicht angegeben wird, aktiviert showdisplaystring die Anzeige Zeichenfolge. Wenn Sie diese Option aktivieren, kann die Leistung beim Debuggen verlangsamt werden.|
|`remoteMachineName`|string|Der Linux-Remote Computer, der gdb hostet, und das zu debuggende Programm. Verwenden Sie den Verbindungs-Manager zum Hinzufügen neuer Linux-Computer. Bei Verwendung von cmake kann das `${debugInfo.remoteMachineName}` Makro als Wert für dieses Feld verwendet werden.|
|`cwd`|string|Das Arbeitsverzeichnis des Ziels auf dem Remote Computer. Bei Verwendung von cmake kann das `${debugInfo.defaultWorkingDirectory}` Makro als Wert für dieses Feld verwendet werden. Der Standardwert ist der Stamm arbeitsbereichstamm, sofern er nicht in der Datei " *CMakeLists. txt* " überschrieben wurde.|
|`miDebuggerPath`|string|Der Pfad zum Mi-aktivierten Debugger (z. b. gdb). Wenn nicht angegeben, wird der Pfad zuerst nach dem Debugger durchsucht.|
|`miDebuggerServerAddress`|string|Die Netzwerkadresse des Mi-fähigen Debugger-Servers, mit dem eine Verbindung hergestellt werden soll. Beispiel: localhost: 1234.|
|`setupCommands`|array|Mindestens ein gdb-/lldb-Befehl, der ausgeführt werden soll, um den zugrunde liegenden Debugger einzurichten. Beispiel: `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]` Siehe [Starten von Setup Befehlen](#launch_setup_commands).|
|`customLaunchSetupCommands`|array|Wenn bereitgestellt, ersetzt dies die Standard Befehle, die zum Starten eines Ziels mit anderen Befehlen verwendet werden. Dies kann z. b. "-target-Attach" sein, um an einen Ziel Prozess anzufügen. Eine leere Befehlsliste ersetzt die Start Befehle durch "Nothing". Dies kann hilfreich sein, wenn dem Debugger Startoptionen als Befehlszeilenoptionen bereitgestellt werden. Beispiel: `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`|
|`launchCompleteCommand`|string|Der Befehl, der ausgeführt werden soll, nachdem der Debugger vollständig eingerichtet ist, damit der Ziel Prozess ausgeführt wird. Zulässige Werte sind "Exec-Run", "Exec-Continue", "None". Der Standardwert ist "Exec-Run".|
|`debugServerPath`|string|Optionaler vollständiger Pfad zum zu startendes debugserver. Der Standardwert ist NULL.|
|`debugServerArgs`|string|Optionale Debug-Server Argumente. Der Standardwert ist NULL.|
|`filterStderr`|boolean|Durchsuchen Sie den stderr-Stream nach dem vom Server gestarteten Muster, und protokollieren Sie stderr, um die Ausgabe Wird standardmäßig auf `false` festgelegt.|
|`coreDumpPath`|string|Optionaler vollständiger Pfad zu einer kerndumpdatei für das angegebene Programm. Der Standardwert ist NULL.|
externalconsole|boolean|True gibt an, dass eine Konsole für die zu debuggende Komponente gestartet wird. Gibt `false`an, dass keine Konsole gestartet wird. Wird standardmäßig auf `false` festgelegt. HINWEIS: Diese Option wird in einigen Fällen aus technischen Gründen ignoriert.|
|`pipeTransport`|string|Wenn dieses Element vorhanden ist, wird der Debugger aufgefordert, eine Verbindung mit einem Remote Computer herzustellen, indem eine andere ausführbare Datei als Pipe verwendet wird, mit der die Standardeingabe/-Ausgabe zwischen Visual Studio und dem Mi-fähigen Debugger (z. b. gdb) Zulässige Werte: eine oder mehrere [Pipe-Transport Optionen](#pipe_transport_options).|


## <a name="launch_setup_commands"></a>Setup Befehle starten

Wird mit der `setupCommands` -Eigenschaft verwendet:

||||
|-|-|-|
|`text`|string|Der auszuführende Debugger-Befehl.|
|`description`|string|Optionale Beschreibung des Befehls.|
|`ignoreFailures`|boolean|True gibt an, dass Fehler vom Befehl ignoriert werden. Wird standardmäßig auf `false` festgelegt.|

## <a name = "pipe_transport_options"></a>Pipe-Transport Optionen

Wird mit der `pipeTransport` -Eigenschaft verwendet:

||||
|-|-|-|
|`pipeCwd`|string|Der voll qualifizierte Pfad zum Arbeitsverzeichnis für das pipeprogramm.|
|`pipeProgram`|string|Der voll qualifizierte Pipe-Befehl, der ausgeführt werden soll.|
|`pipeArgs`|array|Befehlszeilenargumente, die an das pipeprogramm übergeben werden, um die Verbindung zu konfigurieren.|
|`debuggerPath`|string|Der vollständige Pfad zum Debugger auf dem Zielcomputer, z. b./usr/bin/gdb.|
|`pipeEnv`|Objekt|Umgebungsvariablen, die an das pipeprogramm übergeben werden.|
|`quoteArgs`|boolean|Wenn einzelne Argumente Zeichen (z. b. Leerzeichen oder Registerkarten) enthalten, sollte Sie in Anführungszeichen gesetzt werden? Gibt `false`an, dass der Debugger-Befehl nicht mehr automatisch in Anführungszeichen gesetzt wird. Der Standardwert ist `true`.|

## <a name="source_file_map_options"></a>Optionen der Quelldatei Zuordnung

Verwenden Sie mit `sourceFileMap` der-Eigenschaft:

||||
|-|-|-|
|`editorPath`|string|Der Speicherort des Quellcodes, den der Editor finden soll.|
|`useForBreakpoints`|boolean|Beim Festlegen von Breakpoints sollte diese Quell Zuordnung verwendet werden. Wenn `false`der Wert ist, werden nur der Dateiname und die Zeilennummer zum Festlegen von Breakpoints verwendet. Wenn `true`der Wert ist, werden Breakpoints nur mit dem vollständigen Pfad zur Datei und Zeilennummer festgelegt, wenn diese Quell Zuordnung verwendet wird. Andernfalls werden beim Festlegen von Breakpoints nur Dateiname und Zeilennummer verwendet. Der Standardwert ist `true`.|
