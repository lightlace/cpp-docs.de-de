---
title: Syntax für die Compilerbefehlszeile
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: f5e611064f7f4670056a42e5ccee1f291fbdd567
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421232"
---
# <a name="compiler-command-line-syntax"></a>Syntax für die Compilerbefehlszeile

Die CL-Befehlszeile wird die folgende Syntax verwendet:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

Die folgende Tabelle beschreibt die Eingabe in der CL-Befehl.

|Eingabe|Bedeutung|
|-----------|-------------|
|*option*|Eine oder mehrere [CL-Optionen](../../build/reference/compiler-options.md). Beachten Sie, dass alle Optionen für alle angegebenen Dateien gelten. Optionen werden durch einen Bindestrich (-) oder einem Schrägstrich (/) angegeben. Wenn eine Option die ein Argument, die Option des Beschreibungsdokumenten verwendet wird, ob ein Leerzeichen zwischen der Option und die Argumente zulässig ist. Optionsnamen (mit Ausnahme der Option ' / help ') sind Groß-/Kleinschreibung beachtet. Finden Sie unter [Reihenfolge von CL-Optionen](../../build/reference/order-of-cl-options.md) für Weitere Informationen.|
|`file`|Der Name des einen oder mehrere Quelldateien, OBJ-Dateien und Bibliotheken. Kompiliert Quelldateien "CL" und übergibt an den Linker die Namen der OBJ-Dateien und Bibliotheken. Finden Sie unter [Syntax für Dateinamen bei CL](../../build/reference/cl-filename-syntax.md) für Weitere Informationen.|
|*lib*|Eine oder mehrere Namen von Typbibliotheken. CL übergibt diese Namen für dem Linker an.|
|*command-file*|Eine Datei mit mehreren Optionen und Dateinamen. Finden Sie unter [CL-Befehlsdateien](../../build/reference/cl-command-files.md) für Weitere Informationen.|
|*link-opt*|Eine oder mehrere [Optionen des Linkers](../../build/reference/linker-options.md). CL übergibt diese Optionen für dem Linker an.|

Sie können eine beliebige Anzahl von Optionen, Dateinamen und Bibliotheksnamen, angeben, solange die Anzahl der Zeichen in der Befehlszeile 1024, das Limit vorgegeben, die vom Betriebssystem nicht überschreitet.

Informationen über den Rückgabewert von cl.exe, finden Sie unter [Rückgabewert von cl.exe](../../build/reference/return-value-of-cl-exe.md) .

> [!NOTE]
>  Grenze von 1024 Zeichen für die Eingabe in der Befehlszeile ist nicht garantiert, in zukünftigen Versionen von Windows unverändert bleiben.

## <a name="see-also"></a>Siehe auch

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)
