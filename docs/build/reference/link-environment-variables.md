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
ms.openlocfilehash: 03f84ea1071a672aef4443e5acf44daae91bb3b7
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422132"
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
