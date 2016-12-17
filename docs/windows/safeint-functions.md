---
title: "SafeInt-Funktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionen, SafeInt"
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeInt-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die SafeInt\-Bibliothek stellt mehrere Funktionen, die Sie verwenden können, ohne eine Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  Wenn Sie einen einzelnen mathematischen Vorgang vom Ganzzahlüberlauf schützen möchten, können diese Funktionen verwenden.  Wenn Sie mehrere mathematische Operationen schützen möchten, sollten Sie `SafeInt`\-Objekte erstellen.  Es ist effizienter, Objekte als `SafeInt` zu erstellen, diese Funktionen mehrmals zu verwenden.  
  
 Diese Funktionen ermöglichen Ihnen, die mathematische Operationen auf zwei verschiedene Typen Parameter vergleichen oder ausführen, ohne zu müssen, sie demselben Typ zuerst zu konvertieren.  
  
 Jede dieser Funktionen verfügt über zwei Vorlagentypen: `T` und `U`.  Jeder dieser Typen kann ein boolescher Wert, ein Zeichen oder ein ganzzahliger Typ sein ein.  Ganzzahlige Typen können mit oder ohne Vorzeichen und jede Größe von 8 Bits auf 64 Bits sein.  
  
## In diesem Abschnitt  
  
|Funktion|**Beschreibung**|  
|--------------|----------------------|  
|[SafeAdd](../windows/safeadd.md)|Addiert zwei Zahlen hinzu und schützt Überlauf.|  
|[SafeCast](../windows/safecast.md)|Typumwandlungen ein Typ Parameter einem anderen Typ.|  
|[SafeDivide](../windows/safedivide.md)|Dividiert zwei Zahlen und schützt das Unterteilen durch null.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [SafeNotEquals](../windows/safenotequals.md)|Vergleicht zwei Zahlen.  Diese Funktionen ermöglichen, dass zwei verschiedene Typen Zahlen vergleichen, ohne ihre Typen ändern.|  
|[SafeModulus](../windows/safemodulus.md)|Führt den Modulo\-Vorgang auf zwei Zahlen aus.|  
|[SafeMultiply](../windows/safemultiply.md)|Multipliziert zwei Zahlen zusammen und schützt Überlauf.|  
|[SafeSubtract](../windows/safesubtract.md)|Subtrahiert zwei Zahlen und schützt Überlauf.|  
  
## Verwandte Abschnitte  
  
|Abschnitt|**Beschreibung**|  
|---------------|----------------------|  
|[SafeInt\-Klasse](../windows/safeint-class.md)|Die `SafeInt`\-Klasse.|  
|[SafeIntException\-Klasse](../windows/safeintexception-class.md)|Das Ausnahmeklassenbesondere zur SafeInt\-Bibliothek.|