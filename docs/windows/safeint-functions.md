---
title: SafeInt-Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
caps.latest.revision: "13"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ae482b7f58d64a46b82b32c6c6d62d7f69f0dce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="safeint-functions"></a>SafeInt-Funktionen
SafeInt-Bibliothek stellt mehrere Funktionen, die Sie verwenden können, ohne das Erstellen einer Instanz von der [SafeInt-Klasse](../windows/safeint-class.md). Wenn Sie einen einzelnen mathematischen Vorgang vor Ganzzahlüberlauf schützen möchten, können Sie diese Funktionen verwenden. Wenn Sie mehrere mathematische Vorgänge zu schützen möchten, sollten Sie erstellen `SafeInt` Objekte. Es ist jedoch effizienter erstellen `SafeInt` Objekte als die Verwendung dieser Funktionen mehrmals.  
  
 Diese Funktionen ermöglichen es Ihnen zu vergleichen oder mathematische Operationen an zwei verschiedene Arten von Parametern ausführen, ohne sie zuerst auf den gleichen Typ zu konvertieren.  
  
 Jede dieser Funktionen hat zwei Vorlagentypen: `T` und `U`. Jeder dieser Typen kann es sich um ein boolescher Wert, Zeichen- oder Ganzzahltyp sein. Ganzzahltypen mit oder ohne Vorzeichen sein können und beliebiger Größe von 8 Bit zu 64 Bit.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|Addiert zwei Zahlen und schützt vor Ganzzahlüberlauf.|  
|[safecast](../windows/safecast.md)|Wandelt einen Typ des Parameters in einen anderen Typ.|  
|[SafeDivide](../windows/safedivide.md)|Dividiert zwei Zahlen und Schutz vor einer Division durch 0 (null).|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [SafeNotEquals](../windows/safenotequals.md)|Vergleicht zwei Zahlen. Diese Funktionen ermöglichen es Ihnen, zwei verschiedene Arten von Zahlen verglichen werden soll, ohne ihre Typen ändern.|  
|[SafeModulus](../windows/safemodulus.md)|Führt die Modulo-Operation für zwei Zahlen.|  
|[SafeMultiply](../windows/safemultiply.md)|Multipliziert zwei Zahlen miteinander und schützt vor Ganzzahlüberlauf.|  
|[SafeSubtract](../windows/safesubtract.md)|Subtrahiert zwei Zahlen und schützt vor Ganzzahlüberlauf.|  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Bereich|Beschreibung|  
|-------------|-----------------|  
|[SafeInt-Klasse](../windows/safeint-class.md)|Der `SafeInt`-Klasse.|  
|[SafeIntException-Klasse](../windows/safeintexception-class.md)|Die Exception-Klasse, die spezifisch für die SafeInt-Bibliothek.|