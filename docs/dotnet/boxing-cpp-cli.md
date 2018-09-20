---
title: Boxing (C++ / CLI) | Microsoft-Dokumentation
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
ms.openlocfilehash: 4c513b0148e2553440e02f9b0d255a0d5750e2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372511"
---
# <a name="boxing-ccli"></a>Boxing (C++/CLI)

Boxing ist der Prozess der Konvertierung eines Werttyps in den Typ `object` oder einen beliebigen anderen Schnittstellentyp, der durch den Werttyp implementiert wird. Wenn die common Language Runtime (CLR) auf einen Werttyp schachtelt, umschließt er den Wert in eine `System.Object` und speichert sie auf dem verwalteten Heap. Durch Unboxing wird der Werttyp aus dem Objekt extrahiert. Boxing ist implizit, Unboxing ist explizit.

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Vorgehensweise: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)|Beschreibt, wie Boxing in einer Variable explizit anfordern.|
|[Vorgehensweise: Verwenden von gcnew zum Erstellen von Werttypen und für implizites Boxing](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Zeigt, wie `gcnew` ein geschachtelten Werttyps zu erstellen, die auf dem verwalteten Heap mit Garbage collection platziert werden können.|
|[Vorgehensweise: Unboxing](../dotnet/how-to-unbox.md)|Zeigt, wie mittels Unboxing zu konvertieren, und ändern einen Wert.|
|[Standardumwandlungen und implizites Boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Zeigt, dass eine standardkonvertierung vom Compiler eine Konvertierung ausgewählt ist, das Boxing erforderlich.|
|[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Der übergeordnete Artikel für .NET-Programmierung in Visual C++-Dokumentation.|