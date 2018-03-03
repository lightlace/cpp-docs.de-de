---
title: -ALLOWISOLATION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba0295d73e51e28fbdd953d7d9a3a2ae5131c27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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