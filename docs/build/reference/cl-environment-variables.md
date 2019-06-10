---
title: CL-Umgebungsvariablen
ms.date: 06/06/2019
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 0f7930728ef1bf6bea50c4388d52d30c569a8795
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821535"
---
# <a name="cl-environment-variables"></a>CL-Umgebungsvariablen

Das CL-Tool verwendet die folgenden Umgebungsvariablen:

- CL und \_CL_, falls definiert. Das CL-Tool voran, die Optionen und Argumente, die definiert, in der CL-Umgebungsvariablen auf die Befehlszeilenargumente und fügt die Optionen und Argumente definiert \_CL_, vor der Verarbeitung.

- EINZUSCHLIEßEN Sie, muss auf das Unterverzeichnis \include"-Unterverzeichnis Ihrer Visual Studio-Installation verweisen.

- LIBPATH, die Verzeichnisse für die Suche nach Metadatendateien mit referenzierte gibt [#using](../../preprocessor/hash-using-directive-cpp.md). Weitere Informationen über LIBPATH finden Sie unter [#using](../../preprocessor/hash-using-directive-cpp.md).

Sie können festlegen, den CL oder \_CL_-Umgebungsvariable, die mit der folgenden Syntax:

> Legen Sie CL = [[*Option*]... [*Datei*]...] [/ link *Link-opt* ...] \
> Legen Sie \_CL\_= [[*Option*]... [*Datei*]...] [/ link *Link-opt* ...]

Weitere Informationen zu den Argumenten der CL und \_CL_ Umgebungsvariablen finden Sie unter [MSVC-Compiler Command-Line Syntax](compiler-command-line-syntax.md).

Sie können diese Umgebungsvariablen verwenden, definieren Sie die Dateien und Optionen, die Sie am häufigsten verwenden. Klicken Sie dann verwenden Sie die Befehlszeile, um weitere Dateien und Optionen auf CL für bestimmte Zwecke zu gewähren. Die CL und \_CL_-Umgebungsvariablen sind auf 1024 Zeichen (die Begrenzung für die Befehlszeileneingabe) beschränkt.

Sie können keine der [/d](d-preprocessor-definitions.md) Option aus, um ein Symbol definieren, die ein Gleichheitszeichen verwendet ( **=** ). Sie können stattdessen die Nummernzeichen ( **#** ) für ein Gleichheitszeichen. Auf diese Weise können Sie die CL oder \_CL_ Umgebungsvariablen zum Definieren von Präprozessorkonstanten mit expliziten Werten – z. B. `/DDEBUG#1` definieren `DEBUG=1`.

Weitere Informationen finden Sie unter [Festlegen von Umgebungsvariablen](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Beispiele

Der folgende Befehl ist ein Beispiel für die CL-Umgebungsvariable festlegen:

> Legen Sie CL = / Zp2/Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ

Wenn CL-Umgebungsvariable festgelegt ist, wenn Sie eingeben `CL INPUT.C` in der Befehlszeile wird der effektive Befehl:

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

Im folgenden Beispiel wird verursacht, dass ein unformatierter CL-Befehl die Quelldateien „FILE1.c“ und „FILE2.c“ kompiliert. Anschließend werden die Objektdateien „FILE1.obj“, „FILE2.obj“ und „FILE3.obj“ verknüpft.

> SET-CL = "FILE1". C-DATEI2. C \
> LEGEN SIE \_CL_ DATEI3 =. OBJ \
> CL

Diese Umgebungsvariablen stellen den Aufruf von CL, die die gleiche Wirkung hat wie die folgende Befehlszeile:

> CL "FILE1". C-DATEI2. C-DATEI3. OBJ

## <a name="see-also"></a>Siehe auch

[Festlegen von Compileroptionen](compiler-command-line-syntax.md) \
[MSVC-Compileroptionen](compiler-options.md)
