---
title: Skalare Typen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b0915637025e176ee98d01be3991b30b4e6544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="scalar-types"></a>Skalare Typen
Obwohl der Zugriff auf Daten aus jeder Ausrichtung ergeben kann, empfiehlt es sich, dass die Daten auf die natürliche Begrenzung zur Vermeidung von Leistung Verlust (oder ein Vielfaches davon) ausgerichtet werden. Enumerationen sind Konstante ganze Zahlen und werden als 32-Bit-Ganzzahlen behandelt. Die folgende Tabelle beschreibt die Typdefinition und empfohlene Speicher dafür, wie sie mithilfe der folgenden Ausrichtungswerte der Ausrichtung bezieht sich:  
  
-   Byte - 8-Bit  
  
-   Word - 16 Bits lang sein  
  
-   Doppelwort - 32-Bit  
  
-   Quad-Word - 64-Bit  
  
-   Octa Word - 128-Bit  
  
|||||  
|-|-|-|-|  
|Skalaren Typ|C-Datentyp|Speichergröße (in Byte)|Empfohlene Ausrichtung|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**Int, long**|4|Doppelwort|  
|**UINT32**|**unsigned Int unsigned long**|4|Doppelwort|  
|**INT64-TYP**|`__int64`|8|Vierfachwort|  
|**UINT64**|**__int64 ohne Vorzeichen**|8|Vierfachwort|  
|**FP32 (einfache Genauigkeit)**|**float**|4|Doppelwort|  
|**FP64 (doppelte Genauigkeit)**|**double**|8|Vierfachwort|  
|**ZEIGER**|**\***|8|Vierfachwort|  
|`__m64`|**Struktur __m64**|8|Vierfachwort|  
|`__m128`|**Struktur __m128**|16|Octaword|  
  
## <a name="see-also"></a>Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)