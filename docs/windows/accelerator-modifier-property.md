---
title: Eigenschaft "Modifizierer" Accelerator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0788536e776661b9a84a6cccc648a7db68389ae5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644254"
---
# <a name="accelerator-modifier-property"></a>Eigenschaft "Modifizierer" von Zugriffstasten
Die folgenden sind Einträge zulässig für die Eigenschaft "Modifizierer" in der tastenkombinationstabelle.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**Keine**|Benutzer drückt nur die **Schlüssel** Wert. Dies ist am effizientesten mit den ASCII/ANSI-Werten 001 bis 026, was interpretiert wird als ^ A bis ^ Z (STRG + A über STRG + Z).|  
|**ALT**|Drücken Sie die Benutzer muss die **Alt** Schlüssel vor der **Schlüssel** Wert.|  
|**STRG**|Drücken Sie die Benutzer muss die **STRG** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|  
|**UMSCHALTTASTE**|Drücken Sie die Benutzer muss die **UMSCHALT** Schlüssel vor der **Schlüssel** Wert.|  
|**Strg + Alt +**|Drücken Sie die Benutzer muss die **STRG** Schlüssel und die **Alt** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|  
|**STRG + UMSCHALT**|Drücken Sie die Benutzer muss die **STRG** Schlüssel und die **UMSCHALT** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|  
|**ALT + UMSCHALT**|Drücken Sie die Benutzer muss die **Alt** Schlüssel und die **UMSCHALT** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|  
|**Strg + Alt + Umschalt**|Der Benutzer muss drücken **STRG**, **Alt**, und **UMSCHALT** vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)