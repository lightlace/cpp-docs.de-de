---
title: Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen | Microsoft Docs
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
ms.openlocfilehash: b05f3e429406b3c24c7a21ce9ee8e10fe19c14b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen
Die einfachste Möglichkeit zum Exportieren von Funktionen aus einer DLL wird anhand des Namens exportiert. Dies ist, was geschieht, wenn Sie **__declspec(dllexport)**, z. B. Aber Sie können stattdessen Funktionen anhand der Ordinalzahl exportieren. Mit dieser Methode müssen Sie verwenden eine DEF-Datei anstelle von **__declspec(dllexport)**. Um Ordinalwert einer Funktion anzugeben, fügen Sie seiner Ordnungszahl, an dem Funktionsnamen in der DEF-Datei. Informationen zum Angeben von Ordinalzahlen finden Sie unter [exportieren aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md).  
  
> [!TIP]
>  Wenn Sie die Größe für die DLL-Datei zu optimieren möchten, verwenden Sie die **NONAME** Attribut für jede exportierte Funktion. Mit der **NONAME** -Attribut, die Ordnungszahlen werden gespeichert, die DLL zu exportieren, den Funktionsnamen, sondern die Tabelle. Dies kann platzsparend sein, wenn Sie viele Funktionen exportieren.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Verwenden Sie eine DEF-Datei, daher können durch die Ordinalzahl exportieren](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)