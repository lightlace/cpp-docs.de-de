---
title: Reservierte Wörter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 132bd8e5ba66cbf9486a6da4747994c667e2f6e7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705659"
---
# <a name="reserved-words"></a>Reservierte Wörter

Die folgenden Wörter sind vom Linker reserviert. Diese Namen können verwendet werden, als Argumente im [moduldefinitionsanweisungen](../../build/reference/module-definition-dot-def-files.md) nur, wenn der Name in doppelte Anführungszeichen eingeschlossen wird ("").

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**VORAB LADEN**|
|**BASIS**|**IOPL**|**PRIVATE**|
|**CODE**|**BIBLIOTHEK**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**ENTSPRECHEN**|**LOADONCALL**<sup>1</sup>|**REINE**<sup>1</sup>|
|**DATEN**|**LONGNAMES**<sup>2</sup>|**READONLY**|
|**BESCHREIBUNG**|**VERSCHIEBBARE**<sup>1</sup>|**READWRITE**|
|**DEV386**|**VERSCHOBEN**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**ENTFERNBAR**|**MEHRERE**|**RESIDENTE**|
|**DYNAMISCHE**|**NAME**|**RESIDENTNAME**<sup>1</sup>|
|**NUR AUSFÜHREN**|**NEWFILES**<sup>2</sup>|**ABSCHNITTE**|
|**EXECUTEONLY**|**"NODATA"**<sup>1</sup>|**SEGMENTE**|
|**AUSFÜHRENLESEN**|**NOIOPL**<sup>1</sup>|**FREIGEGEBENE**|
|**EXETYPE**|**NONAME**|**EINZELNE**|
|**EXPORTE**|**NICHT ÜBEREINSTIMMENDE**<sup>1</sup>|**STACKSIZE**|
|**FESTE**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**FUNKTIONEN**<sup>2</sup>|**KEINE**|**VERSION**|
|**HEAPSIZE**|**NICHT FREIGEGEBENE**|**WINDOWAPI**|
|**IMPORTE**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**UNREINE**<sup>1</sup>|**OBJEKTE**|**WINDOWS**|
|**UMFASSEN**<sup>2</sup>|**ALTE**<sup>1</sup>||

<sup>1</sup> der Linker eine Warnung ("ignoriert") ausgibt, wenn dieser Begriff gefunden wird. Das Wort ist jedoch weiterhin reserviert.

<sup>2</sup> vom Linker ignoriert diese Word jedoch keine Warnung ausgibt.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)