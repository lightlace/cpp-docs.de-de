---
title: -BINDEN VON | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bind
dev_langs:
- C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b77c778017dc78235948e8d23db136c1f63ab12d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372430"
---
# <a name="bind"></a>/BIND
```  
/BIND[:PATH=path]  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option wird die Adressen der Einstiegspunkte in die importieren Local Address Table für eine ausführbare Datei oder DLL an. Verwenden Sie diese Option, um die Ladezeit eines Programms zu reduzieren.  
  
 Geben Sie des Programms ausführbare Datei und -DLLs in den *Dateien* Argument in der EDITBIN-Befehlszeile. Das optionale *Pfad*  /BIND Argument gibt den Speicherort der DLLs, die von den angegebenen Dateien verwendet. Trennen Sie mehrere Verzeichnisse mit einem Semikolon (**;**). Wenn *Pfad* nicht angegeben wird, EDITBIN durchsucht, die in der PATH-Umgebungsvariablen angegebenen Verzeichnisse. Wenn *Pfad* angegeben wird, EDITBIN ignoriert die PATH-Umgebungsvariable.  
  
 Standardmäßig legt das Ladeprogramm die Adressen der Einstiegspunkte, beim Laden eines Programms. Dieser Vorgang dauert lange variiert, je nach der Anzahl der DLLs und die Anzahl der verschiedenen Punkten im Programm verwiesen wird. Wenn ein Programm mit/BIND geändert wurde und die Basisadressen für die ausführbare Datei und die DLLs nicht in Konflikt mit DLLs, die bereits geladen sind, muss das Betriebssystem nicht diese Adressen festgelegt. In einer Situation, in dem die Dateien fälschlicherweise basieren, wird das Betriebssystem verschiebt die DLLs des Programms und berechnet die Einstiegspunkt Adressen, die zur Ladezeit des Programms hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)