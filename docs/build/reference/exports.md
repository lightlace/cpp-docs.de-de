---
title: EXPORTE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- EXPORTS
dev_langs:
- C++
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf350b0a129c642678fc6af1bac7d35633fe909
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860978"
---
# <a name="exports"></a>EXPORTS

Führt einen Abschnitt mit mindestens einer Exportdefinition ein, die die exportierten Namen oder Ordinalzahlen von Funktionen oder Daten angibt. Jede Definition muss sich in einer separaten Zeile befinden.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>Hinweise

Die erste *Definition* auf derselben Zeile wie möglich die `EXPORTS` Schlüsselwort oder in einer nachfolgenden Zeile. Die .DEF-Datei kann eine oder mehrere `EXPORTS`-Anweisungen enthalten.

Die Syntax für einen Export *Definition* ist:

> *Eintragsname*\[__=__*Internal_name*|*other_module.exported_name*] \[ **\@** _ordinal_ \[ **NONAME**]] \[ \[ **PRIVATE**] | \[ **Daten**]]

*Eintragsname* ist der Name der Funktion oder Variable, die Sie exportieren möchten. Dieser ist erforderlich. Wenn der Name, den Sie exportieren, aus dem Namen in der DLL unterscheidet, geben Sie den Namen des Exports in der DLL mit *Internal_name*. Wenn Ihre DLL beispielsweise eine Funktion `func1` exportiert und Sie möchten, dass Aufrufer sie als `func2` verwenden, würden Sie Folgendes angeben:

```DEF
EXPORTS
   func2=func1
```

Wenn der Name, den Sie exportieren aus einem anderen Modul ist, geben Sie den Namen des Exports in der DLL mit *other_module.exported_name*. Wenn Ihre DLL beispielsweise eine Funktion `other_module.func1` exportiert und Sie möchten, dass Aufrufer sie als `func2` verwenden, würden Sie Folgendes angeben:

```DEF
EXPORTS
   func2=other_module.func1
```

Ist der Name, den Sie exportieren aus einem anderen Modul, die anhand der Ordinalzahl exportieren, geben Sie der Export die Ordnungszahl in der DLL können Sie mit *Other_module*.__#__ *ordinal*. Angenommen, Ihre DLL-Exporte eine Funktion aus dem anderen Modul, in denen ordinal 42, und Sie Aufrufern die Verwendung als `func2`, würden Sie angeben:

```DEF
EXPORTS
   func2=other_module.#42
```

Da Visual C++-Compiler die namensergänzung für C++-Funktionen verwendet, müssen Sie entweder die ergänzten Namen verwenden *Internal_name* oder definieren Sie die exportierten Funktionen mithilfe von `extern "C"` im Quellcode. Der Compiler ergänzt auch C-Funktionen, mit denen die [__stdcall](../../cpp/stdcall.md) -Aufrufkonvention mit einem Unterstrich (\_) Präfix und einem Suffix bestehen die at-Zeichen (\@) gefolgt von der Anzahl von Bytes (als Dezimalzahl) in der Argumentliste.

Um die vom Compiler erzeugten, ergänzten Namen zu suchen, verwenden die [DUMPBIN](../../build/reference/dumpbin-reference.md) Tool oder den Linker [/MAP](../../build/reference/map-generate-mapfile.md) Option. Die ergänzten Namen sind compilerspezifisch. Wenn Sie die ergänzten Namen in der .DEF-Datei exportieren, müssen die ausführbaren Dateien, die zur DLL verknüpfen, ebenfalls mit derselben Version des Compilers erstellt werden. Damit wird sichergestellt, dass die ergänzten Namen im Aufrufer den exportierten Namen in der .DEF-Datei entsprechen.

Sie können \@ *ordinal* um anzugeben, dass eine Zahl und nicht der Funktionsname wird in der Exporttabelle der. Viele Windows-DLLs exportieren Ordinalzahlen, um Legacycode zu unterstützen. Es war üblich, Ordinalzahlen in 16-Bit-Windows-Code zu verwenden, weil das dazu beitragen kann, die Größe einer DLL zu minimieren. Es wird nicht empfohlen, Funktionen anhand der Ordinalzahl zu exportieren, es sei denn, die Clients Ihrer DLL benötigen sie zur Legacyunterstützung. Da die .LIB-Datei die Zuordnung zwischen der Ordinalzahl und der Funktion enthält, können Sie den Funktionsnamen verwenden, wie Sie es normalerweise in Projekten tun würden, die die DLL verwenden.

Mithilfe des optionalen **NONAME** -Schlüsselwort, Sie können nur anhand der Ordinalzahl exportieren und die Größe der Exporttabelle in der resultierenden DLL reduzieren. Allerdings sollten Sie verwenden [GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) in der DLL, müssen Sie die Ordinalzahl kennen, da der Name nicht gültig ist.

Das optionale Schlüsselwort **PRIVATE** wird verhindert, dass *Eintragsname* aus, die in der von LINK generierte Importbibliothek eingeschlossen wird. Es wirkt sich nicht auf den Export des ebenfalls von LINK generierten Image aus.

Das optionale Schlüsselwort **Daten** gibt an, dass ein Export Daten und keinen Code. Das folgende Beispiel zeigt, wie Sie eine Datenvariable namens `exported_global` exportieren könnten:

```DEF
EXPORTS
   exported_global DATA
```

Es gibt vier Möglichkeiten für das Exportieren einer Definition, aufgelistet in empfohlener Reihenfolge:

1. Die [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) Schlüsselwort im Quellcode

1. Eine `EXPORTS`-Anweisung in einer .DEF-Datei

1. Ein [/EXPORT](../../build/reference/export-exports-a-function.md) Spezifikation in einem LINK-Befehl

1. Ein [Kommentar](../../preprocessor/comment-c-cpp.md) -Anweisung im Quellcode, der das Formular `#pragma comment(linker, "/export: definition ")`. Das folgende Beispiel zeigt eine #pragma Comment-Anweisung vor der Deklaration einer Funktion, in denen `PlainFuncName` ist von der nicht ergänzte Namen, und `_PlainFuncName@4` ist der ergänzte Name der Funktion:

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#Pragma-Direktive ist nützlich, wenn Sie müssen einen nicht ergänzten Funktionsnamen exportieren und anderen Exporte abhängig von der Buildkonfiguration (z. B. in 32-Bit oder 64-Bit-Builds).

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

[Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)
