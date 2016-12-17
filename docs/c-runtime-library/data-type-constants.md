---
title: "Datentypkonstanten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "FLT_MIN"
  - "SHRT_MAX"
  - "CHAR_MIN"
  - "MB_LEN_MAX"
  - "DBL_EPSILON"
  - "SHRT_MIN"
  - "_FLT_RADIX"
  - "FLT_DIG"
  - "FLT_MAX_10_EXP"
  - "FLT_MANT_DIG"
  - "DBL_MAX_EXP"
  - "SCHAR_MIN"
  - "SCHAR_MAX"
  - "DBL_MIN"
  - "FLT_MIN_10_EXP"
  - "_DBL_ROUNDS"
  - "USHRT_MAX"
  - "FLT_MAX_EXP"
  - "LONG_MAX"
  - "DBL_MAX"
  - "DBL_DIG"
  - "FLT_MIN_EXP"
  - "INT_MIN"
  - "DBL_MIN_10_EXP"
  - "CHAR_BIT"
  - "INT_MAX"
  - "ULONG_MAX"
  - "DBL_MIN_EXP"
  - "LONG_MIN"
  - "_FLT_ROUNDS"
  - "DBL_MANT_DIG"
  - "_DBL_RADIX"
  - "CHAR_MAX"
  - "FLT_MAX"
  - "DBL_MAX_10_EXP"
  - "UCHAR_MAX"
  - "FLT_EPSILON"
  - "UINT_MAX"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_DBL_RADIX-Konstante"
  - "_DBL_ROUNDS-Konstante"
  - "_FLT_RADIX-Konstante"
  - "_FLT_ROUNDS-Konstante"
  - "CHAR_BIT-Konstante"
  - "CHAR_MAX-Konstante"
  - "CHAR_MIN-Konstante"
  - "Konstanten [C++], Datentyp"
  - "Datentypkonstanten [C++]"
  - "DBL_DIG-Konstante"
  - "DBL_EPSILON-Konstante"
  - "DBL_MANT_DIG-Konstante"
  - "DBL_MAX-Konstante"
  - "DBL_MAX_10_EXP-Konstante"
  - "DBL_MAX_EXP-Konstante"
  - "DBL_MIN-Konstante"
  - "DBL_MIN_10_EXP-Konstante"
  - "DBL_MIN_EXP-Konstante"
  - "DBL_RADIX-Konstante"
  - "DBL_ROUNDS-Konstante"
  - "FLT_DIG-Konstante"
  - "FLT_EPSILON-Konstante"
  - "FLT_MANT_DIG-Konstante"
  - "FLT_MAX-Konstante"
  - "FLT_MAX_10_EXP-Konstante"
  - "FLT_MAX_EXP-Konstante"
  - "FLT_MIN-Konstante"
  - "FLT_MIN_10_EXP-Konstante"
  - "FLT_MIN_EXP-Konstante"
  - "FLT_RADIX-Konstante"
  - "FLT_ROUNDS-Konstante"
  - "INT_MAX-Konstante"
  - "INT_MIN-Konstante"
  - "LONG_MAX-Konstante"
  - "LONG_MIN-Konstante"
  - "MB_LEN_MAX-Konstante"
  - "SCHAR_MAX-Konstante"
  - "SCHAR_MIN-Konstante"
  - "SHRT_MAX-Konstante"
  - "SHRT_MIN-Konstante"
  - "UCHAR_MAX-Konstante"
  - "UINT_MAX-Konstante"
  - "ULONG_MAX-Konstante"
  - "USHRT_MAX-Konstante"
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Datentypkonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Datentypkonstanten sind die implementierungsabhängigen Wertebereiche, die für ganzzahlige Datentypen ermöglicht werden.  Die Konstanten, unten aufgeführten werden, geben die Bereiche für die ganzzahligen Datentypen und werden in LIMITS.H. definiert.  
  
> [!NOTE]
>  Die \/J\- Compileroption wird der Standard `char`\-Typ zu `unsigned`.  
  
|Konstante|Wert|Bedeutung|  
|---------------|----------|---------------|  
|**SCHAR\_MAX**|127|Maximalwert signierter Wert `char`|  
|**SCHAR\_MIN**|–128|Mindest\- signierter Wert `char`|  
|**UCHAR\_MAX**|255 \(0xff\)|Maximaler Wert `unsigned char`|  
|**CHAR\_BIT**|8|Zahl Bits in `char`|  
|**USHRT\_MAX**|65535 \(0xffff\)|Maximaler Wert **unsigned short**|  
|**SHRT\_MAX**|32767|Maximaler **short**\-Wert \(mit Vorzeichen\)|  
|**SHRT\_MIN**|–32768|Minimaler **short**\-Wert \(mit Vorzeichen\)|  
|**UINT\_MAX**|4294967295 \(0xffffffff\)|Maximaler Wert `unsigned int`|  
|**ULONG\_MAX**|4294967295 \(0xffffffff\)|Maximaler Wert `unsigned long`|  
|**INT\_MAX**|2147483647|Maximaler Wert `int` \(mit Vorzeichen\)|  
|**INT\_MIN**|–2147483647–1|Minimaler `int`\-Wert \(mit Vorzeichen\)|  
|**LONG\_MAX**|2147483647|Maximaler **long**\-Wert \(mit Vorzeichen\)|  
|**LONG\_MIN**|–2147483647–1|Minimaler **long**\-Wert \(mit Vorzeichen\)|  
|**CHAR\_MAX**|127 \(255, wenn \/J\- Option verwendet\)|Maximaler Wert `char`|  
|**CHAR\_MIN**|\- 128 \(0, wenn \/J\- Option verwendet\)|Minimaler `char`\-Wert|  
|**MB\_LEN\_MAX**|2|Maximale Anzahl Bytes im die Mehrbyte\-Codepage `char`|  
|**\_I64\_MAX**|9223372036854775807|Maximaler **int64**\-Wert \(mit Vorzeichen\)|  
|**\_I64\_MIN**|\-9223372036854775807\-1|Minimaler **int64**\-Wert \(mit Vorzeichen\)|  
|**\_UI64\_MAX**|0xffffffffffffffff|Maximaler Wert **int64** \(ohne Vorzeichen\)|  
  
 Die folgenden Konstanten geben den Bereich und andere Eigenschaften der **double** und **float** Datentypen und werden in FLOAT.H definiert:  
  
|Konstante|Wert|**Beschreibung**|  
|---------------|----------|----------------------|  
|**DBL\_DIG**|15|\# von Dezimalstellen von Genauigkeit|  
|**DBL\_EPSILON**|2.2204460492503131e\-016|Am kleinsten dass **DBL\_EPSILON** 1,0\+\! \=1.0|  
|**DBL\_MANT\_DIG**|53|\# von Bits in der Mantisse|  
|**DBL\_MAX**|1.7976931348623158e\+308|Maximalwert|  
|**DBL\_MAX\_10\_EXP**|308|Maximaler dezimaler Exponent|  
|**DBL\_MAX\_EXP**|1024|Maximaler binärer Exponent|  
|**DBL\_MIN**|2.2250738585072014e\-308|Minimaler positiver Wert|  
|**DBL\_MIN\_10\_EXP**|\(\-307\)|Minimaler dezimaler Exponent|  
|**DBL\_MIN\_EXP**|\(–1021\)|Minimaler binärer Exponent|  
|**\_DBL\_RADIX**|2|Exponentenbasis|  
|**\_DBL\_ROUNDS**|1|Hinzufügungsrunden: neben|  
|**FLIGHT\_DIG**|6|Anzahl der Dezimalstellen von Genauigkeit|  
|**FLIGHT\_EPSILON**|1.192092896e\-07F|Am kleinsten dass **FLT\_EPSILON** 1,0\+\! \=1.0|  
|**FLIGHT\_MANT\_DIG**|24|Zahl Bits in der Mantisse|  
|**FLIGHT\_MAX**|3.402823466e\+38F|Maximalwert|  
|**FLIGHT\_MAX\_10\_EXP**|38|Maximaler dezimaler Exponent|  
|**FLIGHT\_MAX\_EXP**|128|Maximaler binärer Exponent|  
|**FLIGHT\_MIN**|1.175494351e\-38F|Minimaler positiver Wert|  
|**FLIGHT\_MIN\_10\_EXP**|\(–37\)|Minimaler dezimaler Exponent|  
|**FLIGHT\_MIN\_EXP**|\(–125\)|Minimaler binärer Exponent|  
|**FLIGHT\_RADIX**|2|Exponentenbasis|  
|**FLIGHT\_ROUNDS**|1|Hinzufügungsrunden: neben|  
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)