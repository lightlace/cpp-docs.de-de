---
title: -ALLOWISOLATION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cb92a7f31d48dad4a7fb608703c71ccc661e176
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368973"
---
# <a name="allowisolation"></a>/ALLOWISOLATION
Gibt das Verhalten bei der Manifestsuche an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ ALLOWISOLATION** bewirkt, dass das Betriebssystem, Suchvorgänge und-Ladevorgänge durchführt.  
  
 **/ ALLOWISOLATION** ist die Standardeinstellung.  
  
 **/ALLOWISOLATION:No** gibt an, dass ausführbare Dateien geladen werden, als wäre es kein Manifest und Ursachen [EDITBIN-Referenz](../../build/reference/editbin-reference.md) festzulegende der `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit im optionalen-Headers `DllCharacteristics` Feld.  
  
 Wenn die Isolation für eine ausführbare Datei deaktiviert ist, führt das Windows-Ladeprogramm keine Suche nach dem Anwendungsmanifest für den neu erstellen Prozess durch. Der neue Prozess verfügt nicht über eine Standard-Aktivierungskontext, selbst wenn ein Manifest in die ausführbare Datei selbst vorhanden ist oder wenn ein Manifest mit dem Namen Listenfeldsteuerelement *Name der ausführbaren Datei*. exe.manifest.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)   
 [/ ALLOWISOLATION (Manifestsuche)](../../build/reference/allowisolation-manifest-lookup.md)   
 [Manifestdateienreferenz](http://msdn.microsoft.com/library/aa375632.aspx)