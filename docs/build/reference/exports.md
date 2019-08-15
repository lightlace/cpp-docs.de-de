---
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: 8338f27d35d3779a55b83b70c7a3eef285a91f46
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492886"
---
# <a name="exports"></a>EXPORTS

Führt einen Abschnitt mit mindestens einer Exportdefinition ein, die die exportierten Namen oder Ordinalzahlen von Funktionen oder Daten angibt. Jede Definition muss sich in einer separaten Zeile befinden.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>Hinweise

Die erste *Definition* kann sich in derselben Zeile wie das `EXPORTS` -Schlüsselwort oder in einer nachfolgenden Zeile befinden. Die .DEF-Datei kann eine oder mehrere `EXPORTS`-Anweisungen enthalten.

Die Syntax für eine Export *Definition* lautet wie folgt:

> *entryname*\[internal_name other_module. exported_name] \[ _Ordnungszahl Noname_ ] ]\[ **\@** | __=__ \[ \[ **Privat**] | **Daten]** ] \[

*entryname* ist der Funktions-oder Variablenname, den Sie exportieren möchten. Dieser ist erforderlich. Wenn der Name, den Sie exportieren, vom Namen in der DLL abweicht, geben Sie den Namen des Exports in der DLL mit *internal_name*an. Wenn Ihre DLL beispielsweise eine Funktion `func1` exportiert und Sie möchten, dass Aufrufer sie als `func2` verwenden, würden Sie Folgendes angeben:

```DEF
EXPORTS
   func2=func1
```

Wenn der Name, den Sie exportieren, aus einem anderen Modul besteht, geben Sie den Namen des Exports in der DLL mithilfe von *other_module. exported_name*an. Wenn Ihre DLL beispielsweise eine Funktion `other_module.func1` exportiert und Sie möchten, dass Aufrufer sie als `func2` verwenden, würden Sie Folgendes angeben:

```DEF
EXPORTS
   func2=other_module.func1
```

Wenn der Name, den Sie exportieren, von einem anderen Modul verwendet wird, das nach Ordinalzahlen exportiert, geben Sie die Ordinalzahl des Exports in der DLL mit *other_module*an. *Ordinalzahl.* __#__ Wenn Ihre DLL z. b. eine Funktion aus dem anderen Modul exportiert, in dem Sie Ordnungszahl 42 ist, und Sie möchten, dass `func2`Aufrufer Sie als verwenden, geben Sie Folgendes an:

```DEF
EXPORTS
   func2=other_module.#42
```

Da der MSVC-Compiler die namens Ergänzung C++ für Funktionen verwendet, müssen Sie entweder den ergänzten Namen *internal_name* verwenden oder die exportierten `extern "C"` Funktionen mithilfe von im Quellcode definieren. Der Compiler ergänzt auch C-Funktionen, die die [__stdcall](../../cpp/stdcall.md) -Aufruf Konvention mit einem unter\_Strich ()-Präfix verwenden, und ein Suffix\@, das aus dem @-Zeichen () gefolgt von der Anzahl der Bytes (in dezimal) in der Argumentliste besteht.

Um die vom Compiler erstellten ergänzten Namen zu finden, verwenden Sie das [DUMPBIN](dumpbin-reference.md) -Tool oder die [/map](map-generate-mapfile.md) -Option Linker. Die ergänzten Namen sind compilerspezifisch. Wenn Sie die ergänzten Namen in der .DEF-Datei exportieren, müssen die ausführbaren Dateien, die zur DLL verknüpfen, ebenfalls mit derselben Version des Compilers erstellt werden. Damit wird sichergestellt, dass die ergänzten Namen im Aufrufer den exportierten Namen in der .DEF-Datei entsprechen.

Sie können \@ *Ordnungszahl* verwenden, um anzugeben, dass eine Zahl und nicht der Funktionsname in die Export Tabelle der dll übergeht. Viele Windows-DLLs exportieren Ordinalzahlen, um Legacycode zu unterstützen. Es war üblich, Ordinalzahlen in 16-Bit-Windows-Code zu verwenden, weil das dazu beitragen kann, die Größe einer DLL zu minimieren. Es wird nicht empfohlen, Funktionen anhand der Ordinalzahl zu exportieren, es sei denn, die Clients Ihrer DLL benötigen sie zur Legacyunterstützung. Da die .LIB-Datei die Zuordnung zwischen der Ordinalzahl und der Funktion enthält, können Sie den Funktionsnamen verwenden, wie Sie es normalerweise in Projekten tun würden, die die DLL verwenden.

Mithilfe des optionalen **Noname** -Schlüssel Worts können Sie nur nach Ordinalzahl exportieren und die Größe der Export Tabelle in der resultierenden DLL verringern. Wenn Sie jedoch [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) in der DLL verwenden möchten, müssen Sie die Ordnungszahl kennen, da der Name nicht gültig ist.

Das optionale Schlüsselwort **private** verhindert, dass *entryname* in der Import Bibliothek enthalten ist, die von Link generiert wird. Es wirkt sich nicht auf den Export des ebenfalls von LINK generierten Image aus.

Die optionalen Schlüsselwort **Daten** geben an, dass ein Exportdaten und nicht Code ist. Das folgende Beispiel zeigt, wie Sie eine Datenvariable namens `exported_global` exportieren könnten:

```DEF
EXPORTS
   exported_global DATA
```

Es gibt vier Möglichkeiten für das Exportieren einer Definition, aufgelistet in empfohlener Reihenfolge:

1. Das Schlüsselwort [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) im Quellcode

1. Eine `EXPORTS`-Anweisung in einer .DEF-Datei

1. Eine [/Export](export-exports-a-function.md) -Spezifikation in einem Link Befehl

1. Eine [comment](../../preprocessor/comment-c-cpp.md) -Anweisung im Quellcode der Form `#pragma comment(linker, "/export: definition ")`. Das folgende Beispiel zeigt eine #pragma comment-Direktive vor einer Funktionsdeklaration, wobei `PlainFuncName` der nicht ergänzte Name und `_PlainFuncName@4` der ergänzte Name der Funktion ist:

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

Die #pragma-Direktive ist nützlich, wenn Sie einen nicht ergänzten Funktionsnamen exportieren müssen und abhängig von der Buildkonfiguration unterschiedliche Exporte aufweisen müssen (z. b. in 32-Bit-oder 64-Bit-Builds).

Alle vier Methoden können im selben Programm verwendet werden. Wenn LINK ein Programm erstellt, das Exporte enthält, wird auch eine Importbibliothek erstellt, es sei denn, im Build wird eine .EXP-Datei verwendet.

Hier ist ein Beispiel für einen EXPORTS-Abschnitt:

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

Wenn Sie eine Variable aus einer DLL über dien .DEF-Datei exportieren, müssen Sie `__declspec(dllexport)` nicht in der Variable angeben. Sie müssen jedoch in jeder Datei, die die DLL verwendet, immer noch `__declspec(dllimport)` in der Deklaration der Daten verwenden.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](rules-for-module-definition-statements.md)
