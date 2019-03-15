---
title: CL-Befehlsdateien
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
ms.openlocfilehash: 9810f7b4308eab2b47a068072039335e59e19f5f
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57816073"
---
# <a name="cl-command-files"></a>CL-Befehlsdateien

Eine Befehlsdatei ist eine Textdatei, die Optionen und Dateinamen, geben Sie andernfalls auf, enthält die [Befehlszeile](compiler-command-line-syntax.md) oder mithilfe der [CL-Umgebungsvariablen](cl-environment-variables.md). CL akzeptiert eine Compiler-Befehlsdatei als Argument in der CL-Umgebungsvariablen oder in der Befehlszeile an. Anders als in der Befehlszeile oder in der CL-Umgebungsvariablen können Sie in einer Befehlsdatei mehrzeilige Optionen und Dateinamen verwenden.

Optionen und Dateinamen in einer Befehlsdatei werden entsprechend der Position eines Befehls Dateinamens in der CL-Umgebungsvariablen oder in der Befehlszeile verarbeitet. Wenn die Option/Link in der Befehlsdatei angezeigt wird, werden jedoch alle Optionen auf der Rest der Zeile an den Linker übergeben. Optionen in den nachfolgenden Zeilen in der Befehlsdatei und Optionen in der Befehlszeile nach dem Aufruf der Befehlsdatei werden weiterhin wie Compileroptionen akzeptiert. Weitere Informationen zu den Auswirkungen von deren Interpretation aufgelistet in der Reihenfolge der Optionen, finden Sie unter [Reihenfolge von CL-Optionen](order-of-cl-options.md).

Eine Befehlsdatei darf nicht den CL-Befehl. Jede Option muss beginnen und enden, die in der gleichen Zeile; Sie können den umgekehrten Schrägstrich nicht verwenden (**\\**) eine Option auf zwei Zeilen zu kombinieren.

Eine Befehlsdatei wird angegeben, indem ein at-Zeichen (**\@**) gefolgt von einem Filename; der Dateiname kann einen absoluten oder relativen Pfad angeben.

Beispielsweise in einer Datei mit dem Namen RESP ist der folgende Befehl aus:

```
/Og /link LIBC.LIB
```

und geben Sie den folgenden CL-Befehl:

```
CL /Ob2 @RESP MYAPP.C
```

der Befehl für CL lautet wie folgt aus:

```
CL /Ob2 /Og MYAPP.C /link LIBC.LIB
```

Beachten Sie, dass die Befehlszeile und die Befehlsdatei Befehle effektiv kombiniert werden.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[MSVC-Compiler-Optionen](compiler-options.md)
