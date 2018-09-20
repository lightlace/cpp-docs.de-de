---
title: Festlegen des Pfadnamens | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 636326e5af577b4e26c61a2094fe73dd4a680f2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402472"
---
# <a name="specifying-the-pathname"></a>Festlegen des Pfadnamens

Akzeptiert jede Option für die Ausgabedatei eine *Pfadnamen* Argument, das einen Speicherort und einen Namen für die Ausgabedatei angeben kann. Das Argument kann es sich um einen Laufwerknamen Verzeichnis und Dateinamen enthalten. Zwischen der Option und das Argument darf kein Leerzeichen stehen.

Wenn *Pfadnamen* enthält einen Dateinamen ohne Erweiterung, gibt der Compiler die Ausgabe eine standarderweiterung. Wenn *Pfadnamen* enthält ein Verzeichnis, aber keine Dateinamen, erstellt der Compiler eine Datei mit einem Standardnamen im angegebenen Verzeichnis. Der Standardname basiert auf der Basisname der Quelldatei und die standarderweiterung basierend auf dem Typ der Ausgabedatei. Wenn Sie deaktiviert lassen *Pfadnamen* vollständig, erstellt der Compiler eine Datei mit einem Standardnamen in einem Standardverzeichnis.

Sie können auch die *Pfadnamen* Argument kann einen Gerätenamen (AUX, CON, PRN oder null) sein, anstatt einen Dateinamen ein. Verwenden Sie ein Leerzeichen zwischen der Option und der Name des Geräts oder einen Doppelpunkt nicht als Teil des Gerätenamens.

|Name des Geräts|Bedeutung|
|-----------------|----------------|
|AUX|Zusätzliche Geräte|
|CON|Konsole|
|PRN|Drucker|
|NUL|NULL-Gerät (keine Datei erstellt)|

## <a name="example"></a>Beispiel

Die folgende Befehlszeile wird eine MAP-Datei an den Drucker gesendet:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)