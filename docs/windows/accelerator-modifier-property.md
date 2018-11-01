---
title: Accelerator-Modifier-Eigenschaft (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
ms.openlocfilehash: f9dfcbde68d2b3d1ebdd1b94aa40339bbc0ff4e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650678"
---
# <a name="accelerator-modifier-property-c"></a>Accelerator-Modifier-Eigenschaft (C++)

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

[Festlegen von Eigenschaften für Zugriffstasten](../windows/setting-accelerator-properties.md)<br/>
[Zugriffstasten-Editor](../windows/accelerator-editor.md)