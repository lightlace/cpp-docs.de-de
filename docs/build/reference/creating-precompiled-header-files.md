---
title: Erstellen vorkompilierter Headerdateien
ms.date: 11/19/2018
f1_keywords:
- pch
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: b570b76328ee9824610aac495d97cede19189cf9
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176431"
---
# <a name="creating-precompiled-header-files"></a>Erstellen vorkompilierter Headerdateien

Die Microsoft C- und C++-Compiler stellen Optionen für das Vorkompilieren von beliebigem C- oder C++-Code bereit, einschließlich Inlinecode. Mithilfe dieser leistungsstarken Funktion können Sie einen stabilen Codeabschnitt kompilieren, den Code im kompilierten Zustand in einer Datei speichern und bei nachfolgenden Kompilierungen den vorkompilierten Code mit dem noch in Entwicklung befindlichen Code kombinieren. So können nachfolgende Kompilierungen beschleunigt werden, da der bereits stabile Code nicht neu kompiliert werden muss.

Dieses Thema behandelt die folgenden Themen der vorkompilierten Headerdatei:

- [Wann sollte Quellcode vorkompiliert werden?](#when-to-precompile-source-code)

- [Zwei Methoden für das Vorkompilieren von Code](#two-choices-for-precompiling-code)

- [Konsistenzregeln für vorkompilierte Header](#precompiled-header-consistency-rules)

- [Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei](#consistency-rules-for-per-file-use-of-precompiled-headers)

- [Konsistenzregeln für "/ Yc" und "/ Yu"](#consistency-rules-for-yc-and-yu)

- [Verwenden von vorkompilierten Headern in einem Projekt](#using-precompiled-headers-in-a-project)

- [PCH-Dateien im Erstellungsvorgang](#pch-files-in-the-build-process)

- [Beispielmakefile für PCH](#sample-makefile-for-pch)

- [Beispielcode für PCH](#example-code-for-pch)

Referenzinformationen zu den Compileroptionen, die im Zusammenhang mit vorkompilierten Headern finden Sie unter [/y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md).

## <a name="when-to-precompile-source-code"></a>Wann sollte Quellcode vorkompiliert werden?

Vorkompilierter Code ist nützlich während des Entwicklungszyklus, Zeitpunkt der Kompilierung, zu reduzieren, insbesondere dann, wenn:

- Sie verwenden immer eine große Menge von Code, die sich selten ändern.

- Das Programm umfasst mehrere Module, die einen Standardsatz von Include-Dateien und die gleichen Kompilierungsoptionen verwenden. In diesem Fall sind alle Dateien in einem vorkompilierten Header vorkompiliert werden.

Die erste Kompilierung, derjenige, der die vorkompilierte Headerdatei (PCH) erstellt, dauert etwas länger als nachfolgende Kompilierungen. Nachfolgende Kompilierungen können schneller von vorkompilierter Code fortfahren.

Sie können C- und C++-Programme vorkompilieren. In C++-Programmierung ist es üblich, Informationen von Klasse-Schnittstelle in Headerdateien zu trennen. Dieser Header-Dateien können später in Programme enthalten sein, die die Klasse zu verwenden. Durch eine Vorkompilierung diese Header, können Sie die Zeit reduzieren dauert ein Programm um zu kompilieren.

> [!NOTE]
> Obwohl Sie nur eine vorkompilierte Headerdatei (.pch) pro Quelldatei verwenden können, können Sie mehrere PCH-Dateien in einem Projekt verwenden.

## <a name="two-choices-for-precompiling-code"></a>Zwei Methoden für das Vorkompilieren von Code

Mit Visual C++ können Sie jeder C- oder C++-Code Vorkompilieren; Sie sind nicht auf das Vorkompilieren von nur-Header-Dateien beschränkt.

Das Vorkompilieren erfordert Planung, aber es bietet wesentlich schnellere Kompilierungen, wenn Sie Quellcode als einfache Headerdateien vorkompilieren.

Vorkompilieren Sie Code an, wenn Sie wissen, dass die Quelldateien, Headerdateien gemeinsame verwenden, aber Sie sie nicht in der gleichen Reihenfolge schließen oder wenn Sie Quellcode in die Vorkompilierung einbeziehen möchten.

Die Optionen für vorkompilierte Header sind ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md) und [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md). Verwendung **"/ Yc"** einen vorkompilierten Header erstellen. Bei Verwendung mit dem optionalen [Hdrstop](../../preprocessor/hdrstop.md) Pragma **"/ Yc"** können Sie beide Headerdateien vorkompilieren und Quellcode. Wählen Sie **"/ Yu"** auf eine vorhandene vorkompilierte Headerdatei in der vorhandenen Kompilierung verwenden. Sie können auch **/fp** mit der **"/ Yc"** und **"/ Yu"** Optionen, um einen alternativen Namen für die vorkompilierte Headerdatei anzugeben.

Die Compiler-Option-Referenzthemen für **"/ Yu"** und **"/ Yc"** beschrieben, wie diese Funktionalität in der Entwicklungsumgebung zugreifen.

## <a name="precompiled-header-consistency-rules"></a>Konsistenzregeln für vorkompilierte Header

Da PCH-Dateien mit Informationen über die computerumgebung sowie die Arbeitsspeicher-Adressinformationen über das Programm enthält, sollten Sie nur eine PCH-Datei auf dem Computer verwenden, der es erstellt wurde.

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei

Die ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) -Compileroption können Sie angeben, welche PCH-Datei verwendet.

Wenn Sie eine PCH-Datei verwenden, nimmt der Compiler an die gleichen kompilierungsumgebung – konsistente Compileroptionen, Pragmas, usw. verwendet –, die gültig war bei der Erstellung der PCH-Datei, es sei denn, Sie nichts anderes angeben. Wenn der Compiler eine Inkonsistenz erkannt wird, eine Warnung ausgegeben und Inkonsistenzen identifiziert, wenn möglich. Diese Warnungen bedeuten nicht unbedingt ein Problem mit der PCH-Datei; Diese Warnung einfach über mögliche Konflikte. Konsistenzanforderungen für PCH-Dateien werden in den folgenden Abschnitten beschrieben.

### <a name="compiler-option-consistency"></a>Konsistenz von Compileroptionen

Die folgenden Compileroptionen können Sie bei Verwendung einer PCH-Datei eine Inkonsistenz Warnung auslösen:

- Makros, die mit der Präprozessor erstellt (/ D)-Option muss der Kompilierung, die die PCH-Datei erstellt und der aktuellen Kompilierung identisch sein. Der Status der definierten Konstanten nicht aktiviert ist, jedoch zu unvorhersehbaren Ergebnissen können auftreten, wenn diese ändern.

- PCH-Dateien funktionieren nicht mit den Optionen/e "und" / EP.

- PCH-Dateien müssen erstellt werden, verwenden entweder die generieren durchsuchen Informationen (/ FR)-Option oder der lokalen Variablen ausschließen (/ "fr") option, damit nachfolgende Kompilierungen, die die PCH-Datei verwenden, diese Optionen verwenden können.

### <a name="c-70-compatible-z7"></a>C# 7.0-kompatibel (/ Z7)

Wenn diese Option aktiviert ist, wenn die PCH-Datei erstellt wird, können nachfolgende Kompilierungen, die die PCH-Datei verwenden, die Debuginformationen.

Wenn die C# 7.0-kompatibel (/ Z7) Option ist nicht gültig, wenn die PCH-Datei erstellt wird, die nachfolgende Kompilierungen, die PCH-Datei, und "/ Z7" verwenden, eine Warnung ausgelöst. Die Debuginformationen werden in der aktuellen OBJ-Datei, und lokale Symbole in der PCH-Datei definiert sind nicht an den Debugger verfügbar.

### <a name="include-path-consistency"></a>Pfad-Konsistenz einschließen

PCH-Datei enthält keine Informationen zu den Includepfad, die gültig war, wenn es erstellt wurde. Wenn Sie eine PCH-Datei verwenden, verwendet der Compiler immer die Include-Pfad, in der aktuellen Kompilierung angegeben.

### <a name="source-file-consistency"></a>Konsistenz der Source-Datei

Wenn Sie die Option für die vorkompilierte Headerdatei verwenden (/ Yu) angeben, ignoriert der Compiler alle Präprozessordirektiven (einschließlich Pragmas), die im Quellcode angezeigt werden, die vorkompiliert werden soll. Die Kompilierung durch solche Präprozessordirektiven angegeben muss identisch mit der Kompilierung für die vorkompilierte Headerdatei erstellen (/ Yc)-Option verwendet werden.

### <a name="pragma-consistency"></a>Pragma-Konsistenz

Pragmas, die in der Regel während der Erstellung einer PCH-Datei verarbeitet Auswirkungen auf die Datei mit der später die PCH-Datei verwendet wird. Die `comment` und `message` Pragmas wirken sich nicht auf den Rest der Kompilierung.

Diese Pragmas beeinflussen nur den Code in die PCH-Datei; Sie haben keine Auswirkungen auf Code, der anschließend die PCH-Datei verwendet:

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

Diese Pragmas, die als Teil eines vorkompilierten Headers beibehalten werden und Auswirkungen auf den Rest der Kompilierung, die in der vorkompilierten Headerdatei verwendet:

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>Konsistenzregeln für "/Yc" und "/Yu"

Bei Verwendung ein vorkompiliertes Headers, der mit "/ Yc" oder "/ Yu" erstellt, vergleicht der Compiler der aktuellen kompilierungsumgebung demjenigen, den vorhanden waren, als Sie die PCH-Datei erstellt. Achten Sie darauf, um eine Umgebung, die konsistent mit dem vorherigen Beispiel (mit konsistenten Compileroptionen, Pragmas, usw.) für die aktuelle Kompilierung anzugeben. Wenn der Compiler eine Inkonsistenz erkannt wird, eine Warnung ausgegeben und Inkonsistenzen identifiziert, wenn möglich. Diese Warnungen angeben nicht unbedingt ein Problem mit der PCH-Datei; Diese Warnung einfach über mögliche Konflikte. In den folgenden Abschnitten wird erläutert, die konsistenzanforderungen für vorkompilierte Header.

### <a name="compiler-option-consistency"></a>Konsistenz von Compileroptionen

Diese Tabelle enthält die Compileroptionen, die eine Inkonsistenz Warnung auslösen könnte, wenn Sie einen vorkompilierten Header verwenden:

|Option|name|Regel|
|------------|----------|----------|
|/D|Definieren von Konstanten und Makros|Zwischen der Kompilierung, die Erstellen des vorkompilierten Headers und der aktuellen Kompilierung identisch sein muss. Der Status der definierten Konstanten nicht aktiviert ist, jedoch zu unvorhersehbaren Ergebnissen können auftreten, wenn Ihre Dateien auf den Werten der Konstanten geänderten abhängig sind.|
|/ E "oder" / EP|Kopieren der Präprozessorausgabe in die Standardausgabe|Vorkompilierte Header funktionieren nicht mit der Option/e "oder" / EP.|
|/ FR oder/fr|Microsoft Source Browserinformationen generieren|Für die Optionen "/ fr und/fr" mit der Option "/ Yu" gültig ist müssen sie in Kraft bereits haben als die vorkompilierte Header erstellt wurde. Nachfolgende Kompilierungen, die Verwendung des vorkompilierten Headers generieren auch Quellbrowser Informationen. Browserinformationen in einer einzelnen SBR-Datei befindet und von anderen Dateien verwiesen wird, auf die gleiche Weise wie CodeView-Informationen. Die Platzierung von Browserinformationen Quelle kann nicht überschrieben werden.|
|/ GA, / GD, / ge, "/ GW" oder "/ GW"|Windows-Protokoll-Optionen|Zwischen der Kompilierung, die Erstellen des vorkompilierten Headers und der aktuellen Kompilierung identisch sein muss. Wenn diese Optionen unterscheiden, führt eine Warnmeldung angezeigt.|
|/ZI|Vollständige Debuginformationen generieren|Wenn diese Option aktiviert ist, wenn der vorkompilierte Header erstellt wird, können nachfolgende Kompilierungen, die die Vorkompilierung zu verwenden, Informationen zum Debuggen verwenden. Wenn "/ Zi" nicht aktiviert ist, wenn der vorkompilierte Header erstellt wird, wird eine Warnung von Kompilierungen, die verwenden die Vorkompilierung sowie die Option "/ Zi" ausgelöst. Die Debuginformationen in der aktuellen Objektdatei platziert wird, und in der vorkompilierten Headerdatei definierte lokale Symbole sind nicht an den Debugger verfügbar.|

> [!NOTE]
>  Die vorkompilierte Header-Funktion dient nur in C und C++-Quelldateien.

## <a name="using-precompiled-headers-in-a-project"></a>Verwenden von vorkompilierten Headern in einem Projekt

Frühere Abschnitte enthalten eine Übersicht über vorkompilierte Header: "/ Yc" und "/ Yu" die Option/fp und [Hdrstop](../../preprocessor/hdrstop.md) Pragma. In diesem Abschnitt wird beschrieben, eine Methode für die manuellen Optionen für vorkompilierte Header in einem Projekt verwenden; Es endet mit einer Beispiel-Makefile und den Code, den er verwaltet.

Sehen Sie sich für einen anderen Ansatz verwenden Sie die manuellen Optionen für vorkompilierte Header in einem Projekt den Makefiles MFC\SRC im Verzeichnis, das bei der Standardinstallation von Visual C++ erstellt wird. Diese Makefiles nehmen einen ähnlichen Ansatz, mit dem in diesem Abschnitt dargestellt, aber stärkerer Einsatz der Microsoft Program Maintenance Utility (NMAKE) Makros und bieten mehr Kontrolle des Buildprozesses.

## <a name="pch-files-in-the-build-process"></a>PCH-Dateien im Erstellungsvorgang

Die Codebasis eines Softwareprojekts ist in mehrere C oder C++-Quelldateien, Objektdateien, Bibliotheken und Headerdateien in der Regel enthalten. Makefile-Koordinaten in der Regel die Kombination dieser Elemente in eine ausführbare Datei. Die folgende Abbildung zeigt die Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet. Die Namen der NMAKE-Makros und die Dateinamen in diesem Diagramm sind konsistent zu denjenigen sind im Beispielcode finden Sie im [Beispielmakefile für PCH](#sample-makefile-for-pch) und [Beispielcode für PCH](#example-code-for-pch).

In der Abbildung verwendet drei DSL-Geräte, um den Fluss des Buildprozesses anzuzeigen. Jede Datei bzw. das Makro die benannt werden Rechtecke darstellen. die drei Makros stellen eine oder mehrere Dateien dar. Schattierte Flächen darstellen, jede Kompilier- oder Aktion. Pfeile zeigen, welche Dateien und Makros während der Kompilierung oder Verknüpfungsvorgang kombiniert werden.

![Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet](../../build/reference/media/vc30ow1.gif "Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet") <br/>
Struktur eines Makefiles, das eine vorkompilierte Headerdatei verwendet

Am oberen Rand der Abbildung befinden sich sowohl STABLEHDRS und ist NMAKE-Makros, die in denen Sie Dateien, die wahrscheinlich nicht benötigen eine Neukompilierung aufgelistet. Diese Dateien werden durch die Befehlszeichenfolge kompiliert.

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

nur, wenn die vorkompilierte Headerdatei (STABLE.pch) nicht vorhanden ist oder wenn Sie Änderungen an Dateien vornehmen, die in die beiden Makros aufgelistet werden. In beiden Fällen enthält die vorkompilierten Header-Datei Code nur aus den Dateien in das Makro STABLEHDRS aufgelistet. Führen Sie die letzte Datei, in das Makro ist vorkompiliert werden soll.

Die Dateien, die Sie in diesen Makros auflisten können entweder "Headerdateien" oder "C oder C++-Quelldateien sein. (Eine einzelne PCH-Datei kann nicht mit C und C++ Module verwendet werden.) Beachten Sie, mit denen Sie die **Hdrstop** Makro zum Beenden der Vorkompilierung an einem bestimmten Punkt in der Datei ist. Finden Sie unter [Hdrstop](../../preprocessor/hdrstop.md) für Weitere Informationen.

Im Diagramm abwärts APPLIB.obj die stellt Unterstützungscode dar, die in der fertigen Anwendung verwendet. Sie wird aus APPLIB.cpp erstellt, die Dateien in das Makro UNSTABLEHDRS aufgeführt und vorkompiliertem Code aus dem vorkompilierten Header.

MYAPP.obj stellt die endgültige Anwendung dar. Sie wird aus MYAPP.cpp erstellt, die Dateien in das Makro UNSTABLEHDRS aufgeführt und vorkompiliertem Code aus dem vorkompilierten Header.

Zum Schluss die ausführbare Datei ("MyApp". EXE-Datei) wird durch die aufgelisteten Dateien in der OBJ-Dateien-Makro (APPLIB.obj und MYAPP.obj) erstellt.

## <a name="sample-makefile-for-pch"></a>Beispielmakefile für PCH

Das folgende Makefile verwendet Makros und ein! IF! #ELSE! ENDIF-flusssteuerung-Befehl-Struktur, die die Anpassung an das Projekt zu vereinfachen.

```NMAKE
# Makefile : Illustrates the effective use of precompiled
#            headers in a project
# Usage:     NMAKE option
# option:    DEBUG=[0|1]
#            (DEBUG not defined is equivalent to DEBUG=0)
#
OBJS = myapp.obj applib.obj
# List all stable header files in the STABLEHDRS macro.
STABLEHDRS = stable.h another.h
# List the final header file to be precompiled here:
BOUNDRY = stable.h
# List header files under development here:
UNSTABLEHDRS = unstable.h
# List all compiler options common to both debug and final
# versions of your code here:
CLFLAGS = /c /W3
# List all linker options common to both debug and final
# versions of your code here:
LINKFLAGS = /NOD /ONERROR:NOEXE
!IF "$(DEBUG)" == "1"
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f
LINKFLAGS = $(LINKFLAGS) /COD
LIBS      = slibce
!ELSE
CLFLAGS   = $(CLFLAGS) /Oselg /Gs
LINKFLAGS = $(LINKFLAGS)
LIBS      = slibce
!ENDIF
myapp.exe: $(OBJS)
    link $(LINKFLAGS) @<<
$(OBJS), myapp, NUL, $(LIBS), NUL;
<<
# Compile myapp
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp
# Compile applib
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp
# Compile headers
stable.pch : $(STABLEHDRS)
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp
```

Abgesehen von den STABLEHDRS ist und UNSTABLEHDRS Makros, die in der Abbildung "Struktur von ein Makefile, verwendet eine vorkompilierte Headerdatei" dargestellt wird, [PCH-Dateien im Erstellungsvorgang](#pch-files-in-the-build-process), dieses Makefile bietet ein CLFLAGS-Makro und ein LINKFLAGS -Makro. Sie müssen diese Makros verwenden, um aufzulisten, Compiler- und Linkeroptionen, die angewendet werden, ob eine Debug- oder endgültige Version der ausführbaren Datei der Anwendung erstellt werden. Darüber hinaus wird ein Makro BIBLIOTHEKEN, in dem Sie die Bibliotheken Ihrem Projekt ist erforderlich.

Das Makefile verwendet auch! IF! #ELSE! ENDIF, um festzustellen, ob Sie über ein DEBUG-Symbol in der Befehlszeile NMAKE definieren:

```NMAKE
NMAKE DEBUG=[1|0]
```

Dieses Feature ermöglicht es für Sie mit der gleichen Makefile während der Entwicklung und für die endgültigen Versionen des Programms – verwenden Sie DEBUG = 0 für die endgültigen Versionen. Die folgenden Befehlszeilen sind gleichwertig:

```NMAKE
NMAKE
NMAKE DEBUG=0
```

Weitere Informationen zu Makefiles finden Sie unter [NMAKE-Referenz](../../build/nmake-reference.md). Siehe auch [Compileroptionen](../../build/reference/compiler-options.md) und [Optionen des Linkers](../../build/reference/linker-options.md).

## <a name="example-code-for-pch"></a>Beispielcode für PCH

Die folgenden Quelldateien werden verwendet, in dem beschriebenen Makefile [PCH-Dateien im Erstellungsvorgang](#pch-files-in-the-build-process) und [Beispielmakefile für PCH](#sample-makefile-for-pch). Beachten Sie, dass die Kommentare wichtige Informationen enthalten.

```cpp
// ANOTHER.H : Contains the interface to code that is not
//             likely to change.
//
#ifndef __ANOTHER_H
#define __ANOTHER_H
#include<iostream>
void savemoretime( void );
#endif // __ANOTHER_H
```

```cpp
// STABLE.H : Contains the interface to code that is not likely
//            to change. List code that is likely to change
//            in the makefile's STABLEHDRS macro.
//
#ifndef __STABLE_H
#define __STABLE_H
#include<iostream>
void savetime( void );
#endif // __STABLE_H
```

```cpp
// UNSTABLE.H : Contains the interface to code that is
//              likely to change. As the code in a header
//              file becomes stable, remove the header file
//              from the makefile's UNSTABLEHDR macro and list
//              it in the STABLEHDRS macro.
//
#ifndef __UNSTABLE_H
#define __UNSTABLE_H
#include<iostream.h>
void notstable( void );
#endif // __UNSTABLE_H
```

```cpp
// APPLIB.CPP : This file contains the code that implements
//              the interface code declared in the header
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
// The following code represents code that is deemed stable and
// not likely to change. The associated interface code is
// precompiled. In this example, the header files STABLE.H and
// ANOTHER.H are precompiled.
void savetime( void )
    { cout << "Why recompile stable code?\n"; }
void savemoretime( void )
    { cout << "Why, indeed?\n\n"; }
// The following code represents code that is still under
// development. The associated header file is not precompiled.
void notstable( void )
    { cout << "Unstable code requires"
            << " frequent recompilation.\n";
    }
```

```cpp
// MYAPP.CPP : Sample application
//             All precompiled code other than the file listed
//             in the makefile's BOUNDRY macro (stable.h in
//             this example) must be included before the file
//             listed in the BOUNDRY macro. Unstable code must
//             be included after the precompiled code.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
int main( void )
{
    savetime();
    savemoretime();
    notstable();
}
```

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)