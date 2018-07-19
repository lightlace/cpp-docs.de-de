---
title: Importieren und Exportieren von Inlinefunktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b666d450766a5a285f02517d92d5eb4dc3f29c68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368576"
---
# <a name="importing-and-exporting-inline-functions"></a>Importieren und Exportieren von Inlinefunktionen
Importierte Funktionen können als Inline definiert werden. Die Wirkung gleicht ungefähr identisch mit eine standard-Funktion Inline zu definieren; Aufrufe der Funktion werden als Inlinecode, ähnlich wie ein Makro erweitert. Dies eignet sich hauptsächlich als eine Methode zur Unterstützung von C++ in einer DLL Bindungselementklassen, kommt es möglicherweise Inline Teil ihrer Member-Funktionen für die Effizienz.  
  
 Eine Funktion des Inline-importierten Funktion ist, deren Adresse in C++ zu übernehmen. Der Compiler gibt die Adresse der Kopie in der DLL Inlinefunktion zurück. Eine weitere Funktion von importierten Inlinefunktionen ist, dass Sie die statische lokale Daten der importierten Funktion, im Gegensatz zu globalen importierten Daten initialisiert werden können.  
  
> [!CAUTION]
>  Inlinefunktionen Bereitstellung importiert werden, da die Möglichkeit, dass Konflikte zwischen Versionen erstellt werden kann, sollten Sie Sorgfalt walten. Eine Inlinefunktion ruft in den Code der Anwendung erweitert. Deshalb, wenn Sie die Funktion später neu schreiben, wird er nicht aktualisiert, wenn die Anwendung selbst neu kompiliert wird. (In der Regel können DLL-Funktionen aktualisiert werden, ohne das Neuerstellen der Anwendungen, die sie verwenden.)  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)  
  
-   [Exportieren Sie aus einer DLL verwenden. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Welche Exportmethode ermitteln](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren und Exportieren](../build/importing-and-exporting.md)