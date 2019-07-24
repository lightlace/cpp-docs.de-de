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
ms.openlocfilehash: 7d51f599dfb81dfa860e1bdba86c4372e80379fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319420"
---
# <a name="reserved-words"></a>Reservierte Wörter

Die folgenden Wörter sind vom Linker reserviert. Diese Namen können verwendet werden, als Argumente in [moduldefinitionsanweisungen](module-definition-dot-def-files.md) nur dann, wenn der Name in doppelte Anführungszeichen eingeschlossen wird ("").

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**VORAB LADEN**|
|**BASE**|**IOPL**|**PRIVATE**|
|**CODE**|**BIBLIOTHEK**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**ENTSPRECHEN**|**LOADONCALL**<sup>1</sup>|**REINE**<sup>1</sup>|
|**DATA**|**LONGNAMES**<sup>2</sup>|**READONLY**|
|**BESCHREIBUNG**|**MOVABLE**<sup>1</sup>|**READWRITE**|
|**DEV386**|**MOVEABLE**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**ENTFERNBARE**|**MULTIPLE**|**RESIDENT**|
|**DYNAMIC**|**NAME**|**RESIDENTNAME**<sup>1</sup>|
|**NUR AUSFÜHREN**|**NEWFILES**<sup>2</sup>|**ABSCHNITTE**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**SEGMENTE**|
|**AUSFÜHRENLESEN**|**NOIOPL**<sup>1</sup>|**FREIGEGEBENE**|
|**EXETYPE**|**NONAME**|**EINZELNE**|
|**EXPORTE**|**NICHT KONFORME**<sup>1</sup>|**STACKSIZE**|
|**FESTE**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**FUNKTIONEN**<sup>2</sup>|**NONE**|**VERSION**|
|**HEAPSIZE**|**NICHT FREIGEGEBENE**|**WINDOWAPI**|
|**IMPORTS**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**UNSAUBEREN**<sup>1</sup>|**OBJEKTE**|**WINDOWS**|
|**UMFASSEN**<sup>2</sup>|**OLD**<sup>1</sup>||

<sup>1</sup> der Linker eine Warnung ("ignoriert") gibt, wenn dieser Begriff gefunden. Das Wort ist jedoch weiterhin reserviert.

<sup>2</sup> vom Linker ignoriert dieses Wort, jedoch keine Warnung ausgegeben.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)