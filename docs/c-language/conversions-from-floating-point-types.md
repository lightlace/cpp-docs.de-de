---
title: "Konvertierungen von Gleitkommatypen"
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
  - "Konvertieren von Gleitkommazahlen"
  - "Gleitkommakonvertierung"
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Konvertierungen von Gleitkommatypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein **float**\-Wert, der in einen **double**\- oder `long double`\-Wert konvertiert wird, oder ein **double**\-Wert, der in einen `long double`\-Wert konvertiert wird, erfährt keine Änderung des Werts.  Ein **double**\-Wert, der in einen **float**\-Wert konvertiert wird, wird exakt dargestellt, sofern dies möglich ist.  Genauigkeit geht möglicherweise verloren, wenn der Wert nicht exakt dargestellt werden kann.  Wenn das Ergebnis außerhalb des gültigen Bereichs liegt, ist das Verhalten nicht definiert.  Weitere Informationen über den Bereich von Gleitkommatypen erhalten Sie unter [Grenzwerte für Gleitkommakonstanten](../c-language/limits-on-floating-point-constants.md).  
  
 Ein Gleitkommawert wird in einen ganzzahligen Wert konvertiert, indem er zuerst in einen **long**\-Wert und dann von dem **long**\-Wert in den spezifischen ganzzahligen Wert konvertiert wird.  Die Nachkommastellen des Gleitkommawerts werden bei der Konvertierung in **long** verworfen.  Wenn das Ergebnis immer noch zu groß ist, um in **long** zu passen, ist das Ergebnis der Konvertierung nicht definiert.  
  
 **Microsoft\-spezifisch**  
  
 Wenn eine **double**\- oder `long double`\-Gleitkommazahl in eine kleinere Gleitkommazahl umgewandelt wird und ein Unterlauf auftritt, wird der Wert der Gleitkommavariablen in Richtung 0 \(null\) abgeschnitten.  Ein Überlauf verursacht einen Laufzeitfehler.  Beachten Sie, dass der Microsoft C\-Compiler `long double` dem Typ **double** zuordnet.  
  
 **END Microsoft\-spezifisch**  
  
 In der folgenden Tabelle werden die Konvertierungen von Gleitkommatypen zusammengefasst.  
  
### Konvertierungen von Gleitkommatypen  
  
|Von|Zweck|Methode|  
|---------|-----------|-------------|  
|**float**|`char`|Konvertieren zu **long**; Konvertieren von **long** zu `char`|  
|**float**|**short**|Konvertieren zu **long**; Konvertieren von **long** zu **short**|  
|**float**|**long**|Beim Dezimaltrennzeichen abschneiden.  Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|  
|**float**|**unsigned short**|Konvertieren zu **long**; Konvertieren von **long** zu `unsigned` **short**|  
|**float**|`unsigned long`|Konvertieren zu **long**; Konvertieren von **long** zu `unsigned` **long**|  
|**float**|**double**|Ändern der internen Darstellung|  
|**float**|`long double`|Ändern der internen Darstellung|  
|**double**|`char`|Konvertieren zu **float**; Konvertieren von **float** zu `char`|  
|**double**|**short**|Konvertieren zu **float**; Konvertieren von **float** zu **short**|  
|**double**|**long**|Beim Dezimaltrennzeichen abschneiden.  Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|  
|**double**|**unsigned short**|Konvertieren zu **long**; Konvertieren von **long** zu **unsigned short**|  
|**double**|`unsigned long`|Konvertieren zu **long**; Konvertieren von **long** zu `unsigned` **long**|  
|**double**|**float**|Darstellen als **float**.  Wenn ein **double**\-Wert nicht exakt als **float** dargestellt werden kann, tritt ein Genauigkeitsverlust auf.  Wenn der Wert zu groß ist, um als **float** dargestellt zu werden, ist das Ergebnis nicht definiert.|  
|`long double`|`char`|Konvertieren zu **float**; Konvertieren von **float** zu `char`|  
|`long double`|**short**|Konvertieren zu **float**; Konvertieren von **float** zu **short**|  
|`long double`|**long**|Beim Dezimaltrennzeichen abschneiden.  Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|  
|`long double`|**unsigned short**|Konvertieren zu **long**; Konvertieren von **long** zu `unsigned` **short**|  
|`long double`|`unsigned long`|Konvertieren zu **long**; Konvertieren von **long** zu `unsigned` **long**|  
|`long double`|**float**|Darstellen als **float**.  Wenn ein **double**\-Wert nicht exakt als **float** dargestellt werden kann, tritt ein Genauigkeitsverlust auf.  Wenn der Wert zu groß ist, um als **float** dargestellt zu werden, ist das Ergebnis nicht definiert.|  
|`long double`|**double**|Der Wert **long double** wird als **double** behandelt.|  
  
 Konvertierungen von **float**, **double** oder `long double`\-Werten zu `unsigned long` sind nicht genau, wenn der Wert, der konvertiert wird, größer als der maximale positive **long**\-Wert ist.  
  
## Siehe auch  
 [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)