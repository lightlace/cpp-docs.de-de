---
title: /PDBALTPATH (Use Alternate PDB Path)
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: 660e39a97b9fed0c5a9228fe011e7c0fa2566e68
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820714"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Use Alternate PDB Path)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>Argumente

*pdb_file_name*<br/>
Der Pfad und der Dateiname für die .pdb-Datei.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Option, um einen alternativen Speicherort für die Programmdatenbankdatei (.pdb) in einer kompilierten Binärdatei bereitzustellen. Normalerweise zeichnet der Linker den Speicherort der .pdb-Dateien in den Binärdateien auf, die er produziert. Sie können diese Option verwenden, um einen anderen Pfad und Dateinamen für die .pdb-Datei bereitzustellen. Die mit /PDBALTPATH bereitgestellten Informationen ändern weder den Standort noch den Namen der tatsächlichen .pdb-Datei, sondern sie ändern die Informationen, die der Linker in die Binärdatei schreibt. Damit können Sie einen Pfad bereitstellen, der unabhängig von der Dateistruktur des Buildcomputers ist. Zwei typische Verwendungszwecke für die Option ist die Bereitstellung eines Netzwerkpfads oder einer Datei, die keine Pfadinformationen hat.

Der Wert des *Pdb_file_name* kann eine beliebige Zeichenfolge, die eine Umgebungsvariable sein oder **%_PDB%**. Der Linker erweitert eine Umgebungsvariable, wie z. B. **%SystemRoot%**, auf den Wert. Der Linker definiert die Umgebungsvariablen **%_PDB%** und **%_EXT%**. **%_PDB%** wird auf den Namen der tatsächlichen .pdb-Datei ohne Pfadinformationen erweitert und **%_EXT%** ist die Erweiterung der generierten ausführbaren Datei.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)<br/>
[/PDBPATH](pdbpath.md)
