---
title: Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt nach Name | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- NONAME
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d894df971dd0c50556a420eafa2909474ee6912
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714258"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen

Die einfachste Möglichkeit zum Exportieren von Funktionen aus einer DLL ist nach dem Namen exportiert. Dies ist der Fall bei der Verwendung **__declspec(dllexport)**, z. B. Aber Sie können stattdessen Funktionen anhand der Ordinalzahl exportieren. Mit diesem Verfahren können Sie müssen eine DEF-Datei anstelle von verwenden **__declspec(dllexport)**. Fügen Sie zum Angeben einer Funktion Ordinalwert seiner Ordnungszahl, an dem Funktionsnamen in der DEF-Datei. Weitere Informationen zum Festlegen der Ordinalzahlen, finden Sie unter [aus einer DLL mithilfe von DEF-Dateien exportieren](../build/exporting-from-a-dll-using-def-files.md).

> [!TIP]
>  Wenn Sie die Größe von der DLL Datei optimieren möchten, verwenden Sie die **NONAME** Attribut für jede exportierte Funktion. Mit der **NONAME** -Attribut die Ordnungszahlen werden gespeichert, der DLLs zu exportieren, die Namen der Funktionen, sondern die Tabelle. Dies kann eine erheblichen einsparungen sein, wenn Sie viele Funktionen exportieren.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Verwenden Sie eine DEF-Datei, sodass ich anhand der Ordinalzahl exportieren können](../build/exporting-from-a-dll-using-def-files.md)

- [Verwenden von "__declspec(dllexport)" "](../build/exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](../build/exporting-from-a-dll.md)