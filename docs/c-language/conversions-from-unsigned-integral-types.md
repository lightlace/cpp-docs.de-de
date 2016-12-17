---
title: "Konvertierungen von ganzzahligen Typen ohne Vorzeichen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Datentypkonvertierung [C++], Ganzzahlen mit und ohne Vorzeichen"
  - "Ganze Zahlen, Konvertieren"
  - "Ganzzahlkonvertierungen, Von Typen ohne Vorzeichen"
  - "Typumwandlungen, Unter Einbeziehung von Ganzzahlen"
  - "Typkonvertierung [C++], Ganzzahlen mit und ohne Vorzeichen"
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Konvertierungen von ganzzahligen Typen ohne Vorzeichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine ganze Zahl ohne Vorzeichen wird durch Abschneiden der höherwertigen Bits zu einer kürzeren Zahl ohne oder mit Vorzeichen konvertiert, oder sie wird durch Nullerweiterung zu einer längeren Zahl ohne oder mit Vorzeichen konvertiert. Sie finden die Auflistung der Typen in der Tabelle [Konvertierungen von ganzzahligen Typen ohne Vorzeichen](#_clang_table_4..3).  
  
 Wenn der Ganzzahlwert in eine ganze Zahl mit Vorzeichen mit geringerer Größe tiefer gestuft wird, oder eine ganze Zahl ohne Vorzeichen in ihre entsprechende ganze Zahl mit Vorzeichen konvertiert wird, bleibt der Wert unverändert, wenn er im neuen Typ dargestellt werden kann.  Der dargestellte Wert ändert sich jedoch, wenn wie im folgenden Beispiel das Vorzeichenbit festgelegt wird.  
  
```  
int j;  
unsigned short k = 65533;  
  
j = k;  
printf_s( "%hd\n", j );   // Prints -3  
```  
  
 Wenn er nicht dargestellt werden kann, wird das Ergebnis durch die Implementierung definiert.  Weitere Informationen zur Verarbeitung von tiefer gestuften Ganzzahlen durch den C\-Compiler von Microsoft erhalten Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md).  Eine ganzzahlige Konvertierung oder eine Typumwandlung der ganzen Zahl führen zum selben Verhalten.  
  
 Werte ohne Vorzeichen werden so konvertiert, dass ihr Wert beibehalten und nicht direkt in C darstellbar ist.  Die einzige Ausnahme ist eine Konvertierung von `unsigned long` in **float**, welcher höchstens die niedrigen Bits verliert.  Andernfalls wird der Wert beibehalten, mit oder ohne Vorzeichen.  Wenn ein Wert des ganzzahligen Typs in einen Gleitkommawert konvertiert wird, und der Wert außerhalb des darstellbaren Bereichs liegt, ist das Ergebnis nicht definiert. Informationen über den Bereich für ganzzahlige Typen und Gleitkommatypen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).  
  
 In der folgenden Tabelle werden die Konvertierungen von ganzzahligen Typen ohne Vorzeichen zusammengefasst.  
  
### Konvertierungen von ganzzahligen Typen ohne Vorzeichen  
  
|Von|Zweck|Methode|  
|---------|-----------|-------------|  
|`unsigned char`|`char`|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|  
|`unsigned char`|**short**|Nullerweiterung|  
|`unsigned char`|**long**|Nullerweiterung|  
|`unsigned char`|**unsigned short**|Nullerweiterung|  
|`unsigned char`|`unsigned long`|Nullerweiterung|  
|`unsigned char`|**float**|Konvertieren zu **long**; **long** zu **float** konvertieren|  
|`unsigned char`|**double**|Konvertieren zu **long**; **long** zu **double** konvertieren|  
|`unsigned char`|`long double`|Konvertieren zu **long**; **long** zu **double** konvertieren|  
|**unsigned short**|`char`|Niederwertiges Byte beibehalten|  
|**unsigned short**|**short**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|  
|**unsigned short**|**long**|Nullerweiterung|  
|**unsigned short**|`unsigned char`|Niederwertiges Byte beibehalten|  
|**unsigned short**|`unsigned long`|Nullerweiterung|  
|**unsigned short**|**float**|Konvertieren zu **long**; **long** zu **float** konvertieren|  
|**unsigned short**|**double**|Konvertieren zu **long**; **long** zu **double** konvertieren|  
|**unsigned short**|`long double`|Konvertieren zu **long**; **long** zu **double** konvertieren|  
|`unsigned long`|`char`|Niederwertiges Byte beibehalten|  
|`unsigned long`|**short**|Niederwertiges Wort beibehalten|  
|`unsigned long`|**long**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|  
|`unsigned long`|`unsigned char`|Niederwertiges Byte beibehalten|  
|`unsigned long`|**unsigned short**|Niederwertiges Wort beibehalten|  
|`unsigned long`|**float**|Konvertieren zu **long**; **long** zu **float** konvertieren|  
|`unsigned long`|**double**|Direkt in **double** konvertieren|  
|`unsigned long`|`long double`|Konvertieren zu **long**; **long** zu **double** konvertieren|  
  
 **Microsoft\-spezifisch**  
  
 Für den 32\-Bit\-C\-Compiler von Microsoft ist der `unsigned int`\-Typ gleich dem `unsigned long`\-Typ.  Die Konvertierung eines `unsigned int`\-Werts wird auf dieselbe Weise wie die Konvertierung eines `unsigned long`\-Werts ausgeführt.  Konvertierungen von `unsigned long`\-Werten in **float**\-Werte sind nicht genau, wenn der Wert, der konvertiert wird, größer als der maximale positive **long**\-Wert mit Vorzeichen ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)