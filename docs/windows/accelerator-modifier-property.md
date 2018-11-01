---
title: Accelerator-Modifier-Eigenschaft (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: 3c053af58842c75910b0214ae828c652daa33a81
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389290"
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