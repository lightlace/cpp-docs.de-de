---
title: Boxing (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3b9898b4a640d2f3aa4e38ceb621521ffb301fed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="boxing-ccli"></a>Boxing (C++/CLI)
Boxing ist der Prozess der Konvertierung von eines Werttyp in den Typ `object` oder auf einen beliebigen anderen Schnittstellentyp, der durch den Werttyp implementiert wird. Wenn die common Language Runtime (CLR) einen Werttyp, umschließt er den Wert in einer `System.Object` und auf dem verwalteten Heap gespeichert. Durch Unboxing wird der Werttyp aus dem Objekt extrahiert. Boxing ist implizit, Unboxing ist explizit.  
  
## <a name="related-articles"></a>Verwandte Artikel  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Vorgehensweise: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)|Beschreibt, wie Boxing für eine Variable explizit anfordern.|  
|[Vorgehensweise: Verwenden von gcnew zum Erstellen von Werttypen und für implizites Boxing](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Zeigt, wie `gcnew` einen geschachtelter Werttyp erstellen, die auf dem verwalteten Heap mit Garbage collection platziert werden können.|  
|[Vorgehensweise: Unboxing](../dotnet/how-to-unbox.md)|Zeigt, wie Unboxing und einen Wert ändern.|  
|[Standardumwandlungen und implizites Boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Zeigt, dass eine standardkonvertierung vom Compiler über eine Konvertierung ausgewählt wird, das Boxing erfordert.|  
|[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Der übergeordnete Artikel für .NET Programmieren in Visual C++-Dokumentation.|