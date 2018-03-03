---
title: "Reservierte Wörter | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35f9a3e907b72b4b8cf8e673e771832ba3fc0527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="reserved-words"></a>Reservierte Wörter
Die folgenden Wörter sind vom Linker reserviert. Diese Namen können verwendet werden, als Argumente im [moduldefinitionsanweisungen](../../build/reference/module-definition-dot-def-files.md) nur, wenn der Name in doppelte Anführungszeichen eingeschlossen wird ("").  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**VORAB LADEN**|  
|**BASIS**|**IOPL**|**PRIVATE**|  
|**CODE**|**BIBLIOTHEK**1|**PROTMODE**2|  
|**ENTSPRECHEN**|**LOADONCALL**1|**REINE**1|  
|**DATEN**|**LONGNAMES**2|**READONLY**|  
|**BESCHREIBUNG**|**VERSCHIEBBARE**1|**READWRITE**|  
|**DEV386**|**VERSCHOBEN**1|**REALMODE**1|  
|**ENTFERNBAR**|**MEHRERE**|**RESIDENTE**|  
|**DYNAMISCHE**|**NAME**|**RESIDENTNAME**1|  
|**NUR AUSFÜHREN**|**NEWFILES**2|**ABSCHNITTE**|  
|**EXECUTEONLY**|**"NODATA"**1|**SEGMENTE**|  
|**AUSFÜHRENLESEN**|**NOIOPL**1|**FREIGEGEBENE**|  
|**EXETYPE**|**NONAME**|**EINZELNE**|  
|**EXPORTE**|**NICHT ÜBEREINSTIMMENDE**1|**STACKSIZE**|  
|**FESTE**1|**NONDISCARDABLE**|**STUB**|  
|**FUNKTIONEN**2|**KEINE**|**VERSION**|  
|**HEAPSIZE**|**NICHT FREIGEGEBENE**|**WINDOWAPI**|  
|**IMPORTE**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**UNREINE**1|**OBJEKTE**|**WINDOWS**|  
|**UMFASSEN**2|**ALTE**1||  
  
 1 der Linker gibt eine Warnung ("ignoriert"), wenn dieser Begriff gefunden wird. Das Wort ist jedoch weiterhin reserviert.  
  
 2 der Linker ignoriert dieses Wort, aber es gibt keine Warnung aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)