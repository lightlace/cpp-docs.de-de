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
ms.openlocfilehash: f29b8e61fbfbdb0f373e3e7510cb3f1fe0b9cc2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319849"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der .dll oder .exe-Datei für die die entsprechenden PDB-Datei gefunden werden sollen.

**:VERBOSE**<br/>
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

[DUMPBIN-Optionen](dumpbin-options.md)<br/>
[/PDBALTPATH (Alternativen PDB-Pfad verwenden)](pdbaltpath-use-alternate-pdb-path.md)
