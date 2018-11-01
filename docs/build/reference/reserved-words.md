---
title: Reservierte Wörter
ms.date: 11/04/2016
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
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 360baf479f9100483fe694ca8860dfc1d7ebfe11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502465"
---
# <a name="reserved-words"></a>Reservierte Wörter

Die folgenden Wörter sind vom Linker reserviert. Diese Namen können verwendet werden, als Argumente in [moduldefinitionsanweisungen](../../build/reference/module-definition-dot-def-files.md) nur dann, wenn der Name in doppelte Anführungszeichen eingeschlossen wird ("").

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**VORAB LADEN**|
|**BASIS**|**IOPL**|**PRIVATE**|
|**CODE**|**BIBLIOTHEK**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**ENTSPRECHEN**|**LOADONCALL**<sup>1</sup>|**REINE**<sup>1</sup>|
|**DATEN**|**LONGNAMES**<sup>2</sup>|**READONLY**|
|**BESCHREIBUNG**|**VERSCHIEBBARE**<sup>1</sup>|**"READWRITE"**|
|**DEV386**|**MOVEABLE**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**ENTFERNBARE**|**MEHRERE**|**RESIDENTE**|
|**DYNAMISCHE**|**NAME**|**RESIDENTNAME**<sup>1</sup>|
|**NUR AUSFÜHREN**|**NEWFILES**<sup>2</sup>|**ABSCHNITTE**|
|**EXECUTEONLY**|**"NODATA"**<sup>1</sup>|**SEGMENTE**|
|**AUSFÜHRENLESEN**|**NOIOPL**<sup>1</sup>|**FREIGEGEBENE**|
|**EXETYPE**|**NONAME**|**EINZELNE**|
|**EXPORTE**|**NICHT KONFORME**<sup>1</sup>|**STACKSIZE**|
|**FESTE**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**FUNKTIONEN**<sup>2</sup>|**KEINE**|**VERSION**|
|**HEAPSIZE**|**NICHT FREIGEGEBENE**|**WINDOWAPI**|
|**IMPORTE**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**UNSAUBEREN**<sup>1</sup>|**OBJEKTE**|**WINDOWS**|
|**UMFASSEN**<sup>2</sup>|**ALTE**<sup>1</sup>||

<sup>1</sup> der Linker eine Warnung ("ignoriert") gibt, wenn dieser Begriff gefunden. Das Wort ist jedoch weiterhin reserviert.

<sup>2</sup> vom Linker ignoriert dieses Wort, jedoch keine Warnung ausgegeben.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)