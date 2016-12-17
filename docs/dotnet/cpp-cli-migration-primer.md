---
title: "Einf&#252;hrung in die C++/CLI-Migration"
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
helpviewer_keywords: 
  - "C++/CLI Version 2"
  - "C++/CLI Version 2, Managed Extensions"
  - "Managed Extensions for C++, Aktualisieren der Syntax"
  - "Migration [C++], C++/CLI Version 2"
  - "Aktualisieren von Visual C++-Anwendungen, Managed Extensions for C++ auf Visual C++ 2005-Syntax"
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Einf&#252;hrung in die C++/CLI-Migration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dies ist eine Anweisung für die Migration von Visual C\+\+\-Programmen von Managed Extensions for C\+\+ zu [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Eine zusammengefasste Prüfliste der syntaktischen Änderungen finden Sie unter [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](assetId:///edbded88-7ef3-4757-bd9d-b8f48ac2aada).  
  
 C\+\+\/CLI erweitert ein dynamisches Komponentenprogrammierparadigma auf die ISO\-C\+\+\-Standardsprache.  Die neue Sprache hat gegenüber Managed Extensions eine ganze Reihe bedeutender Verbesserungen zu bieten.  Dieser Abschnitt stellt eine Auflistung der Sprachfeatures in Managed Extensions for C\+\+ bereit und, soweit dies möglich ist, deren Zuordnung zu [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)]. Zudem werden jene Konstrukte aufgezeigt, die nicht zugeordnet werden können.  
  
## In diesem Abschnitt  
 [Gliederung der Änderungen \(C\+\+\/CLI\)](../dotnet/outline-of-changes-cpp-cli.md)  
 Eine ausführliche Gliederung als Kurzreferenz mit einer Auflistung der Änderungen unter fünf allgemeinen Kategorien.  
  
 [Sprachschlüsselwörter \(C\+\+\/CLI\)](../dotnet/language-keywords-cpp-cli.md)  
 Behandelt Änderungen im Zusammenhang mit Sprachschlüsselwörtern, darunter die Beseitigung doppelter Unterstriche und die Einführung sowohl von kontextbezogenen Schlüsselwörtern als auch von durch Leerzeichen getrennten Schlüsselwörtern.  
  
 [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)  
 Betrachtet syntaktische Änderungen in der Deklaration des CTS \(Common Type System\). Dazu gehören Änderungen in der Deklaration von Klassen, Arrays \(einschließlich des Parameterarrays\), Enumerationen usw.  
  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 Präsentiert die Änderungen bei Klassenmembern, z. B. Skalare Eigenschaften, Indexeigenschaften, Operatoren, Delegaten und Ereignisse.  
  
 [Werttypen und ihr Verhalten \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Konzentriert sich auf Werttypen und die neue Familie innerer und fester Zeiger.  Befasst sich außerdem mit einer Reihe signifikanter semantischer Änderungen, wie der Einführung von implizitem Boxing, der Unveränderlichkeit geschachtelter Werttypen und dem Wegfall der Unterstützung für Standardkonstruktoren innerhalb von Wertklassen.  
  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)  
 Geht ausführlich auf semantische Änderungen ein, wie die Unterstützung von Umwandlungsnotation, das Verhalten von Zeichenfolgenliteralen und semantische Änderungen von C\+\+\/CLI gegenüber ISO\-C\+\+.  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)