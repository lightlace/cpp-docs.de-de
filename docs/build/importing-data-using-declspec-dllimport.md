---
title: Importieren von Daten mithilfe von "__declspec(dllimport)" "| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9877c5a229c3cabcb7703dd2617d1d57e3512f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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