---
title: Importieren von Daten mithilfe von "__declspec(dllimport)" "| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ebbc91b9144a7fe8025a34e9c1476ab23b604c46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="importing-data-using-declspecdllimport"></a>Importieren von Daten mithilfe von "__declspec(dllimport)"
Im Fall von Daten mithilfe von **von "__declspec(dllimport)" "** bietet eine bequeme Möglichkeit, die eine Dereferenzierungsschicht entfernt werden. Beim Importieren von Daten aus einer DLL müssen Sie die Import Local Address Table durchlaufen. Vor dem **von "__declspec(dllimport)" "**, hierzu mussten wir mussten Sie denken Sie daran, eine zusätzliche Dereferenzierungsebene beim Zugreifen auf Daten, die von der DLL exportiert:  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 Sie würden dann exportieren, die Daten in Ihrem. DEF-Datei:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 und darauf außerhalb der DLL zugreifen:  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 Wenn Sie die Daten als markieren **von "__declspec(dllimport)" "**, generiert der Compiler die Dereferenzierung Code automatisch für Sie. Sie müssen nicht mehr über den oben beschriebenen Schritten machen. Wie bereits erwähnt, verwenden Sie keine **von "__declspec(dllimport)" "** Deklaration für die Daten beim Erstellen der DLL. Funktionen innerhalb der DLL verwenden Sie die Import Local Address Table auf das Datenobjekt nicht; aus diesem Grund müssen Sie nicht den zusätzliche Maß an Dereferenzierung vorhanden.  
  
 Verwenden Sie diese Deklaration, um die Daten automatisch aus der DLL zu exportieren:  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)