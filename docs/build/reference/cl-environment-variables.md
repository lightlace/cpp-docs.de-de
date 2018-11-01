---
title: CL-Umgebungsvariablen
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 4c9643e977c707f7e7fd99ccc48d0475e2dc7837
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535772"
---
# <a name="cl-environment-variables"></a>CL-Umgebungsvariablen

Das CL-Tool verwendet die folgenden Umgebungsvariablen:

- CL und \_CL\_, wenn definiert. Das CL-Tool voran, die Optionen und Argumente, die definiert, in der CL-Umgebungsvariablen auf die Befehlszeilenargumente und fügt die Optionen und Argumente definiert \_CL\_, vor der Verarbeitung.

- INCLUDE: Hierbei muss es sich um den Punkt zu Ihrem „\include“-Unterverzeichnis Ihrer Visual C++-Installation handeln.

- LIBPATH, die Verzeichnisse für die Suche nach Metadatendateien mit referenzierte gibt [#using](../../preprocessor/hash-using-directive-cpp.md). Weitere Informationen über LIBPATH finden Sie unter `#using`.

Sie können festlegen, den CL oder \_CL\_ Umgebungsvariable, die mit der folgenden Syntax:

> Legen Sie CL = [[*Option*]... [*Datei*]...] [/ link *Link-opt* ...] Legen Sie \_CL\_= [[*Option*]... [*Datei*]...] [/ link *Link-opt* ...]

Weitere Informationen zu den Argumenten der CL und \_CL\_ Umgebungsvariablen finden Sie unter [Compiler Command-Line Syntax](../../build/reference/compiler-command-line-syntax.md).

Sie können diese Umgebungsvariablen verwenden, um die Dateien und Optionen zu definieren, die Sie am häufigsten verwenden. Zudem können Sie die Befehlszeile verwenden, um bestimmte Dateien und Optionen für bestimmte Zwecke zu definieren. Die CL und \_CL\_ Umgebungsvariablen sind auf 1024 Zeichen (die Begrenzung für die Befehlszeileneingabe) beschränkt.

Sie können nicht die Option „/D“ zum Definieren eines Symbols verwenden, welches das Gleichheitszeichen (=) verwendet. Sie können das Nummernzeichen (#) für ein Gleichheitszeichen ersetzen. Auf diese Weise können Sie die CL oder \_CL\_ Umgebungsvariablen zum Definieren von Präprozessorkonstanten mit expliziten Werten – z. B. `/DDEBUG#1` definieren `DEBUG=1`.

Weitere Informationen finden Sie unter [Festlegen von Umgebungsvariablen](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Beispiele

Im folgenden finden ein Beispiel für die CL-Umgebungsvariable festlegen:

> Legen Sie CL = / Zp2/Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ

Wenn diese Umgebungsvariable festgelegt ist, wenn Sie eingeben `CL INPUT.C` in der Befehlszeile, die dies ist der effektive Befehl:

> CL /Zp2/Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ-EINGABE. C

Im folgenden Beispiel wird verursacht, dass ein unformatierter CL-Befehl die Quelldateien „FILE1.c“ und „FILE2.c“ kompiliert. Anschließend werden die Objektdateien „FILE1.obj“, „FILE2.obj“ und „FILE3.obj“ verknüpft.

> SET-CL = "FILE1". C-DATEI2. C-SATZ \_CL\_DATEI3 =. OBJ-CL

Dies hat den gleichen Effekt wie der Code in der folgenden Befehlszeile:

> CL "FILE1". C-DATEI2. C-DATEI3. OBJ

## <a name="see-also"></a>Siehe auch

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)
