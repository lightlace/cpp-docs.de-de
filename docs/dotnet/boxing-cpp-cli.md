---
title: Boxing (C++/CLI)
ms.date: 11/04/2016
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
ms.openlocfilehash: 3f756eaef59c24ca5b82c485bd8352dffe9fb1db
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345765"
---
# <a name="boxing-ccli"></a>Boxing (C++/CLI)

Boxing ist der Prozess der Konvertierung eines Werttyps in den Typ `object` oder einen beliebigen anderen Schnittstellentyp, der durch den Werttyp implementiert wird. Wenn die common Language Runtime (CLR) auf einen Werttyp schachtelt, umschließt er den Wert in eine `System.Object` und speichert sie auf dem verwalteten Heap. Durch Unboxing wird der Werttyp aus dem Objekt extrahiert. Boxing ist implizit, Unboxing ist explizit.

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Vorgehensweise: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)|Beschreibt, wie Boxing in einer Variable explizit anfordern.|
|[Vorgehensweise: Verwenden von gcnew zum Erstellen von Werttypen und für implizites Boxing](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Zeigt, wie `gcnew` ein geschachtelten Werttyps zu erstellen, die auf dem verwalteten Heap mit Garbage collection platziert werden können.|
|[Vorgehensweise: Anwenden von Unboxing](../dotnet/how-to-unbox.md)|Zeigt, wie mittels Unboxing zu konvertieren, und ändern einen Wert.|
|[Standardumwandlungen und implizites Boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Zeigt, dass eine standardkonvertierung vom Compiler eine Konvertierung ausgewählt ist, das Boxing erforderlich.|
|[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Der übergeordnete Artikel für .NET-Programmierung in Visual C++-Dokumentation.|