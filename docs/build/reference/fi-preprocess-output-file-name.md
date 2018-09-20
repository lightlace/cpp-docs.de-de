---
title: -Fi (Ausgabedateiname vorverarbeiten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f69a4ab16956924e3bcfd785c6a86c7ac238b36
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431553"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (Ausgabedateiname vorverarbeiten)

Gibt den Namen der Ausgabedatei an, die die [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) Compileroption die vorverarbeitete Ausgabe schreibt.

## <a name="syntax"></a>Syntax

```
/Fipathname
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`pathname`|Den Namen und Pfad der Ausgabedatei erstellt, indem die **/p** -Compileroption.|

## <a name="remarks"></a>Hinweise

Verwenden der **/Fi** -Compileroption in Kombination mit der **/p** -Compileroption.

Wenn Sie angeben, dass nur einen Pfad für die `pathname` Parameter, der Basisname der Quelldatei als Basisname der vorverarbeiteten Ausgabedatei verwendet wird. Die `pathname` Parameter erfordert keine bestimmten Dateinamenerweiterung. Allerdings ist eine Erweiterung von "fügen" verwendet, wenn Sie keine Dateinamenerweiterung angeben.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile führt eine vorverarbeitung PROGRAM.cpp, behält Kommentare, fügt [#line](../../preprocessor/hash-line-directive-c-cpp.md) -Direktiven und das Ergebnis der MYPROCESS.i-Datei schreibt.

```
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[/P (In einer Datei vorverarbeiten)](../../build/reference/p-preprocess-to-a-file.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)