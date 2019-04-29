---
title: MSVC-Compiler-Befehlszeilensyntax
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 5cee76d5c053dbcfef33a191dc38a958338e4a82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294342"
---
# <a name="compiler-command-line-syntax"></a>Syntax für die Compilerbefehlszeile

Die CL-Befehlszeile wird die folgende Syntax verwendet:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

Die folgende Tabelle beschreibt die Eingabe in der CL-Befehl.

|Eingabe|Bedeutung|
|-----------|-------------|
|*option*|Eine oder mehrere [CL-Optionen](compiler-options.md). Beachten Sie, dass alle Optionen für alle angegebenen Dateien gelten. Optionen werden durch einen Bindestrich (-) oder einem Schrägstrich (/) angegeben. Wenn eine Option die ein Argument, die Option des Beschreibungsdokumenten verwendet wird, ob ein Leerzeichen zwischen der Option und die Argumente zulässig ist. Optionsnamen (mit Ausnahme der Option ' / help ') sind Groß-/Kleinschreibung beachtet. Finden Sie unter [Reihenfolge von CL-Optionen](order-of-cl-options.md) für Weitere Informationen.|
|`file`|Der Name des einen oder mehrere Quelldateien, OBJ-Dateien und Bibliotheken. Kompiliert Quelldateien "CL" und übergibt an den Linker die Namen der OBJ-Dateien und Bibliotheken. Finden Sie unter [Syntax für Dateinamen bei CL](cl-filename-syntax.md) für Weitere Informationen.|
|*lib*|Eine oder mehrere Namen von Typbibliotheken. CL übergibt diese Namen für dem Linker an.|
|*command-file*|Eine Datei mit mehreren Optionen und Dateinamen. Finden Sie unter [CL-Befehlsdateien](cl-command-files.md) für Weitere Informationen.|
|*link-opt*|Eine oder mehrere [MSVC-Linkeroptionen](linker-options.md). CL übergibt diese Optionen für dem Linker an.|

Sie können eine beliebige Anzahl von Optionen, Dateinamen und Bibliotheksnamen, angeben, solange die Anzahl der Zeichen in der Befehlszeile 1024, das Limit vorgegeben, die vom Betriebssystem nicht überschreitet.

Informationen über den Rückgabewert von cl.exe, finden Sie unter [Rückgabewert von cl.exe](return-value-of-cl-exe.md) .

> [!NOTE]
>  Grenze von 1024 Zeichen für die Eingabe in der Befehlszeile ist nicht garantiert, in zukünftigen Versionen von Windows unverändert bleiben.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)
