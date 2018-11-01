---
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: d77ab2eb056326ba372a60cc79688d26b252ac44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527217"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der .dll oder .exe-Datei für die die entsprechenden PDB-Datei gefunden werden sollen.

**: AUSFÜHRLICHE**<br/>
(Optional) Gibt alle Verzeichnisse, in dem versucht wurde, die PDB-Datei zu suchen.

## <a name="remarks"></a>Hinweise

/ PDBPATH sucht auf den Computer, auf die gleiche Pfade, die der Debugger Suche nach einer PDB-Datei und meldet die, sofern vorhanden, PDB-Dateien im angegebenen Datei entsprechen *Filename*.

Wenn Sie Visual Studio-Debugger verwenden, ein Problem kann auftreten, aufgrund der Tatsache, dass der Debugger keine PDB-Datei für eine andere Version der Datei verwendet wird, die Sie debuggen.

/ PDBPATH sucht nach PDB-Dateien die folgenden Pfade:

- Überprüfen Sie den Speicherort, in dem die ausführbare Datei befindet.

- Überprüfen Sie den Speicherort der PDB-Datei in die ausführbare Datei geschrieben. In der Regel ist dies der Speicherort, zu dem Zeitpunkt, der das Bild verknüpft wurde.

- Überprüfen Sie auf den Suchpfad, die in Visual Studio-IDE konfiguriert.

- Überprüfen Sie entlang der Pfade in der _NT_SYMBOL_PATH und _NT_ALT_SYMBOL_PATH Umgebungsvariablen.

- Überprüfen Sie in das Windows-Verzeichnis.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)<br/>
[/PDBALTPATH (Alternativen PDB-Pfad verwenden)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)