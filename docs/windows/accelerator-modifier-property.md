---
title: Eigenschaft "Modifizierer" Accelerator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63d6a4b526fc1f2aeb2a942e682a8c7cc6f9b58c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-modifier-property"></a>Eigenschaft "Modifizierer" von Zugriffstasten
Die folgenden sind Einträge zulässig für die Eigenschaft "Modifizierer" in der Zugriffstastentabelle.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**Keine**|Benutzer drückt die Schlüssel-Wert. Dies ist am effizientesten mit den ASCII/ANSI-Werten 001 bis 026, was interpretiert wird als ^ A bis ^ Z (STRG + A bis STRG-Z).|  
|**ALT-Taste**|Der Benutzer muss vor dem Schlüssel-Wert die ALT-Taste drücken.|  
|**STRG**|Benutzer muss vor dem Schlüssel-Wert die STRG-Taste drücken. Mit dem ASCII-Typ ist ungültig.|  
|**Umschalttaste gedrückt**|Der Benutzer muss die UMSCHALTTASTE gedrückt, bevor der Schlüssel-Wert drücken.|  
|**Strg + Alt**|Der Benutzer muss die STRG-Taste und bevor der Schlüssel-Wert die ALT-Taste drücken. Mit dem ASCII-Typ ist ungültig.|  
|**STRG + UMSCHALT**|Benutzer muss drücken Sie die STRG-Taste und die UMSCHALTTASTE gedrückt, bevor der Schlüssel-Wert. Mit dem ASCII-Typ ist ungültig.|  
|**ALT + UMSCHALT**|Benutzer muss drücken Sie die ALT-Taste und die UMSCHALTTASTE gedrückt, bevor der Schlüssel-Wert. Mit dem ASCII-Typ ist ungültig.|  
|**Strg + Alt + Umschalt**|Benutzer drücken vor dem Schlüssel-Wert STRG und ALT, UMSCHALT. Mit dem ASCII-Typ ist ungültig.|  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)