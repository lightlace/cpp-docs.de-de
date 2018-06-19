---
title: Datenzugriff mit ADO.NET (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 21d19955e19931a573836baa6e0e0fee841e3548
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108279"
---
# <a name="data-access-using-adonet-ccli"></a>Datenzugriff mit ADO.NET (C++/CLI)
ADO.NET ist die .NET Framework-API für den Datenzugriff und bietet Power und einfache Verwendung von vorherigen Data Access-Lösungen. Dieser Abschnitt beschreibt einige der Probleme im Zusammenhang mit ADO.NET, die für Visual C++-Benutzer, wie z. B. das Marshalling von systemeigenen Typs eindeutig sind.  
  
 ADO.NET wird unter der Common Language Runtime (CLR) ausgeführt. Aus diesem Grund muss jede Anwendung, die mit ADO.NET interagiert auch die CLR abzielen. Allerdings bedeutet dies nicht, dass systemeigene Anwendungen ADO.NET verwenden können. In diesen Beispielen werden die Interaktion mit einer ADO.NET-Datenbank von systemeigenem Code veranschaulicht.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen für ADO.NET (C++/CLI)](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [Vorgehensweise: Marshallen von BSTR-Zeichenfolgen für ADO.NET (C++/CLI)](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen für ADO.NET (C++/CLI)](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [Vorgehensweise: Marshallen eines VARIANT für ADO.NET (C++/CLI)](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [Vorgehensweise: Marshallen eines SAFEARRAY für ADO.NET (C++/CLI)](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
|Bereich|Beschreibung|  
|-------------|-----------------|  
|[ADO.NET](/dotnet/framework/data/adonet/index)|Bietet eine Übersicht über ADO.NET eine Reihe von Klassen, die Datenzugriffsdienste für .NET-Programmierer verfügbar machen.|  
  
## <a name="see-also"></a>Siehe auch  
 [.NET Programmieren mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)