---
title: Konvertierungen von Gleitkommatypen | Microsoft-Dokumentation
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80e84ba9a78f78fd93d7bd7fedbcbfaf168a7ec2
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="conversions-from-floating-point-types"></a>Konvertierungen von Gleitkommatypen

Bei einem **float**-Wert, der in einen **double**- oder **long double**-Wert konvertiert wird, oder einem **double**-Wert, der in einen **long double**-Wert konvertiert wird, wird keine Änderung des Werts vorgenommen. Ein **double**-Wert, der in einen **float**-Wert konvertiert wird, wird exakt dargestellt, sofern dies möglich ist. Genauigkeit geht möglicherweise verloren, wenn der Wert nicht exakt dargestellt werden kann. Wenn das Ergebnis außerhalb des gültigen Bereichs liegt, ist das Verhalten nicht definiert. Weitere Informationen über den Bereich von Gleitkommatypen erhalten Sie unter [Grenzwerte für Gleitkommakonstanten](../c-language/limits-on-floating-point-constants.md).

Ein Gleitkommawert wird in einen ganzzahligen Wert konvertiert, indem er zuerst in einen **long**-Wert und dann von dem **long**-Wert in den spezifischen ganzzahligen Wert konvertiert wird. Die Nachkommastellen des Gleitkommawerts werden bei der Konvertierung in **long** verworfen. Wenn das Ergebnis immer noch zu groß ist, um in **long** zu passen, ist das Ergebnis der Konvertierung nicht definiert.

**Microsoft-spezifisch**

Wenn eine **double**- oder **long double**-Gleitkommazahl in eine kleinere Gleitkommazahl umgewandelt wird und ein Unterlauf auftritt, wird der Wert der Gleitkommavariable in Richtung null abgeschnitten. Ein Überlauf verursacht einen Laufzeitfehler. Beachten Sie, dass beim Microsoft C-Compiler **long double** dem Typ **double** zuordnet wird.

**Ende Microsoft-spezifisch**

In der folgenden Tabelle werden die Konvertierungen von Gleitkommatypen zusammengefasst.

## <a name="conversions-from-floating-point-types"></a>Konvertierungen von Gleitkommatypen

|Von|Beschreibung|Methode|
|----------|--------|------------|
|**float**|**char**|Konvertieren in **long**; Konvertieren von **long** in **char**|
|**float**|**short**|Konvertieren in **long**; Konvertieren von **long** in **short**|
|**float**|**long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**float**|**unsigned short**|Konvertieren in **long**; Konvertieren von **long** in **unsigned short**|
|**float**|**unsigned long**|Konvertieren in **long**; Konvertieren von **long** in **unsigned long**|
|**float**|**double**|Ändern der internen Darstellung|
|**float**|**long double**|Ändern der internen Darstellung|
|**double**|**char**|Konvertieren in **float**; Konvertieren von **float** in **char**|
|**double**|**short**|Konvertieren in **float**; Konvertieren von **float** in **short**|
|**double**|**long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**double**|**unsigned short**|Konvertieren in **long**; Konvertieren von **long** in **unsigned short**|
|**double**|**unsigned long**|Konvertieren in **long**; Konvertieren von **long** in **unsigned long**|
|**double**|**float**|Darstellen als **float**. Wenn ein **double**-Wert nicht exakt als **float** dargestellt werden kann, tritt ein Genauigkeitsverlust auf. Wenn der Wert zu groß ist, um als **float** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**long double**|**char**|Konvertieren in **float**; Konvertieren von **float** in **char**|
|**long double**|**short**|Konvertieren in **float**; Konvertieren von **float** in **short**|
|**long double**|**long**|Beim Dezimaltrennzeichen abschneiden. Wenn das Ergebnis zu groß ist, um als **long** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**long double**|**unsigned short**|Konvertieren in **long**; Konvertieren von **long** in **unsigned short**|
|**long double**|**unsigned long**|Konvertieren in **long**; Konvertieren von **long** in **unsigned long**|
|**long double**|**float**|Darstellen als **float**. Wenn ein **double**-Wert nicht exakt als **float** dargestellt werden kann, tritt ein Genauigkeitsverlust auf. Wenn der Wert zu groß ist, um als **float** dargestellt zu werden, ist das Ergebnis nicht definiert.|
|**long double**|**double**|Der Wert **long double** wird als **double** behandelt.|

Konvertierungen von **float**, **double** oder **long double**-Werten in **unsigned long** sind nicht genau, wenn der Wert, der konvertiert wird, größer als der maximale positive **long**-Wert ist.

## <a name="see-also"></a>Siehe auch

[Zuweisungskonvertierungen](../c-language/assignment-conversions.md)  
