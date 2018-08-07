---
title: SafeInt-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b8a0475b5d3ba9053cd5d2df5ffd99ce9292ba8e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603454"
---
# <a name="safeint-functions"></a>SafeInt-Funktionen
Die SafeInt-Bibliothek stellt mehrere Funktionen, die Sie verwenden können, ohne eine Instanz des der [SafeInt-Klasse](../windows/safeint-class.md). Wenn Sie einen einzelnen mathematischen Vorgang vor Ganzzahlüberlauf schützen möchten, können Sie diese Funktionen. Wenn Sie mehrere mathematische Vorgänge schützen möchten, sollten Sie erstellen **SafeInt** Objekte. Es ist jedoch effizienter erstellen **SafeInt** Objekte, anstatt diese Funktionen mehrmals.  
  
 Diese Funktionen können Sie vergleichen oder die mathematische Operationen für zwei verschiedene Arten von Parametern ausführen, ohne sie zuerst auf den gleichen Typ konvertieren zu müssen.  
  
 Jede dieser Funktionen hat zwei Vorlagentypen: `T` und `U`. Jeder dieser Typen kann ein boolescher Wert, Zeichen oder ganzzahliger Typ sein. Ganzzahltypen mit oder ohne Vorzeichen werden können und beliebiger Größe von 8 Bits bis 64 Bits.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|Addiert zwei Zahlen und schützt vor Ganzzahlüberlauf.|  
|[safecast](../windows/safecast.md)|Wandelt einen Typ des Parameters in einen anderen Typ.|  
|[SafeDivide](../windows/safedivide.md)|Dividiert zwei Zahlen und schützt vor Division durch 0 (null).|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|Vergleicht zwei Zahlen. Diese Funktionen können Sie zwei verschiedene Arten von Zahlen zu vergleichen, ohne ihre Typen ändern.|  
|[SafeModulus](../windows/safemodulus.md)|Führt die Modulo-Operation für zwei Zahlen.|  
|[SafeMultiply](../windows/safemultiply.md)|Multipliziert zwei Zahlen zusammen und schützt vor Ganzzahlüberlauf.|  
|[SafeSubtract](../windows/safesubtract.md)|Subtrahiert zwei Zahlen und schützt vor Ganzzahlüberlauf.|  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Bereich|Beschreibung|  
|-------------|-----------------|  
|[SafeInt-Klasse](../windows/safeint-class.md)|Die **SafeInt** Klasse.|  
|[SafeIntException-Klasse](../windows/safeintexception-class.md)|Die Exception-Klasse, die spezifisch für die SafeInt-Bibliothek.|