---
title: "Gemischte (systemeigene und verwaltete) Assemblys"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Gemischte Assemblys"
  - "Assemblys [C++], Gemischt"
  - "Interop [C++], Gemischte Assemblys"
  - "Interoperabilität [C++], Gemischte Assemblys"
  - "Verwalteter Code [C++], Interoperabilität"
  - "Gemischte Assemblys [C++]"
  - "Gemischte Assemblys [C++], Informationen zu gemischten Assemblys"
  - "Gemischte DLL laden [C++]"
  - "Systemeigener Code [C++], .NET-Interoperabilität"
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
caps.latest.revision: 35
caps.handback.revision: "35"
ms.author: "mblome"
manager: "ghogen"
---
# Gemischte (systemeigene und verwaltete) Assemblys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gemischte Assemblys können sowohl nicht verwaltete Maschinenanweisungen als auch MSIL\-Anweisungen enthalten.  Dadurch können sie .NET\-Komponenten aufrufen und von ihnen aufgerufen werden, wobei die Kompatibilität mit vollständig nicht verwalteten Komponenten erhalten bleibt.  Mit gemischten Assemblys können Entwickler Anwendungen mit einer Mischung aus verwalteten und nicht verwalteten Funktionen erstellen.  Deshalb sind gemischte Assemblys optimal für das Migrieren von vorhandenen Visual C\+\+\-Anwendungen zur .NET\-Plattform geeignet.  
  
 So kann z. B. eine vorhandene Anwendung, die vollständig aus nicht verwalteten Funktionen besteht, in die .NET\-Plattform integriert werden, indem lediglich ein Modul mit dem **\/clr**\-Compilerschalter neu kompiliert wird.  Dieses Modul kann dann .NET\-Features verwenden, bleibt aber mit dem Rest der Anwendung kompatibel.  Dadurch kann eine Anwendung schrittweise in die .NET\-Plattform konvertiert werden.  Es ist sogar möglich, sich für die verwaltete oder die nicht verwaltete Kompilierung für jede einzelne Funktion in derselben Datei gesondert zu entscheiden \(siehe [managed, unmanaged](../preprocessor/managed-unmanaged.md)\).  
  
 Visual C\+\+ unterstützt das Generieren von drei verschiedenen Typen verwalteter Assemblys: gemischte, reine und überprüfbare Assemblys.  Die beiden letzteren Typen werden unter [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md) behandelt.  
  
## In diesem Abschnitt  
 [Gewusst wie: Migrieren zu \/clr](../dotnet/how-to-migrate-to-clr.md)  
 Beschreibt die empfohlenen Schritte zum Einführen bzw. Aktualisieren der .NET\-Funktionen in der Anwendung.  
  
 [Gewusst wie: Kompilieren von MFC\-Code und ATL\-Code mit \/clr](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 Erläutert, wie vorhandene MFC\- und ATL\-Programme für die Common Language Runtime kompiliert werden können.  
  
 [Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md)  
 Beschreibt das Problem der "Ladeprogrammsperren" und die entsprechenden Lösungen.  
  
 [Bibliotheksunterstützung für verschiedene Assemblys](../dotnet/library-support-for-mixed-assemblies.md)  
 Erörtert, wie systemeigene Bibliotheken in **\/clr**\-Kompilierungen verwendet werden.  
  
 [Überlegungen zur Leistung](../dotnet/performance-considerations-for-interop-cpp.md)  
 Beschreibt, wie sich gemischte Assemblys und das Marshalling von Daten auf die Leistung auswirken.  
  
 [Anwendungsdomänen und Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)  
 Erörtert die Visual C\+\+\-Unterstützung für Anwendungsdomänen.  
  
 [Doppeltes Thunking](../dotnet/double-thunking-cpp.md)  
 Erörtert, wie sich ein systemeigener Einstiegspunkt für eine verwaltete Funktion auf die Leistung auswirkt.  
  
 [Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit \/clr erstellte COM\-Objekte verwendet werden](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 Erörtert, wie das ordnungsgemäße Schließen einer verwalteten Anwendung sichergestellt wird, die ein mit **\/clr** kompiliertes COM\-Objekt verwendet.  
  
 [Gewusst wie: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit der CRT\-Bibliotheks\-DLL](../dotnet/create-a-partially-trusted-application.md)  
 Beschreibt das Erstellen einer teilweise vertrauenswürdigen Common Language Runtime\-Anwendung mithilfe von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], indem die Abhängigkeit von msvcm90.dll aufgehoben wird.  
  
 Weitere Informationen über Codierungsrichtlinien für gemischte Assemblys finden Sie im MSDN\-Artikel zur Übersicht über die Interoperabilität von verwaltetem\/nicht verwaltetem Code unter [http:\/\/msdn.microsoft.com\/netframework\/default.aspx?pull\=\/library\/dndotnet\/html\/manunmancode.asp](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp).  
  
## Siehe auch  
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)