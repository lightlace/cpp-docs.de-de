---
title: Konvertierungen von integraler Typen mit Vorzeichen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8977c70fc2ebdc6e9fccf22e44a04afaceae1392
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="conversions-from-signed-integral-types"></a>Konvertierungen von ganzzahligen Typen mit Vorzeichen
Wenn eine ganze Zahl mit Vorzeichen in eine ganze Zahl ohne Vorzeichen mit der gleichen Größe oder länger konvertiert wird und der Wert der ganzen Zahl mit Vorzeichen nicht negativ ist, bleibt der Wert unverändert. Die Konvertierung erfolgt durch Zeichenerweiterung der ganzen Zahl mit Vorzeichen. Eine ganze Zahl mit Vorzeichen wird in eine kürzere Zahl mit Vorzeichen konvertiert, indem die höherwertigen Bits abgeschnitten werden. Das Ergebnis wird als Wert ohne Vorzeichen interpretiert, wie in diesem Beispiel gezeigt wird.  
  
```  
int i = -3;  
unsigned short u;  
  
u = i;   
printf_s( "%hu\n", u );  // Prints 65533  
  
```  
  
 Beim Konvertieren einer Ganzzahl mit Vorzeichen in einen Gleitkommawert gehen keine Informationen verloren, wenn jedoch ein **long int**- oder **unsigned long int**-Wert in einen **float**-Wert konvertiert wird, wirkt sich dies geringfügig auf die Genauigkeit aus.  
  
 In der folgenden Tabelle sind die Konvertierungen von ganzzahligen Typen mit Vorzeichen zusammengefasst. In dieser Tabelle wird davon ausgegangen, dass der Typ **char** standardmäßig ein Vorzeichen hat. Wenn Sie eine Kompilierzeitoption verwenden, um den Standardwert für den **char**-Typ in einen Typ ohne Vorzeichen zu ändern, gelten die Konvertierungen aus der Tabelle [Conversions from Unsigned Integral Types (Konvertierungen von integralen Typen ohne Vorzeichen)](../c-language/conversions-from-unsigned-integral-types.md) für den Typ **unsigned char** anstelle der Konvertierungen in der folgenden Tabelle „Konvertierungen von integralen Typen mit Vorzeichen“.  
  
### <a name="conversions-from-signed-integral-types"></a>Konvertierungen von ganzzahligen Typen mit Vorzeichen  
  
|Von|Beschreibung|Methode|  
|----------|--------|------------|  
|**char**1|**short**|Signaturerweiterung|  
|**char**|**long**|Signaturerweiterung|  
|**char**|**unsigned char**|Muster beibehalten; oberes Bit verliert Funktion als Vorzeichenbit|  
|**char**|**unsigned short**|Signaturerweiterung auf **short**; Konvertieren von **short** in **unsigned short**|  
|**char**|**unsigned long**|Signaturerweiterung auf **long**; Konvertieren von **long** in **unsigned long**|  
|**char**|**float**|Signaturerweiterung auf **long**; Konvertieren von **long** in **float**|  
|**char**|**double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|  
|**char**|**long double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|  
|**short**|**char**|Niederwertiges Byte beibehalten|  
|**short**|**long**|Signaturerweiterung|  
|**short**|**unsigned char**|Niederwertiges Byte beibehalten|  
|**short**|**unsigned short**|Bitmuster beibehalten; höherwertiges Bit verliert Funktion als Vorzeichenbit|  
|**short**|**unsigned long**|Signaturerweiterung auf **long**; Konvertieren von **long** in **unsigned long**|  
|**short**|**float**|Signaturerweiterung auf **long**; Konvertieren von **long** in **float**|  
|**short**|**double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|  
|**short**|**long double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|  
|**long**|**char**|Niederwertiges Byte beibehalten|  
|**long**|**short**|Niederwertiges Wort beibehalten|  
|**long**|**unsigned char**|Niederwertiges Byte beibehalten|  
|**long**|**unsigned short**|Niederwertiges Wort beibehalten|  
|**long**|**unsigned long**|Bitmuster beibehalten; höherwertiges Bit verliert Funktion als Vorzeichenbit|  
|**long**|**float**|Darstellen als **float**. Wenn **long** nicht genau dargestellt werden kann, wirkt sich dies geringfügig auf die Genauigkeit aus.|  
|**long**|**double**|Darstellen als **double**. Wenn **long** nicht genau als **double** dargestellt werden kann, wirkt sich dies geringfügig auf die Genauigkeit aus.|  
|**long**|**long double**|Darstellen als **double**. Wenn **long** nicht genau als **double** dargestellt werden kann, wirkt sich dies geringfügig auf die Genauigkeit aus.|  
  
 1. Bei allen **char**-Einträgen wird davon ausgegangen, dass der **char**-Typ standardmäßig ein Vorzeichen hat.  
  
 **Microsoft-spezifisch**  
  
 Für den 32-Bit-C-Compiler von Microsoft ist eine ganze Zahl gleichbedeutend mit **long**. Konvertierung eines **int**-Werts erfolgt auf dieselbe Weise wie bei **long**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)