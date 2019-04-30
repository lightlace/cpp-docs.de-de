---
title: Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen
ms.date: 11/04/2016
f1_keywords:
- NONAME
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: 26b9a51a440e4e05c39908cb437d82e2e08e30c9
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342207"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen

Die einfachste Möglichkeit zum Exportieren von Funktionen aus einer DLL ist nach dem Namen exportiert. Dies ist der Fall bei der Verwendung **__declspec(dllexport)**, z. B. Aber Sie können stattdessen Funktionen anhand der Ordinalzahl exportieren. Mit diesem Verfahren können Sie müssen eine DEF-Datei anstelle von verwenden **__declspec(dllexport)**. Fügen Sie zum Angeben einer Funktion Ordinalwert seiner Ordnungszahl, an dem Funktionsnamen in der DEF-Datei. Weitere Informationen zum Festlegen der Ordinalzahlen, finden Sie unter [aus einer DLL mithilfe von DEF-Dateien exportieren](exporting-from-a-dll-using-def-files.md).

> [!TIP]
>  Wenn Sie die Größe von der DLL Datei optimieren möchten, verwenden Sie die **NONAME** Attribut für jede exportierte Funktion. Mit der **NONAME** -Attribut die Ordnungszahlen werden gespeichert, der DLLs zu exportieren, die Namen der Funktionen, sondern die Tabelle. Dies kann eine erheblichen einsparungen sein, wenn Sie viele Funktionen exportieren.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Verwenden Sie eine DEF-Datei, sodass ich anhand der Ordinalzahl exportieren können](exporting-from-a-dll-using-def-files.md)

- [Use __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](exporting-from-a-dll.md)
