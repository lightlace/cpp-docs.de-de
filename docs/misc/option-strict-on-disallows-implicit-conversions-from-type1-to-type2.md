---
title: "Option Strict On l&#228;sst keine impliziten Konvertierungen von &#39;&lt;Typ1&gt;&#39; in &#39;&lt;Typ2&gt;&#39; zu"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30512"
  - "vbc30512"
helpviewer_keywords: 
  - "BC30512"
ms.assetid: b9756d48-05fa-4027-8a80-b4a0ef92099d
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On l&#228;sst keine impliziten Konvertierungen von &#39;&lt;Typ1&gt;&#39; in &#39;&lt;Typ2&gt;&#39; zu
Sie haben versucht, einen Typ in einen anderen Typ zu konvertieren, der den Wert möglicherweise nicht enthalten kann, z. B. `Long` zu `Integer`, während der Schalter für die Typüberprüfung \([Option Strict Statement](../Topic/Option%20Strict%20Statement.md)\) auf `On` festgelegt ist.  
  
 Diese Art der Konvertierung wird als *einschränkende Konvertierung* bezeichnet, bei der es möglich ist, dass zur Laufzeit Fehler auftreten. Aus diesem Grund gestattet `Option Strict On` keine impliziten einschränkenden Konvertierungen.  
  
 **Fehler\-ID:** BC30512  
  
### So beheben Sie diesen Fehler  
  
1.  Ermitteln Sie, ob eine Konvertierung eines beliebigen Typs von `<type1>` in `<type2>` vorhanden ist. Wenn beide Type elementare Typen von [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] oder Instanzen von Klassen sind, können Sie diese Ermittlung in der Regel über die Tabelle in [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md) vornehmen.  
  
2.  Wenn nur eine einschränkende Konvertierung von `<type1>` in `<type2>` vorhanden ist, sollten Sie die explizite Umwandlung verwenden. Die Schlüsselwörter [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md) und [DirectCast Operator](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md) lösen zur Laufzeit eine Ausnahme aus, wenn die Konvertierung fehlschlägt. Das Schlüsselwort [TryCast Operator](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md) gilt nur für Verweistypen und es gibt [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md) zurück, wenn bei der Konvertierung ein Fehler auftritt.  
  
3.  Wenn eine einschränkende Konvertierung vorhanden ist und Ihr Programm einen Laufzeitfehler tolerieren kann oder Sie zuversichtlich sind, dass ein Laufzeitfehler nicht möglich ist, können Sie `Option Strict Off` am Anfang des Quellcodes angeben. Aber Sie sollten die Konvertierung immer noch in einen [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)\-Block einschließen, um unerwartete Ergebnisse oder eine vorzeitige Beendigung des Programms zu vermeiden.  
  
4.  Wenn keine Konvertierung von `<type1>` in `<type2>` vorhanden ist, müssen Sie die Programmlogik neu bewerten. Möglicherweise können Sie einen Code schreiben, mit dem Werte zu `<type2>` zugeordnet werden, die erwarteten Werten von `<type1>` entsprechen.  
  
5.  Wenn keine Konvertierung von `<type1>` in `<type2>` vorhanden ist und einer der Typen einer von Ihnen definierten Klasse oder Struktur entspricht, können Sie möglicherweise einen Konvertierungsoperator dieses Typs für die Konvertierung in den \(oder aus dem\) anderen Typ definieren. Weitere Informationen finden Sie unter [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md).  
  
6.  In sämtlichen Fällen und als allgemeine Richtlinie sollten Sie einschränkende Konvertierungen nur verwenden, wenn Sie Fehler in einem `Catch`\-Block abfangen und effektiv behandeln können.  
  
## Siehe auch  
 [Option Strict Statement](../Topic/Option%20Strict%20Statement.md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [DirectCast Operator](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [TryCast Operator](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md)   
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)