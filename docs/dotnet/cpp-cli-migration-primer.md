---
title: C + c++ / CLI Migration Primer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5861a4931a1241a213157b94ca189c6b95f0fb6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccli-migration-primer"></a>Einführung in die C++/CLI-Migration
Dies ist eine Anleitung für die Migration von Visual C++-Programmen von Managed Extensions für C++ in Visual C++. Eine Zusammenfassung der Prüfliste syntaktische Änderungen, finden Sie unter [(NOTINBUILD) Managed Extensions for C++ Syntax Upgrade Checklist](http://msdn.microsoft.com/en-us/edbded88-7ef3-4757-bd9d-b8f48ac2aada).  
  
 C++/CLI erweitert ein dynamisches Komponentenprogrammierparadigma auf die ISO-C++-Standardsprache. Die neue Sprache hat gegenüber Managed Extensions eine ganze Reihe bedeutender Verbesserungen zu bieten. Dieser Abschnitt enthält eine Auflistung der Sprachfeatures in Managed Extensions für C++-Sprachfunktionen und deren Zuordnung zu Visual C++, in denen eine solche Zuordnung vorhanden ist, und Sprachfeatures für die keine Zuordnung vorhanden ist.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gliederung der Änderungen (C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)  
 Eine ausführliche Gliederung als Kurzreferenz mit einer Auflistung der Änderungen unter fünf allgemeinen Kategorien.  
  
 [Sprachschlüsselwörter (C++/CLI)](../dotnet/language-keywords-cpp-cli.md)  
 Behandelt Änderungen im Zusammenhang mit Sprachschlüsselwörtern, darunter die Beseitigung doppelter Unterstriche und die Einführung sowohl von kontextbezogenen Schlüsselwörtern als auch von durch Leerzeichen getrennten Schlüsselwörtern.  
  
 [Verwaltete Typen (C + c++ / CL)](../dotnet/managed-types-cpp-cl.md)  
 Betrachtet syntaktische Änderungen in der Deklaration des CTS Common Type System () - gehören Änderungen in der Deklaration von Klassen, Arrays (einschließlich des Parameterarrays), Enumerationen und So weiter.  
  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 Präsentiert die Änderungen bei Klassenmembern, z. B. Skalare Eigenschaften, Indexeigenschaften, Operatoren, Delegaten und Ereignisse.  
  
 [Werttypen und ihr Verhalten (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Konzentriert sich auf Werttypen und die neue Familie innerer und fester Zeiger. Befasst sich außerdem mit einer Reihe signifikanter semantischer Änderungen, wie der Einführung von implizitem Boxing, der Unveränderlichkeit geschachtelter Werttypen und dem Wegfall der Unterstützung für Standardkonstruktoren innerhalb von Wertklassen.  
  
 [Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)  
 Geht ausführlich auf semantische Änderungen ein, wie die Unterstützung von Umwandlungsnotation, das Verhalten von Zeichenfolgenliteralen und semantische Änderungen von C++/CLI gegenüber ISO-C++.  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (systemeigene und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)