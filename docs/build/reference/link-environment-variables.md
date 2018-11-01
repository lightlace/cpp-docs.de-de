---
title: LINK-Umgebungsvariablen
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
ms.openlocfilehash: 3a398787530794f5a08d6cd122e55c305e265062
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434410"
---
# <a name="link-environment-variables"></a>LINK-Umgebungsvariablen

Das LINK-Tool verwendet die folgenden Umgebungsvariablen:

- LINK und \_LINK\_, wenn definiert. Das LINK-Tool voran, die Optionen und Argumente, die in der Umgebungsvariablen LINK definiert ist, und fügt die Optionen und Argumente definiert, der \_LINK\_ -Umgebungsvariable auf die Argumente über die Befehlszeile vor der Verarbeitung.

- LIB, falls definiert. Der LINK-Tools verwenden den LIB-Pfad an, bei der Suche nach der ein Objekt, Bibliothek oder anderen Datei angegeben, in der Befehlszeile oder durch die [/BASE](../../build/reference/base-base-address.md) Option. Der LIB-Pfad wird auch verwendet, um nach einer in einem Objekt genannten PDB-Datei zu suchen. Die LIB-Variable kann mehrere durch Semikolons getrennte Pfadangaben enthalten. Ein Pfad muss auf das Unterverzeichnis \lib der Visual C++-Installation zeigen.

- PATH, wenn das Tool CVTRES ausführen muss und die Datei nicht im selben Verzeichnis wie LINK findet. (LINK benötigt CVTRES, um eine RES-Datei zu verknüpfen.) PATH muss auf das Unterverzeichnis \bin der Visual C++-Installation zeigen.

- TMP zum Angeben eines Verzeichnisses beim Verknüpfen von OMF oder RES-Dateien

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
[Erstellen von C/C++-Code in der Befehlszeile](../../build/building-on-the-command-line.md)<br/>
[Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
