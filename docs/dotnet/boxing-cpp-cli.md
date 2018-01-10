---
title: Boxing (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e49c6f82099e6d7dbcfc47079d19228d7a91dc05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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