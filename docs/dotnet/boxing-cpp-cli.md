---
title: "Boxing (C++/CLI)"
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
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# Boxing (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Boxing ist der Prozess der Konvertierung eines Werttyps in den Typ `object` oder auf ein Schnittstellentyp, der durch den Werttyp implementiert wird.  Wenn die Common Language Runtime \(CLR\) ein Werttyp einpackt, wird sie den Wert in ein `System.Object` und speichert ihn auf dem verwalteten Heap.  Durch Unboxing wird der Werttyp aus dem Objekt extrahiert.  Boxing ist implizit, Unboxing ist explizit.  
  
## Verwandte Artikel  
  
|Titel|**Beschreibung**|  
|-----------|----------------------|  
|[Gewusst wie: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)|Beschreibt, wie auf eine Variable explizit Boxing erfordert.|  
|[Gewusst wie: Verwenden von gcnew zum Erstellen von Werttypen und für implizites Boxing](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Zeigt, wie `gcnew` verwendet, um einen verschachtelten Werttyp, der auf das verwaltete abgelegt werden kann, aus der Garbage Collection zu erstellen.|  
|[Gewusst wie: Unboxing](../dotnet/how-to-unbox.md)|Zeigt, wie ein Wert konvertiert und ändert.|  
|[Standardumwandlungen und implizites Boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Stellt dar, dass eine Standardkonvertierung vom Compiler einer Konvertierung ausgewählt wird, die Boxing erfordert.|  
|[.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Der Artikel der obersten Ebene für .NET, das in der Visual C\+\+\-Dokumentation Programmierung.|