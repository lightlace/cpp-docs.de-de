---
title: CL-Umgebungsvariablen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f3986097bcb5028d9ad708c9a3132f5e417d502
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cl-environment-variables"></a>CL-Umgebungsvariablen

Das CL-Tool verwendet die folgenden Umgebungsvariablen:

- CL und \_CL\_, falls definiert. Das CL-Tool stellt die Optionen und Argumente, die in der CL-Umgebungsvariablen für die Befehlszeilenargumente definierten voran, und fügt die Optionen und Argumente definiert, \_CL\_, vor der Verarbeitung.

- INCLUDE: Hierbei muss es sich um den Punkt zu Ihrem „\include“-Unterverzeichnis Ihrer Visual C++-Installation handeln.

- LIBPATH: Gibt Verzeichnisse zum Suchen nach Metadatendateien mit verwiesen an [#using](../../preprocessor/hash-using-directive-cpp.md). Weitere Informationen über LIBPATH finden Sie unter `#using`.

Sie können festlegen, dass die CL oder \_CL\_ Umgebungsvariable, die mithilfe der folgenden Syntax:

> Legen Sie CL = [[*Option*]... [*Datei*]...] [/ link *Link-opt* ...]  
> Legen Sie \_CL\_= [[*Option*]... [*Datei*]...] [/ link *Link-opt* ...]

Weitere Informationen zu den Argumenten CL und \_CL\_ Umgebungsvariablen finden Sie unter [Compiler Befehlszeilensyntax](../../build/reference/compiler-command-line-syntax.md).

Sie können diese Umgebungsvariablen verwenden, um die Dateien und Optionen zu definieren, die Sie am häufigsten verwenden. Zudem können Sie die Befehlszeile verwenden, um bestimmte Dateien und Optionen für bestimmte Zwecke zu definieren. Das CL und \_CL\_ Umgebungsvariablen sind auf 1024 Zeichen (Begrenzung für die Befehlszeileneingabe) beschränkt.

Sie können nicht die Option „/D“ zum Definieren eines Symbols verwenden, welches das Gleichheitszeichen (=) verwendet. Sie können das Nummernzeichen (#) für ein Gleichheitszeichen ersetzen. Auf diese Weise können Sie die CL oder \_CL\_ Umgebungsvariablen zum Definieren von Präprozessorkonstanten mit expliziten Werten – z. B. `/DDEBUG#1` definieren `DEBUG=1`.

Weitere Informationen finden Sie unter [Festlegen von Umgebungsvariablen](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Beispiele

Im folgenden finden ein Beispiel für die CL-Umgebungsvariable festlegen:

> Legen Sie CL = / Zp2/Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ

Wenn diese Umgebungsvariable festgelegt ist, bei der Eingabe `CL INPUT.C` in der Befehlszeile, die dies ist der effektive Befehl:

> CL /Zp2/Ox /I\INCLUDE\MYINCLS \LIB\BINMODE. OBJ-EINGABE. C

Im folgenden Beispiel wird verursacht, dass ein unformatierter CL-Befehl die Quelldateien „FILE1.c“ und „FILE2.c“ kompiliert. Anschließend werden die Objektdateien „FILE1.obj“, „FILE2.obj“ und „FILE3.obj“ verknüpft.

> SET CL = "FILE1" HER. C-FILE2. C  
> LEGEN SIE \_CL\_= DATEI3. OBJ  
> CL  

Dies hat den gleichen Effekt wie der Code in der folgenden Befehlszeile:

> CL "FILE1" HER. C-FILE2. C-DATEI3. OBJ

## <a name="see-also"></a>Siehe auch

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
[Compileroptionen](../../build/reference/compiler-options.md)
